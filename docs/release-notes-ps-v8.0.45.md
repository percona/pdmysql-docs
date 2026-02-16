# Percona Distribution for MySQL 8.0.45 using Percona Server for MySQL (2026-02-17)

Percona Distribution for MySQL is the most stable, scalable, and secure open source MySQL distribution, with two download options: one based on Percona Server for MySQL and one based on Percona XtraDB Cluster. [Install Percona Distribution for MySQL](installing.md).

This release is based on [Percona Server for MySQL 8.0.45-36](https://docs.percona.com/percona-server/8.0/release-notes/8.0.45-36.html) that includes all the features and bug fixes available in the [MySQL 8.0.45 Community Edition](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/news-8-0-45.html) and enterprise-grade features developed by Percona.

## Release highlights

### MySQL 8.0.45

Improvements and bug fixes provided by Oracle for MySQL 8.0.45 and included in Percona Server for MySQL are the following:

* The warning associated with redo logging being disabled is no longer present, as the underlying condition that triggered the warning has been eliminated. (Bug #37645185)

* A problem affecting the handling of large insert operations has been corrected, improving stability during bulk data loads. (Bug #38208188)

* An error that could arise when running certain SQL statements has been resolved. (Bug #38573285)

* Issues encountered when generating table definitions via `SHOW CREATE TABLE` have been fixed. (Bug #38448700)

* Bug #38298692 was addressed as part of the same fix set as Bug #38448700, resolving related inconsistencies in table metadata handling. (Bug #38298692)

* Performance regressions affecting queries that rely on regular expression matching have been corrected. (Bug #114056, Bug #36326728)

* The bundled OpenSSL dependency has been updated, addressing the issue tracked under Bug #38632932. (Bug #38632932)

* A concurrency flaw in InnoDB that could occur when executing SQL through the `que_eval_sql` interface has been removed. (Bug #118705, Bug #38310595)

* A timing issue that allowed binary logs to be removed before persisted expiration settings were fully applied has been fixed. (Bug #38554467)

* A fault affecting clustered environments, where multiple instances could lose connectivity under specific conditions, has been corrected. (Bug #38380392)

* Several defects that prevented connections from closing properly when using the Thread Pool have been resolved. (Bug #38170188, Bug #36782728, Bug #38549372)

* An issue that caused gaps in GTID sequences when the `replica_skip_errors` option was enabled has been fixed. (Bug #28590993)

Find the complete list of bug fixes and changes in the [MySQL 8.0.45 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/news-8-0-45.html).

## Supplied components

Review each component’s release notes for What’s new, improvements, or bug fixes. The following is a list of the components supplied with the Percona Server for MySQL-based variation of the Percona Distribution for MySQL:

| Component           | Version   | Description                                |
| ------------------- | --------- | -------------------------------------------|
| Orchestrator        | [3.2.6-19](https://github.com/percona/orchestrator/releases/tag/v3.2.6-19)     | The replication topology manager for Percona Server for MySQL|
| ProxySQL            | [2.7.3](https://docs.percona.com/proxysql/2.7.3.html)     | A high performance, high-availability, protocol-aware proxy for MySQL|
| Percona XtraBackup  | [8.0.35-35](https://docs.percona.com/percona-xtrabackup/8.0/release-notes/8.0/8.0.35-35.0.html)| An open-source hot backup utility for MySQL-based servers|
| Percona Toolkit     | [3.7.1](https://docs.percona.com/percona-toolkit/release_notes.html#v3-7-1-released-2025-12-17)     | The set of scripts to simplify and optimize database operation|
| MySQL Shell         | [8.0.45](https://dev.mysql.com/doc/relnotes/mysql-shell/8.0/en/news-8-0-45.html)    | An advanced client and code editor for MySQL Server|
| MySQL Router        | [8.0.45](https://dev.mysql.com/doc/relnotes/mysql-router/8.0/en/news-8-0-45.html)    | Lightweight middleware that provides transparent routing between your application and back-end MySQL servers|
