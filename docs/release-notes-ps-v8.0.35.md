# Percona Distribution for MySQL 8.0.35 using Percona Server for MySQL (2023-12-27)

Percona Distribution for MySQL is the most stable, scalable, and secure open source MySQL distribution, with two download options: one based on Percona Server for MySQL and one based on Percona XtraDB Cluster. [Install Percona Distribution for MySQL](installing.md).

This release is focused on the Percona Server for MySQL-based deployment variation. It is based on [Percona Server for MySQL 8.0.35-27](https://www.percona.com/doc/percona-server/8.0/release-notes/8.0.35-27.html).

## Release highlights

Percona Server for MySQL implements telemetry that fills in the gaps in our understanding of how you use Percona Server to improve our products. Participation in the anonymous program is optional. You can opt-out if you prefer not to share this information. Find more information in the [Telemetry on Percona Server for MySQL](https://docs.percona.com/percona-server/8.0/telemetry.html) document.

This merge fixes the following issue:

* [PS-8849](https://jira.percona.com/browse/PS-8849): The server exited with the `Assertion failure: row0mysql.cc:218:len < 256 * 256 thread`.

Improvements and bug fixes provided by Oracle for MySQL 8.0.35 and included in Percona Server for MySQL are the following:

* Upgraded the linked OpenSSL library to OpenSSL 3.0.10.
* Removed the printed query string limit to display the characters for a detected deadlock section of the engine status log.
* Fixed a procession of single-character tokens by an FTS parser plugin.

### Deprecations

The following items are deprecated in this release and using any of these items may cause a warning:

* The `binlog_transaction_dependency_tracking` server system variable

* The `old` and `new` server system variables

* The `--character-set-client-handshake` server variable

* `INFORMATION_SCHEMA.PROCESSLIST` and the `SHOW PROCESSLIST` command

* The `performance_schema_show_processlist` variable

We recommend migrating from these items as soon as possible. They can be removed in a future release.

Find the full list of bug fixes and changes in the [MySQL 8.0.35 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/news-8-0-35.html).

## Supplied components

Review each component’s release notes for What’s new, improvements, or bug fixes. The following is a list of the components supplied with the Percona Server for MySQL-based variation of the Percona Distribution for MySQL:

| Component           | Version   | Description                                |
| ------------------- | --------- | -------------------------------------------|
| Orchestrator        | [3.2.6-11](https://github.com/percona/orchestrator/releases/tag/v3.2.6-11)     | The replication topology manager for Percona Server for MySQL|
| ProxySQL            | [2.5.5](https://docs.percona.com/proxysql/2.5.5.html)     | A high performance, high-availability, protocol-aware proxy for MySQL|
| Percona XtraBackup  | [8.0.35-30](https://docs.percona.com/percona-xtrabackup/8.0/release-notes/8.0/8.0.35-30.0.html)| An open-source hot backup utility for MySQL-based servers|
| Percona Toolkit     | [3.5.7](https://docs.percona.com/percona-toolkit/release_notes.html#v3-5-7-released-2023-12-22)     | The set of scripts to simplify and optimize database operation|
| MySQL Shell         | [8.0.35](https://dev.mysql.com/doc/relnotes/mysql-shell/8.0/en/news-8-0-35.html)    | An advanced client and code editor for MySQL Server|
| MySQL Router        | [8.0.35](https://dev.mysql.com/doc/relnotes/mysql-router/en/news-8-0-35.html)    | Lightweight middleware that provides transparent routing between your application and back-end MySQL servers|