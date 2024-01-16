# Percona Distribution for MySQL 8.2.0 using Percona Server for MySQL (2024-01-)

Percona Distribution for MySQL is the most stable, scalable, and secure open source MySQL distribution based on Percona Server for MySQL. [Install Percona Distribution for MySQL](installing.md).

This release is based on [Percona Server for MySQL 8.2.0-1].

## Release highlights

Improvements and bug fixes introduced by Oracle for MySQL 8.2 and included in Percona Server for MySQL are the following:

* The insert operations caused `records_in_range` to read too many disk blocks.

* System schema tables with INSTANT ADD columns created before 8.0.29 are incompatible with MySQL versions higher than 8.0.29. Performing DMLs on these tables causes an unexpected server exit.

* A FTS parser plugin now handles single character tokens correctly.

### Deprecation or removal

A future release may remove deprecated variables and options. The usage of these deprecated items may cause a warning. We recommend migrating from deprecated variables and options as soon as possible.

This release deprecates the following variables and options:

* The `binlog_transaction_dependency_tracking` server system variable

* The `old` and `new` server system variables

* The `--character-set-client-handshake` server variable

* `INFORMATION_SCHEMA.PROCESSLIST`

* The implementation of the `SHOW PROCESSLIST` command that uses the `INFORMATION_SCHEMA.PROCESSLIST` table

* The `performance_schema_show_processlist` variable

This release removes the following variables and options:

* The `WAIT_UNTIL_SQL_THREAD_AFTER_GTIDS()` SQL function. Attempting to invoke this function now causes a syntax error. Use `WAIT_FOR_EXECUTED_GTID_SET()` instead.

* The `--abort-slave-event-count` and `--disconnect-slave-event-count` server startup options. Attempting to use these options now results in an error.

* The `expire_logs_days` server system variable. Attempting to use this variable now results in an error. Use the `binlog_expire_logs_seconds` variable instead.

Find the full list of bug fixes and changes in the [MySQL 8.2 Release Notes].

## Supplied components

Review each component’s release notes for What’s new, improvements, or bug fixes. The following is a list of the components supplied with the Percona Server for MySQL-based variation of the Percona Distribution for MySQL:

| Component           | Version   | Description                                |
| ------------------- | --------- | -------------------------------------------|
| Orchestrator        | [3.2.6-11](https://github.com/percona/orchestrator/releases/tag/v3.2.6-11)     | The replication topology manager for Percona Server for MySQL|
| ProxySQL            | [2.5.5](https://docs.percona.com/proxysql/2.5.5.html)     | A high performance, high-availability, protocol-aware proxy for MySQL|
| Percona XtraBackup  | [8.2.0](https://docs.percona.com/percona-xtrabackup/innovation-release/release-notes/8.2.0-1.html)| An open-source hot backup utility for MySQL-based servers|
| Percona Toolkit     | [3.5.7](https://docs.percona.com/percona-toolkit/release_notes.html#v3-5-7-released-2023-12-23)     | The set of scripts to simplify and optimize database operation|
| MySQL Shell         | [8.2.0](https://dev.mysql.com/doc/relnotes/mysql-shell/8.2/en/news-8-2-0.html)    | An advanced client and code editor for MySQL Server|
| MySQL Router        | [8.2.0](https://dev.mysql.com/doc/relnotes/mysql-router/8.2/en/news-8-2-0.html)    | Lightweight middleware that provides transparent routing between your application and back-end MySQL servers|

[Percona Server for MySQL 8.2.0-1]: https://www.percona.com/doc/percona-server/innovation-release/release-notes/8.2.0-1.html
[MySQL 8.2 Release Notes]: https://dev.mysql.com/doc/relnotes/mysql/8.2/en/news-8-2-0.html

