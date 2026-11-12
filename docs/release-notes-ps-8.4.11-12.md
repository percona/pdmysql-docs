# Percona Distribution for MySQL 8.4.11-12 using Percona Server for MySQL (2026-11-12)

Percona Distribution for MySQL is more than just a version of MySQL; it is a comprehensive solution that combines Percona Server for MySQL with additional tools to create a cohesive environment. This distribution is reliable, scalable, and secure, ensuring that all components have been tested to work seamlessly together. You can choose from two download options: one that uses Percona Server for MySQL and another that utilizes Percona XtraDB Cluster. Refer to [Install Percona Distribution for MySQL](installing.md).

This release is based on [Percona Server for MySQL 8.4.11-12](https://docs.percona.com/percona-server/8.4/release-notes/8.4.11-12.html) that includes all the features and bug fixes available in the [MySQL 8.4.11 Community Edition](https://dev.mysql.com/doc/relnotes/mysql/8.4/en/news-8-4-11.html) and enterprise-grade features developed by Percona.

!!! note "A note on MySQL 8.4.12"

    Percona Distribution for MySQL 8.4.11-12 is not based on the MySQL 8.4.12 release. MySQL 8.4.12 is a Critical Security Patch Update (CSPU) — a targeted security release that Oracle can issue between quarterly Critical Patch Updates (CPUs) when needed. The MySQL 8.4.12 CSPU applies to the MySQL Server Docker image only, and its fixes do not affect Percona Server for MySQL.

## Release highlights

### Percona Server for MySQL 8.4.11-12

Percona Server for MySQL 8.4.11-12 includes the following bug fix:

* [PS-11950](https://perconadev.atlassian.net/browse/PS-11950): `mysqldump` did not always dump tables with compressed columns correctly. If a column comment or another quoted string in the table definition contained text that looked like a compressed column attribute, `mysqldump` changed the table definition in the dump, so it was different from the original table. `mysqldump` also did not correctly dump or restore some compression dictionaries, such as dictionaries with names containing quotes, spaces, reserved words or non-ASCII characters, or with non-ASCII data.

## Supplied components

Review each component’s release notes for What’s new, improvements, or bug fixes. The following is a list of the components supplied with the Percona Server for MySQL-based variation of the Percona Distribution for MySQL.

| Component           | Version   | Description                                |
| ------------------- | --------- | -------------------------------------------|
| Orchestrator        | [3.2.6-24](https://github.com/percona/orchestrator/releases/tag/v3.2.6-24)     | The replication topology manager for Percona Server for MySQL|
| ProxySQL            | [2.7.3](https://docs.percona.com/proxysql/2.7.3.html)     | A high performance, high-availability, protocol-aware proxy for MySQL|
| Percona Toolkit     | [3.7.1-3](https://docs.percona.com/percona-toolkit/release_notes.html#v3-7-1-3-released-2026-04-17)     | The set of scripts to simplify and optimize database operation. |
| Percona XtraBackup  | [8.4.0-6](https://docs.percona.com/percona-xtrabackup/8.4/release-notes/8.4.0-6.html)| An open-source hot backup utility for MySQL-based servers|
| MySQL Shell         | [8.4.10](https://dev.mysql.com/doc/relnotes/mysql-shell/8.4/en/news-8-4-10.html)    | An advanced client and code editor for MySQL Server|
| MySQL Router        | [8.4.11](https://dev.mysql.com/doc/relnotes/mysql-router/26.7/en/news-26-7-0.html)    | Lightweight middleware that provides transparent routing between your application and back-end MySQL servers|
