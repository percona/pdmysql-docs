# Percona Distribution for MySQL 8.0.37 using Percona Server for MySQL Update (2024-08-06)

Percona Distribution for MySQL is the most stable, scalable, and secure open source MySQL distribution, with two download options: one based on Percona Server for MySQL and one based on Percona XtraDB Cluster. [Install Percona Distribution for MySQL](installing.md).

## Release highlights

This release enhances telemetry and provides a more comprehensive explanation of how the telemetry works, including new components, metrics files, and additional methods for disabling telemetry. Find more information in the [Telemetry on Percona Server for MySQL](https://docs.percona.com/percona-server/8.0/telemetry.html) document.

Improvements and bug fixes provided by Oracle for MySQL 8.0.37 and included in Percona Server for MySQL are the following:

* The redo log might not record a change in column order when using instant DDL, potentially leading to an inaccurate log replay during the recovery process. (Bug #35183686)

* Enhanced management of buffers has been implemented in deleting tablespaces to prevent a possible assertion failure. (Bug #35676106, Bug #36343647)

* Resolved an assertion failure associated with full-text indexes. (Bug #35836581)

Find the complete list of bug fixes and changes in the [MySQL 8.0.37 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/news-8-0-37.html).

## Deprecation

* [PS-8963](https://perconadev.atlassian.net/browse/PS-8963): The `SEQUENCE_TABLE()` function is deprecated and may be removed in a future release. We recommend that you use `PERCONA_SEQUENCE_TABLE()` instead. To maintain compatibility with existing third-party software, `SEQUENCE_TABLE` is no longer a reserved term and can be used as a regular identifier. Find more information in [PERCONA_SEQUENCE_TABLE(n) function](https://docs.percona.com/percona-server/8.0/percona-sequence-table.html)

## Packaging notes

Percona Server for MySQL 8.0.37-29 supports Ubuntu 24.04.

## Supplied components

Review each component’s release notes for What’s new, improvements, or bug fixes. The following is a list of the components supplied with the Percona Server for MySQL-based variation of the Percona Distribution for MySQL:

| Component           | Version   | Description                                |
| ------------------- | --------- | -------------------------------------------|
| Orchestrator        | [3.2.6-13](https://github.com/percona/orchestrator/releases/tag/v3.2.6-13)     | The replication topology manager for Percona Server for MySQL|
| ProxySQL            | [2.6.3](https://docs.percona.com/proxysql/2.6.3.html)     | A high performance, high-availability, protocol-aware proxy for MySQL|
| Percona XtraBackup  | [8.0.35-30](https://docs.percona.com/percona-xtrabackup/8.0/release-notes/8.0/8.0.35-30.0.html)| An open-source hot backup utility for MySQL-based servers|
| Percona Toolkit     | [3.6.0](https://docs.percona.com/percona-toolkit/release_notes.html#v3-6-0-released-2024-06-12)     | The set of scripts to simplify and optimize database operation|
| MySQL Shell         | [8.0.37](https://dev.mysql.com/doc/relnotes/mysql-shell/8.0/en/news-8-0-37.html)    | An advanced client and code editor for MySQL Server|
| MySQL Router        | [8.0.37](https://dev.mysql.com/doc/relnotes/mysql-router/8.0/en/news-8-0-37.html)    | Lightweight middleware that provides transparent routing between your application and back-end MySQL servers|

