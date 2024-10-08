# Percona Distribution for MySQL 8.0.39 using Percona Server for MySQL (2024-10-08)

Percona Distribution for MySQL is the most stable, scalable, and secure open source MySQL distribution, with two download options: one based on Percona Server for MySQL and one based on Percona XtraDB Cluster. [Install Percona Distribution for MySQL](installing.md).

This release is based on [Percona Server for MySQL 8.0.39-30](https://www.percona.com/doc/percona-server/8.0/release-notes/8.0.39-30.html) that includes all the features and bug fixes available in the [MySQL 8.0.38 Community Edition](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/news-8-0-38.html) and [MySQL 8.0.39 Community Edition](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/news-8-0-39.html) and enterprise-grade features developed by Percona.

## Release highlights

Improvements and bug fixes provided by Oracle for MySQL 8.0.38, MySQL 8.0.39 and included in Percona Server for MySQL are the following:

* The server could not restart successfully after creating a large number of tables (8001 or more). This issue, Bug #36808732, is a regression of Bug #33398681.

* Enhanced performance of tablespace file scanning during startup. (Bug #110402, Bug #35200385)

* InnoDB file system operations now consistently perform an fsync on the parent directory when carrying out directory-altering tasks. (Bug #36174938)

* Worker jobs now include details about the relay log file that initiated the transaction, rather than relying on the default specified by `relay_log`.

Find the complete list of bug fixes and changes in the [MySQL 8.0.38 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/news-8-0-38.html) and [MySQL 8.0.39 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/news-8-0-39.html).

## Supplied components

Review each component’s release notes for What’s new, improvements, or bug fixes. The following is a list of the components supplied with the Percona Server for MySQL-based variation of the Percona Distribution for MySQL:

| Component           | Version   | Description                                |
| ------------------- | --------- | -------------------------------------------|
| Orchestrator        | [3.2.6-14](https://github.com/percona/orchestrator/releases/tag/v3.2.6-14)     | The replication topology manager for Percona Server for MySQL|
| ProxySQL            | [2.6.5](https://docs.percona.com/proxysql/2.6.5.html)     | A high performance, high-availability, protocol-aware proxy for MySQL|
| Percona XtraBackup  | [8.0.35-30](https://docs.percona.com/percona-xtrabackup/8.0/release-notes/8.0/8.0.35-30.0.html)| An open-source hot backup utility for MySQL-based servers|
| Percona Toolkit     | [3.6.0](https://docs.percona.com/percona-toolkit/release_notes.html#v3-6-0-released-2024-06-12)     | The set of scripts to simplify and optimize database operation|
| MySQL Shell         | [8.0.38](https://dev.mysql.com/doc/relnotes/mysql-shell/8.0/en/news-8-0-38.html)    | An advanced client and code editor for MySQL Server|
| MySQL Router        | [8.0.39](https://dev.mysql.com/doc/relnotes/mysql-router/8.0/en/news-8-0-39.html)    | Lightweight middleware that provides transparent routing between your application and back-end MySQL servers|
