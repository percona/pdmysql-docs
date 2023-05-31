# Percona Distribution for MySQL 8.0.33 using Percona Server for MySQL (2023-06-15)

| Release date         | June 15, 2023 |
| :--------------      | :--------------- |
| Install instructions | [Installing Percona Distribution for MySQL](installing.md)|

Percona Distribution for MySQL is the most stable, scalable, and secure open source MySQL distribution, with two download options: one based on Percona Server for MySQL and one based on Percona XtraDB Cluster.

This release is focused on the Percona Server for MySQL-based deployment variation. It is based on [Percona Server for MySQL 8.0.33-25](https://www.percona.com/doc/percona-server/8.0/release-notes/8.0.33-25.html).

## Release highlights

* This release adds the following MyRocks variables:

  * `rocksdb_bulk_load_use_sst_partitioner`

  * `rocksdb_use_hyper_clock_cache`

  * `rocksdb_converter_record_cached_length`

  * `rocksdb_alter_table_comment_inplace`

  * `rocksdb_charge_memory`

  * `rocksdb_column_default_value_as_expression`

  * `rocksdb_corrupt_data_action`

  * `rocksdb_disable_instant_ddl`

  * `rocksdb_enable_delete_range_for_drop_index`

  * `rocksdb_partial_index_blind_delete`

  * `rocksdb_protection_bytes_per_key`

  * `rocksdb_use_write_buffer_manager`

* This release adds a new MyRocks Information Schema Table `ROCKSDB_LIVE_FILES_METADATA`.

* This release removes `rocksdb_instant_ddl` variable. Use `rocksdb_disable_instant_ddl` instead. 

* This merge fixes the following issues:

  * [PS-8477](https://jira.percona.com/browse/PS-8477): The offline-mode persisted when doing `dba.rebootClusterFromCompleteOutage`. 

  * [PS-8699](https://jira.percona.com/browse/PS-8699): `ALTER INSTANCE RELOAD TLS` hung with many concurrent connection attempts. We have included the upstream fix and added our fix for this issue, which significantly reduces the chances that the issue will reoccur.

Improvements and bug fixes introduced by Oracle for MySQL 8.0.33 and included in Percona Server for MySQL are the following:

* The `INSTALL COMPONENT` includes the `SET` clause. The `SET` clause sets the values of component system variables when installing one or several components. This reduces the inconvenience and limitations associated with assigning variable values in other ways.

* The mysqlbinlog `--start-position` accepts values up to `18446744073709551615`. If the `--read-from-remote-server` or `--read-from-remote-source` option is used, the maximum is `4294967295`. (Bug #77818, Bug #21498994)

* Using a generated column with `DEFAULT(col_name)` to specify the default value for a named column is not allowed and throws an error message. (Bug #34463652, Bug #34369580)

* Not all possible error states were reported during the binary log recovery process. (Bug #33658850)

* User-defined collations are deprecated. The usage of the following user-defined collations causes a warning that is written to the log:

  * When `COLLATE` is followed by the name of a user-defined collation in an SQL statement.

  * When the name of a user-defined collation is used as the value of `collation_server`, `collation_database`, or `collation_connection`.

The support for user-defined collations will be removed in a future releases of MySQL.

Find the full list of bug fixes and changes in the [MySQL 8.0.33 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/news-8-0-33.html).

## Supplied components

Review each component’s release notes for What’s new, improvements, or bug fixes. The following is a list of the components supplied with the Percona Server for MySQL-based variation of the Percona Distribution for MySQL:

| Component           | Version   | Description                                |
| ------------------- | --------- | -------------------------------------------|
| Orchestrator        | [3.2.6-9](https://github.com/percona/orchestrator/releases/tag/v3.2.6-9)     | The replication topology manager for Percona Server for MySQL|
| ProxySQL            | [2.5.1](https://docs.percona.com/proxysql/2.5.1.html)     | A high performance, high-availability, protocol-aware proxy for MySQL|
| Percona XtraBackup  | [8.0.33-27](https://docs.percona.com/percona-xtrabackup/8.0/release-notes/8.0/8.0.33-27.0.html)| An open-source hot backup utility for MySQL-based servers|
| Percona Toolkit     | [3.5.3](https://www.percona.com/doc/percona-toolkit/LATEST/release_notes.html#v3-5-3-released-2023-06-07)     | The set of scripts to simplify and optimize database operation|
| MySQL Shell         | [8.0.33](https://dev.mysql.com/doc/relnotes/mysql-shell/8.0/en/news-8-0-33.html)    | An advanced client and code editor for MySQL Server|
| MySQL Router        | [8.0.33](https://dev.mysql.com/doc/relnotes/mysql-router/en/news-8-0-33.html)    | Lightweight middleware that provides transparent routing between your application and back-end MySQL servers|
