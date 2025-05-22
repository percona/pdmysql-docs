# Percona Distribution for MySQL 8.0.41 using Percona Server for MySQL (2025-02-26)

Percona Distribution for MySQL is the most stable, scalable, and secure open source MySQL distribution, with two download options: one based on Percona Server for MySQL and one based on Percona XtraDB Cluster. [Install Percona Distribution for MySQL](installing.md).

This release is based on [Percona Server for MySQL 8.0.41-32](https://docs.percona.com/percona-server/8.0/release-notes/8.0.41-32.html) that includes all the features and bug fixes available in the [MySQL 8.0.41 Community Edition](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/news-8-0-41.html) and enterprise-grade features developed by Percona.

## Release highlights

### Percona Server for MySQL 8.0.41-32

* Extends the [Encryption user-defined functions](https://docs.percona.com/percona-server/8.0/encryption-functions.html) with the following:

     * Added support for `pkcs1`, `oaep`, or `no` padding for RSA encrypt and decrypt operations

     * Added support for `pkcs1` or `pkcs1_pss` padding for RSA sign and verify operations

     * Added the `encryption_udf.legacy_padding_scheme` system variable to manage legacy padding schemes

     * Added the character set awareness

* Improves the [Data masking](https://docs.percona.com/percona-server/8.0/data-masking-overview.html) performance by introducing an internal term cache. The new cache speeds up lookups for `gen_blocklist()` and `gen_dictionary()` functions by storing dictionary data in memory.

    Find more detailed information in the [Data masking overview](https://docs.percona.com/percona-server/8.0/data-masking-overview.html) and in the [Data masking component functions](https://docs.percona.com/percona-server/8.0/data-masking-function-list.html).

### MySQL 8.0.41

Improvements and bug fixes provided by Oracle for MySQL 8.0.41 and included in Percona Server for MySQL are the following:

* Fixed an assertion in debug builds where certain IO buffer serializations caused system hangs. (Bug #37139618)

* Resolved a failure when dropping the primary key and adding a new `AUTO_INCREMENT` column as the primary key in descending order using the `INPLACE` algorithm resulted in failure. (Bug #36658450)

* Fixed incorrect results, including missing rows, in queries that used a descending primary key with the `index_merge` optimization. (Bug #106207, Bug #33767814)

* Addressed a replication channel issue where MySQL failed to stop the channel properly when large transactions were being processed, and `STOP REPLICA` was requested. This issue also prevented graceful server shutdown, requiring process termination or system restart. (Bug #115966, Bug #37008345)

Find the complete list of bug fixes and changes in the [MySQL 8.0.41 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/news-8-0-41.html).

## Supplied components

Review each component’s release notes for What’s new, improvements, or bug fixes. The following is a list of the components supplied with the Percona Server for MySQL-based variation of the Percona Distribution for MySQL:

| Component           | Version   | Description                                |
| ------------------- | --------- | -------------------------------------------|
| Orchestrator        | [3.2.6-16](https://github.com/percona/orchestrator/releases/tag/v3.2.6-16)     | The replication topology manager for Percona Server for MySQL|
| ProxySQL            | [2.7.1-1](https://docs.percona.com/proxysql/2.7.1-1.html)     | A high performance, high-availability, protocol-aware proxy for MySQL|
| Percona XtraBackup  | [8.0.35-32](https://docs.percona.com/percona-xtrabackup/8.0/release-notes/8.0/8.0.35-31.0.upd.html)| An open-source hot backup utility for MySQL-based servers|
| Percona Toolkit     | [3.7.0](https://docs.percona.com/percona-toolkit/release_notes.html#v3-7-0-released-2024-12-23)     | The set of scripts to simplify and optimize database operation|
| MySQL Shell         | [8.0.41](https://dev.mysql.com/doc/relnotes/mysql-shell/8.0/en/news-8-0-41.html)    | An advanced client and code editor for MySQL Server|
| MySQL Router        | [8.0.41](https://dev.mysql.com/doc/relnotes/mysql-router/8.0/en/news-8-0-41.html)    | Lightweight middleware that provides transparent routing between your application and back-end MySQL servers|
