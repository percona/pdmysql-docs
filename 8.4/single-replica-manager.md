> For the complete documentation index, see [llms.txt](https://docs.percona.com/percona-distribution-for-mysql/8.4/llms.txt).

# Single replica manager for Percona XtraDB Cluster

This feature is a tech preview. Before using this feature in a production environment, follow these steps:

• Test restoring production from physical backups in your environment.

• Use an alternative backup method to ensure redundancy.

The single replica manager is a simplified version of the [Replication manager for Percona XtraDB Cluster](https://docs.percona.com/percona-distribution-for-mysql/8.4/replication-manager-for-pxc.html) and is intended to manage a single replica.

The single replica manager requires using a [global transaction identifier (GTID)](https://docs.percona.com/percona-distribution-for-mysql/8.4/glossary.html#gtid) (Oracle implementation).

To use the single replica manager script, edit the script and adjust the ‘sourceCandidates’ and ‘replCreds’ variables. If the Percona XtraDB Cluster nodes are ‘10.1.1.10’, ‘10.1.1.11’, and ‘10.1.1.12’, and the replication user is ‘repluser’ with a password set to ‘replpass’, the variables should look like the following:

```
sourceCandidates="10.1.1.10 10.1.1.11 10.1.1.12"
replCreds="source_user='repl', source_password='replpass'"
```

The credentials to the local MySQL server should be located in the `~/.my.cnf` file of the user under which the cron job is defined. The last step is to enable the cron job that runs every minute:

```
* * * * * /usr/bin/replication_manager.sh
```

If you face any issues, do the following:

```
touch /tmp/replication_manager.log 
chmod a+w /tmp/replication_manager.log
```

Check the `bash trace` file for any issues. During the maintenance on the replica, do the following:

```
touch /tmp/replication_manager.off
```

Once the maintenance is over, remove the file.
