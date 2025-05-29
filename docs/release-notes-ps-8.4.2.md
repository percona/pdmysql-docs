# Percona Distribution for MySQL 8.4.2 using Percona Server for MySQL (2024-11-07)

Percona Distribution for MySQL is the most stable, scalable, and secure open source MySQL distribution, with two download options: one based on Percona Server for MySQL and one based on Percona XtraDB Cluster. [Install Percona Distribution for MySQL](installing.md).

This release is based on [Percona Server for MySQL 8.4.2-2](https://docs.percona.com/percona-server/8.4/release-notes/8.4.2-2.html) that includes all the features and bug fixes available in the [MySQL 8.4.1 Community Edition](https://dev.mysql.com/doc/relnotes/mysql/8.4/en/news-8-4-1.html) and [MySQL 8.4.2 Community Edition](https://dev.mysql.com/doc/relnotes/mysql/8.4/en/news-8-4-2.html) and enterprise-grade features developed by Percona.

## Release highlights

Improvements and bug fixes introduced by Oracle for MySQL 8.4.1 and 8.4.2 and included in Percona Server for MySQL are the following:

* MySQL stopped unexpectedly during an UPDATE after an ALTER TABLE operation.

* Shutting down the server after an XA START with an empty XA transaction caused it to stop unexpectedly.

* Shutting down the replication applier or binlog applier during an empty XA transaction caused the system to stop unexpectedly.

* The result from a spatial index with a column containing a spatial reference identifier (SRID) was empty. Using FORCE INDEX to scan this index caused an assertion error.

* In some cases, after creating more than 8000 tables, the server failed to restart. 

* Startup tablespace file scanning performance was improved.

Find the complete list of bug fixes and changes in the [MySQL 8.4.1 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.4/en/news-8-4-1.html) and [MySQL 8.4.2 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.4/en/news-8-4-2.html).

## Supplied components

Review each component’s release notes for What’s new, improvements, or bug fixes. The following is a list of the components supplied with the Percona Server for MySQL-based variation of the Percona Distribution for MySQL.

!!! important

    This release does not include the Percona Toolkit component. We will add it once a Percona Toolkit version compatible with MySQL 8.4 becomes available.
    
    ProxySQL contains counters that have not been updated to use the new terminology. Unexpected results may occur. In an 8.4.x environment, the binlog reader errors out during initialization due to the use of old terminology, such as the SHOW MASTER STATUS command.

| Component           | Version   | Description                                |
| ------------------- | --------- | -------------------------------------------|
| Orchestrator        | [3.2.6-14](https://github.com/percona/orchestrator/releases/tag/v3.2.6-14)     | The replication topology manager for Percona Server for MySQL|
| ProxySQL            | [2.7.1](https://docs.percona.com/proxysql/2.7.1.html)     | A high performance, high-availability, protocol-aware proxy for MySQL|
| Percona XtraBackup  | [8.4.0-1](https://docs.percona.com/percona-xtrabackup/8.4/release-notes/8.4.0-1.html)| An open-source hot backup utility for MySQL-based servers|
| MySQL Shell         | [8.4.1](https://dev.mysql.com/doc/relnotes/mysql-shell/8.4/en/news-8-4-1.html)    | An advanced client and code editor for MySQL Server|
| MySQL Router        | [8.4.2](https://dev.mysql.com/doc/relnotes/mysql-router/8.4/en/news-8-4-2.html)    | Lightweight middleware that provides transparent routing between your application and back-end MySQL servers|
