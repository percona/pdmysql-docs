# Percona Distribution for MySQL 8.0.40 using Percona Server for MySQL (2025-01-02)

Percona Distribution for MySQL is the most stable, scalable, and secure open source MySQL distribution, with two download options: one based on Percona Server for MySQL and one based on Percona XtraDB Cluster. [Install Percona Distribution for MySQL](installing.md).

This release is based on [Percona Server for MySQL 8.0.40-31](https://docs.percona.com/percona-server/8.0/release-notes/8.0.40-31.html) that includes all the features and bug fixes available in the [MySQL 8.0.40 Community Edition](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/news-8-0-40.html) and enterprise-grade features developed by Percona.

## Release highlights

Improvements and bug fixes provided by Oracle for MySQL 8.0.40 and included in Percona Server for MySQL are the following:

* Changes in MySQL 8.0.33 caused queries using joins on InnoDB tables to perform worse because refactoring affected functions that were previously inline.

* The server crashed when it tried to update columns altered with NULL as the default value using the INSTANT algorithm.

* The server could crash during DELETE or UPDATE operations if a column was dropped using the INSTANT algorithm.

* Importing a table created under a different sql_mode sometimes led to schema mismatches, risking data corruption in secondary indexes. The fix now includes integrity checks on the imported tablespace.

* Rebuilding tables with secondary indexes required more file I/O operations compared to MySQL 8.0.26, which slowed down query performance.

Find the complete list of bug fixes and changes in the [MySQL 8.0.40 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/news-8-0-40.html).

## Supplied components

Review each component’s release notes for What’s new, improvements, or bug fixes. The following is a list of the components supplied with the Percona Server for MySQL-based variation of the Percona Distribution for MySQL:

| Component           | Version   | Description                                |
| ------------------- | --------- | -------------------------------------------|
| Orchestrator        | [3.2.6-15](https://github.com/percona/orchestrator/releases/tag/v3.2.6-15)     | The replication topology manager for Percona Server for MySQL|
| ProxySQL            | [2.7.1-1](https://docs.percona.com/proxysql/2.7.1-1.html)     | A high performance, high-availability, protocol-aware proxy for MySQL|
| Percona XtraBackup  | [8.0.35-31](https://docs.percona.com/percona-xtrabackup/8.0/release-notes/8.0/8.0.35-31.0.upd.html)| An open-source hot backup utility for MySQL-based servers|
| Percona Toolkit     | [3.7.0](https://docs.percona.com/percona-toolkit/release_notes.html#v3-6-0-released-2024-12-23)     | The set of scripts to simplify and optimize database operation|
| MySQL Shell         | [8.0.40](https://dev.mysql.com/doc/relnotes/mysql-shell/8.0/en/news-8-0-40.html)    | An advanced client and code editor for MySQL Server|
| MySQL Router        | [8.0.40](https://dev.mysql.com/doc/relnotes/mysql-router/8.0/en/news-8-0-40.html)    | Lightweight middleware that provides transparent routing between your application and back-end MySQL servers|
