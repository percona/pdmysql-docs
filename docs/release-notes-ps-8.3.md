# Percona Distribution for MySQL 8.3.0 using Percona Server for MySQL (2024-04-16)

Percona Distribution for MySQL is the most stable, scalable, and secure open source MySQL distribution based on Percona Server for MySQL. [Install Percona Distribution for MySQL](installing.md).

This release is based on [Percona Server for MySQL 8.3.0-1].

## Release highlights

This release merges the MySQL 8.3 code base. Within this merge Percona introduces the following changes:

* Percona updates the Binary Log UDFs to make them compatible with new tagged GTIDs (Global Transaction Identifiers).

* [PS-9044](https://perconadev.atlassian.net/browse/PS-9044): Adds the following variables to MyRocks:

    * [`rocksdb_block_cache_numshardbits`](https://docs.percona.com/percona-server/innovation-release/myrocks-server-variables.html#rocksdb_block_cache_numshardbits)

    * [`rocksdb_check_iterate_bounds`](https://docs.percona.com/percona-server/innovation-release/myrocks-server-variables.html#rocksdb_check_iterate_bounds)

    * [`rocksdb_compact_lzero_now`](https://docs.percona.com/percona-server/innovation-release/myrocks-server-variables.html#rocksdb_compact_lzero_now)

    * [`rocksdb_file_checksums`](https://docs.percona.com/percona-server/innovation-release/myrocks-server-variables.html#rocksdb_file_checksums)

    * [`rocksdb_max_file_opening_threads`](https://docs.percona.com/percona-server/innovation-release/myrocks-server-variables.html#rocksdb_max_file_opening_threads)

    * [`rocksdb_partial_index_ignore_killed`](https://docs.percona.com/percona-server/innovation-release/myrocks-server-variables.html#rocksdb_partial_index_ignore_killed)

    Changs the default values for the following variables:

    * [`rocksdb_compaction_sequential_deletes`](https://docs.percona.com/percona-server/innovation-release/myrocks-server-variables.html#rocksdb_compaction_sequential_deletes) from 0 to 14999

    * [`rocksdb_compaction_sequential_deletes_count_sd`](https://docs.percona.com/percona-server/innovation-release/myrocks-server-variables.html#rocksdb_compaction_sequential_deletes_count_sd) from `OFF` to `ON`

    * [`rocksdb_compaction_sequential_deletes_window`](https://docs.percona.com/percona-server/innovation-release/myrocks-server-variables.html#rocksdb_compaction_sequential_deletes_window) from 0 to 15000

    * [`rocksdb_force_flush_memtable_now`](https://docs.percona.com/percona-server/innovation-release/myrocks-server-variables.html#rocksdb_force_flush_memtable_now) from `ON` to `OFF`

    * [`rocksdb_large_prefix`](https://docs.percona.com/percona-server/innovation-release/myrocks-server-variables.html#rocksdb_large_prefix) from `OFF` to `ON`

Improvements and bug fixes introduced by Oracle for MySQL 8.3 and included in Percona Server for MySQL are the following:

* Implements tagged GTIDs (Global Transaction Identifiers) to group related transactions. This helps enhance replication management and simplify tracking transaction dependencies.

* Adds the `explain_json_format_version` server system variable. This variable allows selection between two JSON output formats for `EXPLAIN FORMAT=JSON` statements. Version 1, the default, offers the linear format used in prior versions. Version 2 provides an access path-based format, ensuring better future MySQL Optimizer compatibility.

## Deprecation or removal

A future release may remove deprecated features, variables and options. The usage of these deprecated items may cause a warning. We recommend migrating from deprecated variables and options as soon as possible.

This release deprecates the following option:

* The [`rocksdb_large_prefix`](https://docs.percona.com/percona-server/innovation-release/myrocks-server-variables.html#rocksdb_large_prefix) is deprecated.

This release removes the following features, variables and options:

* The `FLUSH HOSTS` statement was deprecated in MySQL 8.0.23 and has been removed. To clear the host cache, use `TRUNCATE TABLE performance_schema.host_cache` or `mysqladmin flush-hosts`.

* The `--skip-host-cache` server option has been removed. Start the server with the `--host-cache-size=0` option instead.

* The `--character-set-client-handshake` and `--old-style-user-limits` server options.

* The usage of writesets for conflict checks when the row-based logging is in effect is restricted. If `binlog_transaction_dependency_tracking` is set to `WRITESET` or `WRITESET_SESSION`, the `binlog_format` must be `ROW`. The `MIXED` value is no longer supported.

* The [Multi-threaded LRU flusher](https://docs.percona.com/percona-server/innovation-release/xtradb-performance-improvements.html#multi-threaded-lru-flusher) feature is no longer supported.

* The `innodb_parallel_doublewrite_path` and `innodb_parallel_dblwr_encrypt` server options were deprecated in Percona Server 8.0.23 and have had no effect since that time. These options have now been removed.

Review the [MySQL 8.3 Release Notes] for detailed information and explore the new features!

## Supplied components

Review each component’s release notes for What’s new, improvements, or bug fixes. The following is a list of the components supplied with the Percona Server for MySQL-based variation of the Percona Distribution for MySQL:

| Component           | Version   | Description                                |
| ------------------- | --------- | -------------------------------------------|
| Orchestrator        | [3.2.6-12](https://github.com/percona/orchestrator/releases/tag/v3.2.6-12)     | The replication topology manager for Percona Server for MySQL|
| ProxySQL            | [2.5.5-1.2](https://docs.percona.com/proxysql/2.5.5-1.2.html)     | A high performance, high-availability, protocol-aware proxy for MySQL|
| Percona XtraBackup  | [8.3.0](https://docs.percona.com/percona-xtrabackup/innovation-release/release-notes/8.3.0-1.html)| An open-source hot backup utility for MySQL-based servers|
| Percona Toolkit     | [3.5.7](https://docs.percona.com/percona-toolkit/release_notes.html#v3-5-7-released-2023-12-23)     | The set of scripts to simplify and optimize database operation|
| MySQL Shell         | [8.3.0](https://dev.mysql.com/doc/relnotes/mysql-shell/8.3/en/news-8-3-0.html)    | An advanced client and code editor for MySQL Server|
| MySQL Router        | [8.3.0](https://dev.mysql.com/doc/relnotes/mysql-router/8.3/en/news-8-3-0.html)    | Lightweight middleware that provides transparent routing between your application and back-end MySQL servers|

[Percona Server for MySQL 8.3.0-1]: https://www.percona.com/doc/percona-server/innovation-release/release-notes/8.3.0-1.html
[MySQL 8.3 Release Notes]: https://dev.mysql.com/doc/relnotes/mysql/8.3/en/news-8-3-0.html

