# Percona Distribution for MySQL 8.0.43 using Percona Server for MySQL (2025-08-28)

Percona Distribution for MySQL is the most stable, scalable, and secure open source MySQL distribution, with two download options: one based on Percona Server for MySQL and one based on Percona XtraDB Cluster. [Install Percona Distribution for MySQL](installing.md).

This release is based on [Percona Server for MySQL 8.0.43-34](https://docs.percona.com/percona-server/8.0/release-notes/8.0.43-34.html) that includes all the features and bug fixes available in the [MySQL 8.0.43 Community Edition](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/news-8-0-43.html) and enterprise-grade features developed by Percona.

## Release highlights

### Percona Server for MySQL 8.0.43-34

Implements Link-Time Optimization (LTO) to generate more optimized release binaries, resulting in improved performance for specific workloads.

### MySQL 8.0.43

Improvements and bug fixes provided by Oracle for MySQL 8.0.43 and included in Percona Server for MySQL are the following:

* Fixed an issue where rebuilding a primary key with duplicate entries could cause the server to stop unexpectedly. (Bug #37822992)

* Fixed an issue related to dropping columns that were part of an index. (Bug #37726881)

* Fixed an issue with indexing spatial datatype columns. (Bug #36682518)

* Fixed an issue where creating a secondary index on a `VARCHAR` column could exceed configured memory limits, with the amount allocated being directly related to the `value of innodb_ddl_buffer_size`, leading to errors such as ERROR 1136 (21S01): Column count doesn't match value count at row 1. (Bug #37233273)

Find the complete list of bug fixes and changes in the [MySQL 8.0.43 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/news-8-0-43.html).

## Build & packaging notes

* The official packages were built with the `WITH_LTO=ON` flag to enable the Link-Time Optimization (LTO) feature.

## Supplied components

Review each component’s release notes for What’s new, improvements, or bug fixes. The following is a list of the components supplied with the Percona Server for MySQL-based variation of the Percona Distribution for MySQL:

| Component           | Version   | Description                                |
| ------------------- | --------- | -------------------------------------------|
| Orchestrator        | [3.2.6-18](https://github.com/percona/orchestrator/releases/tag/v3.2.6-18)     | The replication topology manager for Percona Server for MySQL|
| ProxySQL            | [2.7.3](https://docs.percona.com/proxysql/2.7.3.html)     | A high performance, high-availability, protocol-aware proxy for MySQL|
| Percona XtraBackup  | [8.0.35-34](https://docs.percona.com/percona-xtrabackup/8.0/release-notes/8.0/8.0.35-34.0.html)| An open-source hot backup utility for MySQL-based servers|
| Percona Toolkit     | [3.7.0-2](https://docs.percona.com/percona-toolkit/release_notes.html#v3-7-0-2-released-2025-05-14)     | The set of scripts to simplify and optimize database operation|
| MySQL Shell         | [8.0.43](https://dev.mysql.com/doc/relnotes/mysql-shell/8.0/en/news-8-0-43.html)    | An advanced client and code editor for MySQL Server|
| MySQL Router        | [8.0.43](https://dev.mysql.com/doc/relnotes/mysql-router/8.0/en/news-8-0-43.html)    | Lightweight middleware that provides transparent routing between your application and back-end MySQL servers|
