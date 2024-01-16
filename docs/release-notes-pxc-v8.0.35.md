# Percona Distribution for MySQL 8.0.35 using Percona XtraDB Cluster (2024-01-17)

Percona Distribution for MySQL is the most stable, scalable and secure open-source MySQL distribution, with two download options: one based on Percona Server for MySQL and one based on Percona XtraDB Cluster. [Install Percona Distribution for MySQL](installing.md).

This release is focused on the Percona XtraDB Cluster-based deployment variation. It is based on [Percona XtraDB Cluster 8.0.35](https://docs.percona.com/percona-xtradb-cluster/8.0/release-notes/8.0.35-27.html)

## Release highlights

Improvements and bug fixes provided by Oracle for MySQL 8.0.35 and included in Percona Server for MySQL are the following:

* Upgraded the linked OpenSSL library to OpenSSL 3.0.10.
* Removed the printed query string limit to display the characters for a detected deadlock section of the engine status log.
* Fixed a procession of single-character tokens by an FTS parser plugin.

### Deprecations

A future release may remove deprecated variables and options. The usage of these deprecated items may cause a warning. We recommend migrating from deprecated variables and options as soon as possible.

This release deprecates the following variables and options:

* The `binlog_transaction_dependency_tracking` server system variable

* The `old` and `new` server system variables

* The `--character-set-client-handshake` server variable

* `INFORMATION_SCHEMA.PROCESSLIST` and the `SHOW PROCESSLIST` command

* The `performance_schema_show_processlist` variable

Find the full list of bug fixes and changes in the [MySQL 8.0.35 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/news-8-0-35.html).

## Supplied components

Review each component’s release notes for What’s new, improvements, or bug fixes. The following is a list of the components supplied with the Percona XtraDB Cluster-based variation of the Percona Distribution for MySQL:

| Component               | Version   | Description                                |
| ----------------------- | --------- | -------------------------------------------|
| Percona XtraBackup      | [8.0.35-30](https://docs.percona.com/percona-xtrabackup/8.0/release-notes/8.0/8.0.35-30.0.html)| An open-source hot backup utility for MySQL-based servers that doesn’t lock your database during the backup.|
| HAProxy                 | [2.8.5](https://git.haproxy.org/?p=haproxy-2.8.git;a=commit;h=aaba8d090ec663906af1fecbad83c26bbccf0761) | A high-availability and load-balancing solution for Percona XtraDB Cluster. This is a default proxy.|
| ProxySQL                | [2.5.5](https://docs.percona.com/proxysql/2.5.5.html)| A high performance, high-availability, protocol-aware proxy for MySQL.          |
| Percona Toolkit         | [3.5.7](https://docs.percona.com/percona-toolkit/release_notes.html#v3-5-7-released-2023-12-23)     | The set of scripts to simplify and optimize database operation. |
| relication_manager.sh   | [1.0](./replication-manager/replication-manager-for-pxc.md)  | A tool to manage multi-source replication between multiple Percona XtraDB Cluster clusters. |
