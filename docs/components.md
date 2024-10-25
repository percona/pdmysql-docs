# Components

Percona Distribution for MySQL consists of the following **components**:

* [Percona Server for MySQL](https://docs.percona.com/percona-server/{{vers}}/) is a drop-in replacement for MySQL Community Edition with the enterprise-grade features embedded by Percona.

* [Percona XtraBackup](https://docs.percona.com/percona-xtrabackup/{{vers}}/) is an open-source hot backup utility for MySQL-based servers that doesn’t lock your database during the backup.


* [Orchestrator](https://github.com/openark/orchestrator) is the replication topology manager for *Percona Server for MySQL*.


* [ProxySQL](https://proxysql.com/) is a high performance, high-availability, protocol-aware proxy for MySQL.


* [MySQL Shell](https://dev.mysql.com/doc/mysql-shell/{{vers}}/en/) is an advanced client and code editor for MySQL Server.


* [MySQL Router](https://dev.mysql.com/doc/mysql-router/{{vers}}/en/) is lightweight middleware that provides transparent routing between your application and back-end MySQL servers.

!!! important

    This release does not include the Percona Toolkit component. We will add it once a Percona Toolkit version compatible with MySQL 8.4 becomes available.
    
    ProxySQL contains counters that have not been updated to use the new terminology. Unexpected results may occur. In an 8.4.x environment, the binlog reader errors out during initialization due to the use of old terminology, such as the SHOW MASTER STATUS command.