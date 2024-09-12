# Replication manager troubleshooting

The [replication manager](replication-manager-for-pxc.md#configuration-steps) script outputs its trace (bash -x) to the file `/tmp/replication_manager.log` if present. If there is an error during the manual invocation or something unexpected happens, touch the file, run the script manually and look at the file content for hints. If you think there is a bug, create an issue on [GitHub](https://github.com/percona/replication-manager/issues/new)).
