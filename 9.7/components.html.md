> For the complete documentation index, see [llms.txt](https://docs.percona.com/percona-distribution-for-mysql/9.7/llms.txt).

# Components

Percona Distribution for MySQL consists of the following **components**:

- [Percona Server for MySQL](https://docs.percona.com/percona-server/9.7/) is a drop-in replacement for MySQL Community Edition with the enterprise-grade features embedded by Percona.
- [Percona XtraDB Cluster](https://docs.percona.com/percona-xtradb-cluster/9.7/index.html) is the high-available clustering solution for MySQL. It is based on [Percona Server for MySQL](https://docs.percona.com/percona-server/9.7/index.html) and uses [Percona XtraBackup](https://docs.percona.com/percona-xtrabackup/9.7/index.html) for node provisioning.
- [Percona XtraBackup](https://docs.percona.com/percona-xtrabackup/9.7/) is an open-source hot backup utility for MySQL-based servers that doesn’t lock your database during the backup.
- [Orchestrator](https://github.com/openark/orchestrator) is the replication topology manager for Percona Server for MySQL.
- [HAProxy](http://www.haproxy.org/) is the default high-availability and load-balancing solution for Percona XtraDB Cluster.
- [ProxySQL](https://proxysql.com/) is a high performance, high-availability, protocol-aware proxy for MySQL.
- [Percona Toolkit](https://docs.percona.com/percona-toolkit/index.html) is the set of scripts to simplify and optimize database operation.
- [MySQL Shell](https://dev.mysql.com/doc/mysql-shell/9.7/en/) is an advanced client and code editor for MySQL Server.
- [MySQL Router](https://dev.mysql.com/doc/mysql-router/9.7/en/) is lightweight middleware that provides transparent routing between your application and back-end MySQL servers.

Important

This release does not include the Percona Toolkit component. We will add it once a Percona Toolkit version compatible with MySQL 9.7 becomes available.

In 9.7.x environments, the ProxySQL binlog reader can fail to initialize because it uses legacy commands, such as SHOW MASTER STATUS. Some internal counters also use outdated terminology. To address most terminology issues, enable the [terminology_use_previous](https://dev.mysql.com/doc/refman/9.7/en/replication-options-replica.html#sysvar_terminology_use_previous) system variable on the database server. This workaround addresses only terminology compatibility and may not fix all failures.
