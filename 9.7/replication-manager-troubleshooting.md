> For the complete documentation index, see [llms.txt](https://docs.percona.com/percona-distribution-for-mysql/9.7/llms.txt).

# Replication manager troubleshooting

The [replication manager](https://docs.percona.com/percona-distribution-for-mysql/9.7/replication-manager-for-pxc.html#configuration-steps) script outputs its trace (bash -x) to the file `/tmp/replication_manager.log` if present. If there is an error during the manual invocation or something unexpected happens, touch the file, run the script manually and look at the file content for hints. If you think there is a bug, create an issue on [GitHub](https://github.com/percona/replication-manager/issues/new) .
