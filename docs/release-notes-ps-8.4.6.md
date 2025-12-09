# Percona Distribution for MySQL 8.4.6 using Percona Server for MySQL (2025-09-08)

Percona Distribution for MySQL is more than just a version of MySQL; it is a comprehensive solution that combines Percona Server for MySQL with additional tools to create a cohesive environment. This distribution is reliable, scalable, and secure, ensuring that all components have been tested to work seamlessly together. You can choose from two download options: one that uses Percona Server for MySQL and another that utilizes Percona XtraDB Cluster. Refer to [Install Percona Distribution for MySQL](installing.md).

This release is based on [Percona Server for MySQL 8.4.6-6](https://docs.percona.com/percona-server/8.4/release-notes/8.4.6-6.html) that includes all the features and bug fixes available in the [MySQL 8.4.6 Community Edition](https://dev.mysql.com/doc/relnotes/mysql/8.4/en/news-8-4-6.html) and enterprise-grade features developed by Percona.

## Release highlights

### Percona Server for MySQL 8.4.6-6

Implements Link-Time Optimization (LTO) to generate more optimized release binaries, resulting in improved performance for specific workloads.

### MySQL 8.4.6

Improvements and bug fixes introduced by Oracle for MySQL 8.4.6 and included in Percona Server for MySQL are the following:

* Fixed an issue where rebuilding a primary key with duplicate entries could cause the server to stop unexpectedly. (Bug #37822992)

* Fixed an issue related to dropping columns that were part of an index. (Bug #37726881)

* Fixed an issue with indexing spatial datatype columns. (Bug #36682518)

* Fixed an issue where creating a secondary index on a `VARCHAR` column could exceed configured memory limits, with the amount allocated being directly related to the `value of innodb_ddl_buffer_size`, leading to errors such as ERROR 1136 (21S01): Column count doesn't match value count at row 1. (Bug #37233273)

Find the complete list of bug fixes and changes in the [MySQL 8.4.6 release notes](https://dev.mysql.com/doc/relnotes/mysql/8.4/en/news-8-4-6.html).

## Build & packaging notes

* The official packages were built with the `WITH_LTO=ON` flag to enable the Link-Time Optimization (LTO) feature.

* Percona Server for MySQL 8.4.6.6 supports Red Hat Enterprise Linux (RHEL) 10.

## Known issues
    
* ProxySQL contains counters that have not been updated to use the new terminology. Unexpected results may occur. In an 8.4.x environment, the binlog reader errors out during initialization due to the use of old terminology, such as the SHOW MASTER STATUS command.

## Supplied components

Review each component’s release notes for What’s new, improvements, or bug fixes. The following is a list of the components supplied with the Percona Server for MySQL-based variation of the Percona Distribution for MySQL.

| Component           | Version   | Description                                |
| ------------------- | --------- | -------------------------------------------|
| Orchestrator        | [3.2.6-18](https://github.com/percona/orchestrator/releases/tag/v3.2.6-18)     | The replication topology manager for Percona Server for MySQL|
| ProxySQL            | [2.7.3](https://docs.percona.com/proxysql/2.7.3.html)     | A high performance, high-availability, protocol-aware proxy for MySQL|
| Percona Toolkit     | [3.7.0-2](https://docs.percona.com/percona-toolkit/release_notes.html#v3-7-0-2-released-2025-05-14)     | The set of scripts to simplify and optimize database operation. |
| Percona XtraBackup  | [8.4.0-4](https://docs.percona.com/percona-xtrabackup/8.4/release-notes/8.4.0-4.html)| An open-source hot backup utility for MySQL-based servers|
| MySQL Shell         | [8.4.6](https://dev.mysql.com/doc/relnotes/mysql-shell/8.4/en/news-8-4-6.html)    | An advanced client and code editor for MySQL Server|
| MySQL Router        | [8.4.6](https://dev.mysql.com/doc/relnotes/mysql-router/8.4/en/news-8-4-6.html)    | Lightweight middleware that provides transparent routing between your application and back-end MySQL servers|
