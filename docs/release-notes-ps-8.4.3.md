# Percona Distribution for MySQL 8.4.3 using Percona Server for MySQL (2024-12-18)

Percona Distribution for MySQL is the most stable, scalable, and secure open source MySQL distribution, with two download options: one based on Percona Server for MySQL and one based on Percona XtraDB Cluster. [Install Percona Distribution for MySQL](installing.md).

This release is based on [Percona Server for MySQL 8.4.3-3](https://www.percona.com/doc/percona-server/8.4/release-notes/8.4.3-3.html) that includes all the features and bug fixes available in the [MySQL 8.4.3 Community Edition](https://dev.mysql.com/doc/relnotes/mysql/8.4/en/news-8-4-1.html) and enterprise-grade features developed by Percona.

## Release highlights

Improvements and bug fixes introduced by Oracle for MySQL 8.4.3 and included in Percona Server for MySQL are the following:

* The query `SELECT * FROM sys.innodb_lock_waits;` now fetches only two locks per wait, instead of scanning all locks twice, improving performance under heavy load. Additionally, primary keys have been added to `DATA_LOCKS` and `DATA_LOCK_WAITS`. (Bug #100537, Bug #31763497)

* Changes in MySQL 8.0.33 caused performance degradation for queries using joins on `InnoDB` tables due to refactoring of functions that were previously inline.

* The server crashed when it tried to update columns altered with `NULL` as the default value using the `INSTANT` algorithm.

* The server could crash during `DELETE` or `UPDATE` operations if a column was dropped using the `INSTANT` algorithm.

* Importing a table created under a different `sql_mode` sometimes led to schema mismatches, risking data corruption in secondary indexes. The fix now includes integrity checks on the imported tablespace.

* Rebuilding tables with secondary indexes required more file `I/O` operations compared to MySQL 8.0.26, which slowed down query performance.

Find the complete list of bug fixes and changes in the [MySQL 8.4.3 release notes](https://dev.mysql.com/doc/relnotes/mysql/8.4/en/news-8-4-3.html).

## Known issues

* This release does not include the Percona Toolkit component. We will add it once a Percona Toolkit version compatible with MySQL 8.4 becomes available.
    
* ProxySQL contains counters that have not been updated to use the new terminology. Unexpected results may occur. In an 8.4.x environment, the binlog reader errors out during initialization due to the use of old terminology, such as the SHOW MASTER STATUS command.

## Supplied components

Review each component’s release notes for What’s new, improvements, or bug fixes. The following is a list of the components supplied with the Percona Server for MySQL-based variation of the Percona Distribution for MySQL.

| Component           | Version   | Description                                |
| ------------------- | --------- | -------------------------------------------|
| Orchestrator        | [3.2.6-15](https://github.com/percona/orchestrator/releases/tag/v3.2.6-15)     | The replication topology manager for Percona Server for MySQL|
| ProxySQL            | [2.7.1-1](https://docs.percona.com/proxysql/2.7.1-1.html)     | A high performance, high-availability, protocol-aware proxy for MySQL|
| Percona XtraBackup  | [8.4.0-1](https://docs.percona.com/percona-xtrabackup/8.4/release-notes/8.4.0-1.html)| An open-source hot backup utility for MySQL-based servers|
| MySQL Shell         | [8.4.3](https://dev.mysql.com/doc/relnotes/mysql-shell/8.4/en/news-8-4-3.html)    | An advanced client and code editor for MySQL Server|
| MySQL Router        | [8.4.3](https://dev.mysql.com/doc/relnotes/mysql-router/8.4/en/news-8-4-3.html)    | Lightweight middleware that provides transparent routing between your application and back-end MySQL servers|
