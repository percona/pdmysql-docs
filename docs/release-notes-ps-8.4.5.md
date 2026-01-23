# Percona Distribution for MySQL 8.4.5 using Percona Server for MySQL (2025-05-29)

Percona Distribution for MySQL is more than just a version of MySQL; it is a comprehensive solution that combines Percona Server for MySQL with additional tools to create a cohesive environment. This distribution is reliable, scalable, and secure, ensuring that all components have been tested to work seamlessly together. You can choose from two download options: one that uses Percona Server for MySQL and another that utilizes Percona XtraDB Cluster. Refer to [Install Percona Distribution for MySQL](installing.md).

This release is based on [Percona Server for MySQL 8.4.5-5](https://docs.percona.com/percona-server/8.4/release-notes/8.4.5-5.html) that includes all the features and bug fixes available in the [MySQL 8.4.5 Community Edition](https://dev.mysql.com/doc/relnotes/mysql/8.4/en/news-8-4-5.html) and enterprise-grade features developed by Percona.

## Release highlights

### Percona Server for MySQL 8.4.5-5

* Updates the C++ level of the KMPI library to enhance error handling capabilities.

* Improves optimizer behavior by restoring correct handling of const tables in `test_quick_select()`. A MySQL Upstream refactor (commit [9a13c1c](https://github.com/percona/percona-server/commit/9a13c1c6971f4bd56d143179ecfb34cca8ecc018)) removed the `QEP_TAB` dependency, causing `get_quick_record_count()` to no longer pass const table information. This could lead to suboptimal range scan boundaries. The applied patch resolves the issue by explicitly passing `const_tables` to `test_quick_select()`, ensuring consistent behavior with the pre-refactor logic.

The latest MyRocks storage engine incorporates code based on RocksDB version 9.3.1. Percona has applied minor modifications to the original RocksDB codebase. Check the list of modifications at [https://github.com/percona/rocksdb/](https://github.com/percona/rocksdb/commit/2864cd95ca72bc4a2e93fe461dbd980f8e2357be).

This release adds the following changes to the list of [MyRocks variables](https://docs.percona.com/percona-server/8.4/myrocks-server-variables.html).

**Adds new MyRocks variables**

* [`--rocksdb_bulk_load_compression_parallel_threads`](https://docs.percona.com/percona-server/8.4/myrocks-server-variables.html#rocksdb_bulk_load_compression_parallel_threads)
* [`--rocksdb_bulk_load_enable_unique_key_check`](https://docs.percona.com/percona-server/8.4/myrocks-server-variables.html#rocksdb_bulk_load_enable_unique_key_check)
* [`--rocksdb_debug_skip_bloom_filter_check_on_iterator_bounds`](https://docs.percona.com/percona-server/8.4/myrocks-server-variables.html#rocksdb_debug_skip_bloom_filter_check_on_iterator_bounds)
* [`--rocksdb_enable_udt_in_mem`](https://docs.percona.com/percona-server/8.4/myrocks-server-variables.html#rocksdb_enable_udt_in_mem)
* [`--rocksdb_invalid_create_option_action`](https://docs.percona.com/percona-server/8.4/myrocks-server-variables.html#rocksdb_invalid_create_option_action)
* [`--rocksdb_io_error_action`](https://docs.percona.com/percona-server/8.4/myrocks-server-variables.html#rocksdb_io_error_action)
* [`--rocksdb_table_stats_skip_system_cf`](https://docs.percona.com/percona-server/8.4/myrocks-server-variables.html#rocksdb_table_stats_skip_system_cf)
* [`--rocksdb_use_io_uring`](https://docs.percona.com/percona-server/8.4/myrocks-server-variables.html#rocksdb_use_io_uring)
* [`--rocksdb_enable_instant_ddl`](https://docs.percona.com/percona-server/8.4/myrocks-server-variables.html#rocksdb_enable_instant_ddl)
* [`--rocksdb_enable_instant_ddl_for_append_column`](https://docs.percona.com/percona-server/8.4/myrocks-server-variables.html#rocksdb_enable_instant_ddl_for_append_column)
* [`--rocksdb_enable_instant_ddl_for_column_default_changes`](https://docs.percona.com/percona-server/8.4/myrocks-server-variables.html#rocksdb_enable_instant_ddl_for_column_default_changes)
* [`--rocksdb_enable_instant_ddl_for_drop_index_changes`](https://docs.percona.com/percona-server/8.4/myrocks-server-variables.html#rocksdb_enable_instant_ddl_for_drop_index_changes)
* [`--rocksdb_enable_instant_ddl_for_table_comment_changes`](https://docs.percona.com/percona-server/8.4/myrocks-server-variables.html#rocksdb_enable_instant_ddl_for_table_comment_changes)
* [`--rocksdb-bulk-load-compression-parallel-threads`](https://docs.percona.com/percona-server/8.4/myrocks-server-variables.html#rocksdb_bulk_load_compression_parallel_threads)
* [`--rocksdb-bulk-load-enable-unique-key-check`](https://docs.percona.com/percona-server/8.4/myrocks-server-variables.html#rocksdb_bulk_load_enable_unique_key_check)
* [`--rocksdb-debug-skip-bloom-filter-check-on-iterator-bounds`](https://docs.percona.com/percona-server/8.4/myrocks-server-variables.html#rocksdb_debug_skip_bloom_filter_check_on_iterator_bounds)

**Changes default values of MyRocks variables**

* [`--rocksdb_disable_instant_ddl`](https://docs.percona.com/percona-server/8.4/myrocks-server-variables.html#rocksdb_disable_instant_ddl) - the default value is changed from `ON` to `OFF`.

* [`--rocksdb_file_checksums`](https://docs.percona.com/percona-server/8.4/myrocks-server-variables.html#rocksdb_file_checksums) - the data type is changed from `Boolean` to `ENUM`. Also, the default value is changed from `OFF` to `CHECKSUMS_OFF`.

* [`--rocksdb_compaction_readahead_size`](https://docs.percona.com/percona-server/8.4/myrocks-server-variables.html#rocksdb_compaction_readahead_size) - the default value is changed from `0` (zero) to `2097152`.

**Deprecates MyRocks variable**

* [`--rocksdb_disable_instant_ddl`](https://docs.percona.com/percona-server/8.4/myrocks-server-variables.html#rocksdb_disable_instant_ddl) - this variable is being deprecated and is expected to be removed in a future release.

**Removes MyRocks variables**

* [`--rocksdb-access-hint-on-compaction-start`](https://docs.percona.com/percona-server/8.4/myrocks-server-variables.html#rocksdb_access_hint_on_compaction_start)
* [`--rocksdb_large_prefix`](https://docs.percona.com/percona-server/8.4/myrocks-server-variables.html#rocksdb_large_prefix)
* [`--rocksdb_strict_collation_check`](https://docs.percona.com/percona-server/8.4/myrocks-server-variables.html#rocksdb_strict_collation_check)
* [`--rocksdb_strict_collation_exceptions`](https://docs.percona.com/percona-server/8.4/myrocks-server-variables.html#rocksdb_strict_collation_exceptions)

### MySQL 8.4.5

Improvements and bug fixes introduced by Oracle for MySQL 8.4.5 and included in Percona Server for MySQL are the following:

* Fixed an issue where `CHECK TABLE` sometimes incorrectly reported that spatial indexes were corrupted. (Bug #37286473)

* Fixed an issue in InnoDB redo log recovery to improve data safety after a crash. (Bug #37061960)

* Fixed an issue where reading `index_id` values could lead to incorrect behavior with indexes. (Bug #36993445, Bug #37709706)

* Fixed a bug related to the `lower_case_table_names` setting that caused inconsistent behavior with table names on different systems. (Bug #32288105)

* Fixed a bug where `mysqldump` did not properly escape certain special characters in its output. (Bug #37540722, Bug #37709163)

* The `fprintf_string()` function in `mysqldump` did not use the correct quote character for escaping strings. (Bug #37607195)

Find the complete list of bug fixes and changes in the [MySQL 8.4.5 release notes](https://dev.mysql.com/doc/relnotes/mysql/8.4/en/news-8-4-5.html).

## Known issues
    
* In 8.4.x environments, the ProxySQL binlog reader can fail to initialize because it uses legacy commands, such as SHOW MASTER STATUS. Some internal counters also use outdated terminology. To address most terminology issues, enable the [terminology_use_previous](https://dev.mysql.com/doc/refman/8.4/en/replication-options-replica.html#sysvar_terminology_use_previous) system variable on the database server. This workaround addresses only terminology compatibility and may not fix all failures.

## Supplied components

Review each component’s release notes for What’s new, improvements, or bug fixes. The following is a list of the components supplied with the Percona Server for MySQL-based variation of the Percona Distribution for MySQL.

| Component           | Version   | Description                                |
| ------------------- | --------- | -------------------------------------------|
| Orchestrator        | [3.2.6-17](https://github.com/percona/orchestrator/releases/tag/v3.2.6-17)     | The replication topology manager for Percona Server for MySQL|
| ProxySQL            | [2.7.3](https://docs.percona.com/proxysql/2.7.3.html)     | A high performance, high-availability, protocol-aware proxy for MySQL|
| Percona Toolkit     | [3.7.0-2](https://docs.percona.com/percona-toolkit/release_notes.html#v3-7-0-2-released-2025-05-14)     | The set of scripts to simplify and optimize database operation. |
| Percona XtraBackup  | [8.4.0-3](https://docs.percona.com/percona-xtrabackup/8.4/release-notes/8.4.0-3.html)| An open-source hot backup utility for MySQL-based servers|
| MySQL Shell         | [8.4.5](https://dev.mysql.com/doc/relnotes/mysql-shell/8.4/en/news-8-4-5.html)    | An advanced client and code editor for MySQL Server|
| MySQL Router        | [8.4.5](https://dev.mysql.com/doc/relnotes/mysql-router/8.4/en/news-8-4-5.html)    | Lightweight middleware that provides transparent routing between your application and back-end MySQL servers|
