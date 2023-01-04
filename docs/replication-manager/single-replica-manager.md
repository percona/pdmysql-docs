# Single replica manager for Percona XtraDB Cluster

{% include './snippets/tech-preview/_tech-preview-feature.md'%}

The single replica manager is a simplified version of the [Replication manager for Percona XtraDB Cluster](replication-manager-for-pxc.md) and is intended to manage a single replica. 

The single replica manager requires using a [global transaction identifier (GTID)](../glossary.md#gtid) (Oracle implementation).

To use the single replica manager script, edit the script and adjust the 'sourceCandidates' and 'replCreds' variables. If the Percona XtraDB Cluster nodes are '10.1.1.10', '10.1.1.11', and '10.1.1.12', and the replication user is 'repluser' with a password set to 'replpass', the variables should look like the following:

```text
sourceCandidates="10.1.1.10 10.1.1.11 10.1.1.12"
replCreds="source_user='repl', source_password='replpass'"
```

The credentials to the local MySQL server should be located in the `~/.my.cnf` file of the user under which the cron job is defined. The last step is to enable the cron job that runs every minute:

```bash
* * * * * /usr/bin/replication_manager.sh 
```

If you face any issues, do the following:

```text
touch /tmp/replication_manager.log 
chmod a+w /tmp/replication_manager.log
```

Check the `bash trace` file for any issues. During the maintenance on the replica, do the following:

```text
touch /tmp/replication_manager.off
```

Once the maintenance is over, remove the file.
