# Components

Percona Distribution for MySQL consists of the following **components**:

* [Percona Server for MySQL :octicons-link-external-16:](https://docs.percona.com/percona-server/{{vers}}/) is a drop-in replacement for MySQL Community Edition with the enterprise-grade features embedded by Percona.

* [Percona XtraDB Cluster :octicons-link-external-16:](https://docs.percona.com/percona-xtradb-cluster/{{vers}}/index.html) is the high-available clustering solution for MySQL. It is based on [Percona Server for MySQL :octicons-link-external-16:](https://docs.percona.com/percona-server/{{vers}}/index.html) and uses [Percona XtraBackup :octicons-link-external-16:](https://docs.percona.com/percona-xtrabackup/{{vers}}/index.html) for node provisioning.

* [Percona XtraBackup :octicons-link-external-16:](https://docs.percona.com/percona-xtrabackup/{{vers}}/) is an open-source hot backup utility for MySQL-based servers that doesn’t lock your database during the backup.

* [Orchestrator :octicons-link-external-16:(https://github.com/openark/orchestrator) is the replication topology manager for Percona Server for MySQL.

* [HAProxy :octicons-link-external-16:](http://www.haproxy.org/) is the default high-availability and load-balancing solution for Percona XtraDB Cluster.

* [ProxySQL :octicons-link-external-16:](https://proxysql.com/) is a high performance, high-availability, protocol-aware proxy for MySQL.

* [Percona Toolkit :octicons-link-external-16:](https://docs.percona.com/percona-toolkit/index.html) is the set of scripts to simplify and optimize database operation.

* [MySQL Shell :octicons-link-external-16:](https://dev.mysql.com/doc/mysql-shell/{{vers}}/en/) is an advanced client and code editor for MySQL Server.


* [MySQL Router :octicons-link-external-16:](https://dev.mysql.com/doc/mysql-router/{{vers}}/en/) is lightweight middleware that provides transparent routing between your application and back-end MySQL servers.

!!! important

    This release does not include the Percona Toolkit component. We will add it once a Percona Toolkit version compatible with MySQL 8.4 becomes available.
    
    ProxySQL contains counters that have not been updated to use the new terminology. Unexpected results may occur. In an 8.4.x environment, the binlog reader errors out during initialization due to the use of old terminology, such as the SHOW MASTER STATUS command.