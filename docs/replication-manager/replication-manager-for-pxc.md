# Replication manager for Percona XtraDB Cluster

The feature is a [tech preview](../glossary.md#tech-preview). Before using this feature in production, we recommend that you test restoring production from physical backups in your environment, and also use the alternative backup method for redundancy.

The replication manager script helps manage [multi-source replication](../glossary.md#multi-source-replication) between multiple Percona XtraDB Cluster clusters. This tool has a failover mechanism and can automatically perform a failover due to source or replica node failures, service degradation, or maintenance requirements.

The replication manager script monitors the active source-replica replication channel. If the source or replica node fails, the script re-establishes the replication channel using alternative source or replica cluster nodes.

## Example

For example, we deploy multi-source replication links between three data centers: DC1, DC2, and DC3. In each data center, there are three Percona XtraDB Cluster nodes form distinct Percona XtraDB Cluster clusters. The data centers contain the following nodes:

|  DC1  |  DC2  |  DC3  |
| ----- | ----- | ----- |
| DC1-1 | DC2-1 | DC3-1 |
| DC1-2 | DC2-2 | DC3-2 |
| DC1-3 | DC2-3 | DC3-3 |
 
The topology is the following:

```text
DC2 <=> DC1 <=> DC3
```

All of the nodes are sources and replicas. DC1 is a replica of DC2 and DC3. DC2 and DC3 are replicas of DC1.

```text
+----------------+---------------+
| clusterSlave   | clusterMaster |
+----------------+---------------+
| DC1            | DC2           |
| DC1            | DC3           |
| DC2            | DC1           |
| DC3            | DC1           |
+----------------+---------------+
```

The example of the minimal MySQL configuration file for DC1 that is common for all three DC1 nodes:

```text
[mysqld]
# General galera reqs
default_storage_engine=InnoDB
innodb_autoinc_lock_mode=2

# Replication settings
binlog_format=ROW
server-id=1
log-bin=mysql-bin
log_replica_updates
expire_logs_days=7
gtid_mode = ON
enforce_gtid_consistency=ON
skip-replica-start
    
# Galera configuration
wsrep_provider=/usr/lib/galera3/libgalera_smm.so
wsrep_cluster_address=gcomm://10.0.4.160,10.0.4.162,10.0.4.163
wsrep_replica_threads= 2
wsrep_log_conflicts
wsrep_cluster_name=DC1
pxc_strict_mode=ENFORCING
wsrep_sst_method=xtrabackup-v2
wsrep_sst_auth="root:root"
```

All nodes have the same `server-id` value.

### Configuration steps

1. Bootstrap the cluster on DC1-1 node by running the following commands as root or using sudo:

    ```bash
    [root@DC1-1 ~]# /etc/init.d/mysql stop 
    [root@DC1-1 ~]# /etc/init.d/mysql bootstrap-pxc
    ```

2. On DC1-2 node, stop MySQL, delete the content of the datadir to force the SST, and start MySQL. Run the following commands as root or using sudo:

    ```bash
    [root@DC1-2 ~]# /etc/init.d/mysql stop
    [root@DC1-2 ~]# rm -rf /var/lib/mysql/*
    [root@DC1-2 ~]# /etc/init.d/mysql start
    ```

3. Once the SST of DC1-2 node is completed, proceed on DC1-3. Run the following commands as root or using sudo:

    ```bash
    [root@DC1-3 ~]# /etc/init.d/mysql stop
    [root@DC1-3 ~]# rm -rf /var/lib/mysql/*
    [root@DC1-3 ~]# /etc/init.d/mysql start
    ```

4. The DC1 cluster uses a single [GTID](../glossary.md#gtid) sequence. To make sure `GTID_PURGED` is the same, run the following commands on DC1-1, DC1-2, and DC1-3 nodes:

    ```{.bash data-prompt="mysql>"}
    mysql> flush logs;
    mysql> purge binary logs to 'mysql-bin.000003';
    ```

    `mysql-bin.000003` is the last file returned when you run the following command:
    
    ```{.bash data-prompt="mysql>"}
    mysql>`SHOW BINARY LOGS`
    ```

5. Adjust the aformentioned steps to set up the DC2 and DC3 clusters accordingly.
    
6. Add privileges for replication between all nodes only for DC1: 

    ```bash
    GRANT REPLICATION CLIENT, REPLICATION SLAVE ON *.* TO 'repl'@'%' identified by 'replpass';
    ```

7. Add the replication tables. For example, we add the tables to DC1: 
    
    ```text
    create database if not exists percona;
    use percona;
    CREATE TABLE `replication` (
      `host` varchar(40) NOT NULL,
      `weight` int(11) NOT NULL DEFAULT 0,
      `localIndex` int(11) DEFAULT NULL,
      `isSlave` enum('No','Yes','Proposed','Failed') DEFAULT 'No',
      `lastUpdate` timestamp NOT NULL DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP,
      `lastHeartbeat` timestamp NOT NULL DEFAULT '1971-01-01 00:00:00',
      `connectionName` varchar(64) NOT NULL,
      PRIMARY KEY (`connectionName`,`host`),
      KEY `idx_host` (`host`)
    ) ENGINE=InnoDB DEFAULT CHARSET=latin1;
    CREATE TABLE `cluster` (
      `cluster` varchar(31) NOT NULL,
      `masterCandidates` varchar(255) NOT NULL,
      `replCreds` varchar(255) NOT NULL,
      PRIMARY KEY (`cluster`)
    ) ENGINE=InnoDB DEFAULT CHARSET=latin1;
    CREATE TABLE `link` (
      `clusterSlave` varchar(31) NOT NULL,
      `clusterMaster` varchar(31) NOT NULL,
      PRIMARY KEY (`clusterSlave`,`clusterMaster`)
    ) ENGINE=InnoDB DEFAULT CHARSET=latin1;
    CREATE TABLE `weight` (
     `cluster` varchar(31) NOT NULL,
     `nodename` varchar(255) NOT NULL,
     `weight` int NOT NULL DEFAULT 0, 
     PRIMARY KEY (`cluster`,`nodename`)
    ) ENGINE=InnoDB DEFAULT CHARSET=latin1;
    ```

    The replication manager writes to the tables. You do not need to adjust the tables.

8. The cluster table contains the details of each cluster. The cluster name is defined in the `wsrep_cluster_name` variable value:

    ```bash
    INSERT INTO `cluster` VALUES ('DC1','10.0.4.160 10.0.4.162 10.0.4.163','source_user=\'repl\', source_password=\'replpass\'');
    INSERT INTO `cluster` VALUES ('DC2','10.0.4.164 10.0.4.165 10.0.4.166','source_user=\'repl\', source_password=\'replpass\'');
    INSERT INTO `cluster` VALUES ('DC3','10.0.4.167 10.0.4.168 10.0.4.169','source_user=\'repl\', source_password=\'replpass\'');
    ```

9. Add the required links:

    ```bash
    INSERT INTO `link` VALUES ('DC1','DC2');
    INSERT INTO `link` VALUES ('DC1','DC3');
    INSERT INTO `link` VALUES ('DC2','DC1');
    INSERT INTO `link` VALUES ('DC3','DC1');
    ```

10. Add the weight:

    ```bash
    INSERT INTO `weight` VALUES('DC1','DC1-1',10); 
    INSERT INTO `weight` VALUES('DC1','DC1-2',11); 
    INSERT INTO `weight` VALUES('DC2','DC2-1',9);
    INSERT INTO `weight` VALUES('DC2','DC2-2',12);
    INSERT INTO `weight` VALUES('DC3','DC3-1',11);
    ```

    The node in the cluster with the highest value is the first to be selected.

11. Provision the remote clusters and start replication. 

    On one of the DC1 nodes, for example DC1-1, perform a `mysqldump` as root or using sudo:

    ```bash
    [root@DC1-1 ~]# mysqldump -u root -p --source-data=2 --single-transaction -R -A -E > dump.sql
    ```  

12. Compress the file if it's too large. You can use [Percona XtraBackup to compress the data](https://docs.percona.com/percona-xtrabackup/8.0/backup_scenarios/compressed_backup.html). Copy the backup file to one node in each remote cluster, for example to DC2-1 and DC3-1. 

    To restore the dump, run the following commands as root or using sudo:

    ```bash
    [root@DC2-1 ~]# mysql -u root -p < dump.sql
    ```

    and

    ```bash
    [root@DC3-1 ~]# mysql -u root -p < dump.sql
    ```

13. Configure the replication. Set up the first replication links manually. 

    For example, on DC2-1 run:

    ```{.bash data-prompt="mysql>"}
    mysql> change replication source to source_host='WAN IP of DC1-1', source_user='repl', source_password='replpass', SOURCE_AUTO_POSITION = 1 FOR CHANNEL 'DC2-DC1';
    mysql> start replica FOR CHANNEL 'DC2-DC1';
    ```
    
    on DC3-1 run: 

    ```{.bash data-prompt="mysql>"}
    mysql> change replication source to source_host='WAN IP of DC1-1', source_user='repl', source_password='replpass', SOURCE_AUTO_POSITION = 1 FOR CHANNEL 'DC3-DC1';
    mysql> start replica FOR CHANNEL 'DC3-DC1';
    ```

    For the other direction, use DC1-1 for both:

    ```{.bash data-prompt="mysql>"}
    mysql> change replication source to source_host='WAN IP of DC2-1', source_user='repl', source_password='replpass', SOURCE_AUTO_POSITION = 1 FOR CHANNEL 'DC1-DC2';
    mysql> start replica FOR CHANNEL 'DC1-DC2';
    mysql> change replication source to source_host='WAN IP of DC3-1', source_user='repl', source_password='replpass', SOURCE_AUTO_POSITION = 1 FOR CHANNEL 'DC1-DC3';
    mysql> start replica FOR CHANNEL 'DC1-DC3';
    ```

    Now, all the clusters are linked in a source to source way. 

14. Install and enable Percona XtraDB Cluster-based variant of Percona Distribution for MySQL as described in [Install Percona Distribution for MySQL](https://docs.percona.com/percona-distribution-for-mysql/8.0/installing.html#procedure).

15. Install the packages for `replication_manager.sh` script depending on your operating system. On each node, perform the following steps as root or using sudo:

    === "On Debian and Ubuntu Linux"

        ```{.bash data-prompt="$"}
        $ sudo apt install percona-replication-manager
        ```
    
    === "On Red Hat Enterprise Linux and derivatives"

        ```{.bash data-prompt="$"}
        $ sudo yum install percona-replication-manager    
        ```

    When executed for the first time, the replication manager detects the current replication links and inserts rows in to the `percona.replication table`. In order to avoid issues, start with the replica nodes. The mysql credentials should be specified in the `/root/.my.cnf` file. On these nodes (DC1-1, DC2-1 and DC3-1), execute the script manually:
    
    ```{.bash data-prompt="$"}
    $ /usr/bin/replication_manager.sh
    ```

    The replication state should be unchanged and the `percona.replication` table should contain the following rows:

    ```{.bash data-prompt="mysql>"}
    mysql> SELECT * FROM percona.replication;
    ```

    ??? example "Expected output"

        ```text
        +-------+--------+------------+-----------+---------------------+---------------------+----------------+
        | host  | weight | localIndex | isSlave   | lastUpdate          | lastHeartbeat       | connectionName |
        +-------+------- +------------+-----------+---------------------+---------------------+----------------+
        | DC1-1 |      10|          1 | Yes       | 2017-06-30 13:03:01 | 2017-06-30 13:03:01 | DC1-DC2        |
        | DC1-1 |      11|          1 | Yes       | 2017-06-30 13:03:01 | 2017-06-30 13:03:01 | DC1-DC3        |
        | DC2-1 |       9|          1 | Yes       | 2017-06-30 13:03:01 | 2017-06-30 13:03:01 | DC2-DC1        |
        | DC3-1 |      11|          1 | Yes       | 2017-06-30 13:03:01 | 2017-06-30 13:03:01 | DC3-DC1        |
        +-------+--------+------------+-----------+---------------------+---------------------+----------------+
        12 rows in set (0.00 sec)
        ```

    If you have issues on these step, see the [Replication manager troubleshooting](replication-manager-troubleshooting.md) document.

    On these same nodes, enable the cron job:

    ```bash
    * * * * * /usr/bin/replication_manager.sh 
    ```

    Wait at least one minute and proceed with the other nodes. Try a manual run first to see if the script adds a line to the replication table for the host, for example, isSlave = No. Then add the cron jobs. 
    
    ```{.bash data-prompt="mysql>"}
    mysql> SELECT * FROM percona.replication;
    ```

    ??? example "Expected output"

        ```text
        +-------+--------+------------+-----------+---------------------+---------------------+----------------+
        | host  | weight | localIndex | isSlave   | lastUpdate          | lastHeartbeat       | connectionName |
        +-------+------- +------------+-----------+---------------------+---------------------+----------------+
        | DC1-1 |      10|          1 | Yes       | 2017-06-30 13:13:01 | 2017-06-30 13:13:01 | DC1-DC2        |
        | DC1-2 |      11|          2 | No        | 2017-06-30 13:13:01 | 2017-06-30 13:13:01 | DC1-DC2        |
        | DC1-3 |       9|          0 | No        | 2017-06-30 13:13:01 | 2017-06-30 13:13:01 | DC1-DC2        |
        | DC1-1 |      11|          1 | Yes       | 2017-06-30 13:13:01 | 2017-06-30 13:13:01 | DC1-DC3        |
        | DC1-2 |      12|          2 | No        | 2017-06-30 13:13:01 | 2017-06-30 13:13:01 | DC1-DC3        |
        | DC1-3 |       0|          0 | No        | 2017-06-30 13:13:01 | 2017-06-30 13:13:01 | DC1-DC3        |
        | DC2-1 |       0|          1 | Yes       | 2017-06-30 13:13:01 | 2017-06-30 13:13:01 | DC2-DC1        |
        | DC2-2 |       0|          0 | No        | 2017-06-30 13:13:01 | 2017-06-30 13:13:01 | DC2-DC1        |
        | DC2-3 |       0|          2 | No        | 2017-06-19 15:58:01 | 2017-06-19 15:58:01 | DC2-DC1        |
        | DC3-1 |       0|          1 | Yes       | 2017-06-30 13:13:01 | 2017-06-30 13:13:01 | DC3-DC1        |
        | DC3-2 |       0|          2 | No        | 2017-06-30 13:13:01 | 2017-06-30 13:13:01 | DC3-DC1        |
        | DC3-3 |       0|          0 | No        | 2017-06-30 13:13:01 | 2017-06-30 13:13:01 | DC3-DC1        |
        +-------+--------+------------+-----------+---------------------+---------------------+----------------+
        ```

!!! admonition "See also"

    To manage a single replica, see [Single replica manager for Percona XtraDB Cluster](single-replica-manager.md).
