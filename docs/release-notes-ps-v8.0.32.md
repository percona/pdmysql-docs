# Percona Distribution for MySQL 8.0.32 using Percona Server for MySQL (2023-03-20)

| Release date         | March 20, 2023 |
| :--------------      | :--------------- |
| Install instructions | [Installing Percona Distribution for MySQL](installing.md)|

Percona Distribution for MySQL is the most stable, scalable, and secure open-source MySQL distribution, with two download options: one based on Percona Server for MySQL and one based on Percona XtraDB Cluster.

This release is focused on the Percona Server for MySQL-based deployment variation. It is based on [Percona Server for MySQL 8.0.32-24](https://www.percona.com/doc/percona-server/8.0/release-notes/8.0.32-24.html).

## Release highlights

Percona decided to revert the following MySQL bug fix:

The data and the GTIDs backed up by mysqldump were inconsistent when the options `--single-transaction` and `--set-gtid-purged=ON` were both used. It was because in between the transaction started by mysqldump and the fetching of `GTID_EXECUTED`, GTIDs on the server could have increased already. With this fixed, a `FLUSH TABLES WITH READ LOCK` is performed before the fetching of `GTID_EXECUTED` to ensure its value is consistent with the snapshot taken by `mysqldump`.

The MySQL fix also added a requirement when using [--single-transaction](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_single-transaction) and executing FLUSH TABLES WITH READ LOCK for the [RELOAD](https://dev.mysql.com/doc/refman/8.0/en/privileges-provided.html#priv_reload) privilege. (Bug #33630199, Bug #105761)

The current Percona decision also provides a solution for [MySQL bug #33630199](https://bugs.mysql.com/bug.php?id=109701). 

The Percona Server version of the `mysqldump` utility, in some modes, can be used with MySQL Server. This utility provides a temporary workaround for the `additional RELOAD privilege` limitation introduced by Oracle MySQL Server 8.0.32.

Improvements and bug fixes introduced by Oracle for MySQL 8.0.32 and included in Percona Server for MySQL are the following:

* A replica can add a Generated Invisible Primary Keys(GIPK) to any InnoDB table. To achieve this behavior, the `GENERATE` value is added as a possible value for the `CHANGE REPLICATION SOURCE TO` statement’s `REQUIRE_TABLE_PRIMARY_KEY_CHECK` option.

* The `REQUIRE_TABLE_PRIMARY_KEY_CHECK = GENERATE` option can be used on a per-channel basis.

* Setting `sql_generate_invisible_primary_key` on the source is ignored by a replica because this variable is not replicated. This behavior is inherited from the previous releases.

* An upgrade from 8.0.28 caused undetectable problems, such as server exit and corruption.

* A fix for after an upgrade, all columns added with `ALGORITHM=INSTANT` materialized and have version=0 for any new row inserted. Now, a column added with `ALGORITHM=INSTANT` fails if the maximum possible size of a row exceeds the row size limit so that all new rows with materialized `ALGORITHM=INSTANT` columns are within the row size limit. (Bug #34558510)

* After a drop, adding a specific column using the `INSTANT` algorithm could cause a data error and a server exit. (Bug #34122122)

* An online rebuild DDL no longer crashes after a column is added with `ALGORITHM=INSTANT`. Thank you, Qingda Hu, for reporting this bug. (Bug #33788578, Bug #106279)

Find the full list of bug fixes and changes in the [MySQL 8.0.32 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/news-8-0-32.html).

## Supplied components

Review each component’s release notes for What’s new, improvements, or bug fixes. The following is a list of the components supplied with the Percona Server for MySQL-based variation of the Percona Distribution for MySQL:

| Component           | Version   | Description                                |
| ------------------- | --------- | -------------------------------------------|
| Orchestrator        | [3.2.6-8](https://github.com/percona/orchestrator/releases/tag/v3.2.6-8)     | The replication topology manager for Percona Server for MySQL|
| ProxySQL            | [2.4.8](https://docs.percona.com/proxysql/2.4.8.html)     | A high performance, high-availability, protocol-aware proxy for MySQL|
| Percona XtraBackup  | [8.0.32-25](https://docs.percona.com/percona-xtrabackup/8.0/release-notes/8.0/8.0.32-25.0.html)| An open-source hot backup utility for MySQL-based servers|
| Percona Toolkit     | [3.5.1](https://www.percona.com/doc/percona-toolkit/LATEST/release_notes.html#v3-5-1-released-2022-11-28)     | The set of scripts to simplify and optimize database operation|
| MySQL Shell         | [8.0.32](https://dev.mysql.com/doc/relnotes/mysql-shell/8.0/en/news-8-0-32.html)    | An advanced client and code editor for MySQL Server|
| MySQL Router        | [8.0.32](https://dev.mysql.com/doc/relnotes/mysql-router/en/news-8-0-32.html)    | Lightweight middleware that provides transparent routing between your application and back-end MySQL servers|
