# Percona Distribution for MySQL 8.1.0 using Percona Server for MySQL (2023-11-27)

Percona Distribution for MySQL is the most stable, scalable, and secure open source MySQL distribution based on Percona Server for MySQL. [Install Percona Distribution for MySQL](installing.md).

This release is based on [Percona Server for MySQL 8.1.0-1].

## Release highlights

Percona Server for MySQL implements telemetry that fills in the gaps in our understanding of how you use Percona Server for MySQL to improve our products. Participation in the anonymous program is optional. You can opt-out if you prefer not to share this information. Find more information in the [Telemetry on Percona Server fo MySQL](telemetry.md) document.

The following user-defined function (UDF) shared objects (so) are converted to components:

* The `data_masking` plugin converted into the `component_masking_functions` component
* The `binlogs_utils_udf` UDF shared object (.so) converted to the `component_binlog_utils` component
* The `percona-udf` UDF shared object (.so) converted to the `component_percona-udf` component

A user does not need to execute a separate `CREATE FUNCTION ... SONAME ...` statement for each function. Installing the components with the `INSTALL COMPONENT 'file://componenet_xxx` statement performs the auto-registration operations.

The `keyring_vault` plugin converted into the `component_keyring_vault` component. This conversion aligns the keyring_vault with the KMIP and KMS keyrings and supports "ALTER INSTANCE RELOAD KEYRING" to update the configuration automatically.

The `audit_log_filter` plugin converted to the `component_audit_log_filter` component. The following changes are also available:

* Adds the `mysql_event_tracking_parse` audit log event
* Reworked, optimized, and reorganized the audit event data members
* Data deduplication within the audit event data members

The current version of `percona-release` does not support the `setup` subcommand with the `pdps-8x-innovation` and `pdps-8.1.0` repositories. Use `percona-release enable` instead. The support of the `pdps-8x-innovation` and `pdps-8.1.0` repositories for the `setup` subcommand will be added in the next release of `percona-release`.

The PS 8.1.0 MTR suites are reorganized. The existing percona-specific MTR test cases are regrouped and put into separate test suites:

* component_encryption_udf
* percona
* percona_innodb

Improvements and bug fixes introduced by Oracle for MySQL 8.1 and included in Percona Server for MySQL are the following:

* The `EXPLAIN FORMAT=JSON` can output the data to a user variable.

* New messages written to the MySQL error log during shutdown:

    * Startup and shutdown log messages, including when the server was started with `--initialize`

    * Start and end of shutdown phases for plugins and components

    * Start-of-phase and end-of-phase messages for connection closing phases

    * The number and ID of threads still alive after being forcibly disconnected and potentially causing a wait


Find the full list of bug fixes and changes in the [MySQL 8.1 Release Notes].

## Deprecation or removal

* The `mysql_native_password` authentication plugin is deprecated and subject to removal in a future version.
* The TokuDB is removed. The following items are also removed:
    * Percona-TokuBackup submodule
    * PerconaFT submodule
    * TokuDB storage engine code
    * TokuDB MTR test suites
    * plugin/tokudb-backup-plugin
* The MyRocks ZenFS is removed. The following items are also removed:
    * zenfs submodule
    * libzdb submodule
    * RocksDB MTR changes are reverted
* Travis CI integration
* Supporting `readline` as a alternative to editline library is removed.
* The `audit_log` (audit version 1) plugin is removed
* The "include/ext" pre-C++17 compatibility headers are removed.
* The `keyring_vault` plugin is removed.
* The `data_masking` UDF shared object (.so) is removed.
* The `binlog_utils_udf` UDF shared object (.so) is removed.
* The `percona_udf` UDF shared object (.so) is removed.

## Platform support

* Percona Server for MySQL 8.1.0-1 is not supported on Ubuntu 18.04.

## Supplied components

Review each component’s release notes for What’s new, improvements, or bug fixes. The following is a list of the components supplied with the Percona Server for MySQL-based variation of the Percona Distribution for MySQL:

| Component           | Version   | Description                                |
| ------------------- | --------- | -------------------------------------------|
| Orchestrator        | [3.2.6-11](https://github.com/percona/orchestrator/releases/tag/v3.2.6-11)     | The replication topology manager for Percona Server for MySQL|
| ProxySQL            | [2.5.5](https://docs.percona.com/proxysql/2.5.5.html)     | A high performance, high-availability, protocol-aware proxy for MySQL|
| Percona XtraBackup  | [8.1.0](https://docs.percona.com/percona-xtrabackup/innovation-release/release-notes/8.1.0-1.html)| An open-source hot backup utility for MySQL-based servers|
| Percona Toolkit     | [3.5.5](https://docs.percona.com/percona-toolkit/release_notes.html#v3-5-5-released-2023-10-03)     | The set of scripts to simplify and optimize database operation|
| MySQL Shell         | [8.1.0](https://dev.mysql.com/doc/relnotes/mysql-shell/8.1/en/news-8-1-0.html)    | An advanced client and code editor for MySQL Server|
| MySQL Router        | [8.1.0](https://dev.mysql.com/doc/relnotes/mysql-router/8.1/en/news-8-1-0.html)    | Lightweight middleware that provides transparent routing between your application and back-end MySQL servers|

[MySQL 8.1 Release Notes]: https://dev.mysql.com/doc/relnotes/mysql/8.1/en/
[Percona Server for MySQL 8.1.0-1]: https://www.percona.com/doc/percona-server/innovation-release/release-notes/8.1.0-1.html