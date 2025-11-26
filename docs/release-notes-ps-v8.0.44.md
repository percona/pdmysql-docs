# Percona Distribution for MySQL 8.0.44 using Percona Server for MySQL (2025-12-01)

Percona Distribution for MySQL is the most stable, scalable, and secure open source MySQL distribution, with two download options: one based on Percona Server for MySQL and one based on Percona XtraDB Cluster. [Install Percona Distribution for MySQL](installing.md).

This release is based on [Percona Server for MySQL 8.0.44-35](https://docs.percona.com/percona-server/8.0/release-notes/8.0.44-35.html) that includes all the features and bug fixes available in the [MySQL 8.0.44 Community Edition](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/news-8-0-44.html) and enterprise-grade features developed by Percona.

## Release highlights

### Percona Server for MySQL 8.0.44-35

Announcement – Discontinuation of the Percona PRO Program

Percona has consolidated its build offerings. The Pro builds are no longer required, and all features have been merged into the main open source Community release.

### MySQL 8.0.44

Improvements and bug fixes provided by Oracle for MySQL 8.0.44 and included in Percona Server for MySQL are the following:

* Fixed an issue where parallel scan thread creation could fail, causing assertion failures when falling back to single-thread mode. (Bug #38325137)

* Fixed an issue where virtual index rollback could fail on 32-bit builds of MySQL Server under certain circumstances. (Bug #38167527)

* Fixed an issue where very large buffer pools could require excessive memory chunks per instance, potentially causing allocation failures. The allocation is now validated to ensure proper memory allocation. (Bug #37994397)

* Fixed an issue where assertion failures could occur due to data size and bounds mismatches during DDL file operations. (Bug #37882398)

* Fixed an issue related to modifying the internal Full-Text Search (FTS) configuration. (Bug #37792010)

* Fixed an issue related to virtual indexes. (Bug #37602657)

* Fixed an issue where confusing warning messages could appear when row sizes exceeded maximum allowed limits with `innodb_strict_mode=OFF`, such as during table selection or column dropping operations. Error messages have been improved for clarity. (Bug #37003342, Bug #36768046, Bug #36867372)

Find the complete list of bug fixes and changes in the [MySQL 8.0.44 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/news-8-0-44.html).

## Build & packaging notes

Amazon Linux 2023 is not supported in Percona Distribution for MySQL. We do support Amazon Linux 2023 in Percona Server for MySQL and Percona XtraBackup.

## Supplied components

Review each component’s release notes for What’s new, improvements, or bug fixes. The following is a list of the components supplied with the Percona Server for MySQL-based variation of the Percona Distribution for MySQL:

| Component           | Version   | Description                                |
| ------------------- | --------- | -------------------------------------------|
| Orchestrator        | [3.2.6-19](https://github.com/percona/orchestrator/releases/tag/v3.2.6-19)     | The replication topology manager for Percona Server for MySQL|
| ProxySQL            | [3.0.1](https://docs.percona.com/proxysql/3.0.1.html)     | A high performance, high-availability, protocol-aware proxy for MySQL|
| Percona XtraBackup  | [8.0.35-34](https://docs.percona.com/percona-xtrabackup/8.0/release-notes/8.0/8.0.35-34.0.html)| An open-source hot backup utility for MySQL-based servers|
| Percona Toolkit     | [3.7.0-2](https://docs.percona.com/percona-toolkit/release_notes.html#v3-7-0-2-released-2025-05-14)     | The set of scripts to simplify and optimize database operation|
| MySQL Shell         | [8.0.44](https://dev.mysql.com/doc/relnotes/mysql-shell/8.0/en/news-8-0-44.html)    | An advanced client and code editor for MySQL Server|
| MySQL Router        | [8.0.44](https://dev.mysql.com/doc/relnotes/mysql-router/8.0/en/news-8-0-44.html)    | Lightweight middleware that provides transparent routing between your application and back-end MySQL servers|
