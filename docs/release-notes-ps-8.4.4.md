# Percona Distribution for MySQL 8.4.4 using Percona Server for MySQL (2025-03-18)

Percona Distribution for MySQL is more than just a version of MySQL; it is a comprehensive solution that combines Percona Server for MySQL with additional tools to create a cohesive environment. This distribution is reliable, scalable, and secure, ensuring that all components have been tested to work seamlessly together. You can choose from two download options: one that uses Percona Server for MySQL and another that utilizes Percona XtraDB Cluster. Refer to [Install Percona Distribution for MySQL](installing.md).

This release is based on [Percona Server for MySQL 8.4.4-4](https://docs.percona.com/percona-server/8.4/release-notes/8.4.4-4.html) that includes all the features and bug fixes available in the [MySQL 8.4.4 Community Edition](https://dev.mysql.com/doc/relnotes/mysql/8.4/en/news-8-4-4.html) and enterprise-grade features developed by Percona.

## Release highlights

### Percona Server for MySQL 8.4.4-4

* Improves the [Data masking](https://docs.percona.com/percona-server/8.4/data-masking-overview.html) performance by introducing an internal term cache. The new cache speeds up lookups for `gen_blocklist()` and `gen_dictionary()` functions by storing dictionary data in memory. However, if the dictionary table is modified directly (outside of the proper functions), the cache may become out of sync. To fix this, use the `new masking_dictionaries_flush()` function.

    Changes also affect row-based replication: dictionary changes on the source server are replicated, but the term cache on the replica doesn’t update immediately. To address this, a new system variable, `component_masking_functions.dictionaries_flush_interval_seconds`, can be set to automatically refresh the cache at specified intervals, helping replicas stay in sync.

    Find more detailed information in the [Data masking overview](https://docs.percona.com/percona-server/8.4/data-masking-overview.html) and in the [Data masking component functions](https://docs.percona.com/percona-server/8.4/data-masking-function-list.html).

* Improves the behavior of `audit_log_filter_set_user` to support wildcards in the hostname.

### MySQL 8.4.4

Improvements and bug fixes introduced by Oracle for MySQL 8.4.4 and included in Percona Server for MySQL are the following:

* Fixed an assertion in debug builds where certain IO buffer serializations caused system hangs. (Bug #37139618)

* Resolved a failure when dropping the primary key and adding a new `AUTO_INCREMENT` column as the primary key in descending order using the `INPLACE` algorithm resulted in failure. (Bug #36658450)

* Fixed incorrect results, including missing rows, in queries that used a descending primary key with the `index_merge` optimization. (Bug #106207, Bug #33767814)

* Addressed a replication channel issue where MySQL failed to stop the channel properly when large transactions were being processed, and `STOP REPLICA` was requested. This issue also prevented graceful server shutdown, requiring process termination or system restart. (Bug #115966, Bug #37008345)

Find the complete list of bug fixes and changes in the [MySQL 8.4.4 release notes](https://dev.mysql.com/doc/relnotes/mysql/8.4/en/news-8-4-4.html).

## Known issues
    
* In 8.4.x environments, the ProxySQL binlog reader can fail to initialize because it uses legacy commands, such as SHOW MASTER STATUS. Some internal counters also use outdated terminology. To address most terminology issues, enable the [terminology_use_previous](https://dev.mysql.com/doc/refman/8.4/en/replication-options-replica.html#sysvar_terminology_use_previous) system variable on the database server. This workaround addresses only terminology compatibility and may not fix all failures.

## Supplied components

Review each component’s release notes for What’s new, improvements, or bug fixes. The following is a list of the components supplied with the Percona Server for MySQL-based variation of the Percona Distribution for MySQL.

| Component           | Version   | Description                                |
| ------------------- | --------- | -------------------------------------------|
| Orchestrator        | [3.2.6-16](https://github.com/percona/orchestrator/releases/tag/v3.2.6-16)     | The replication topology manager for Percona Server for MySQL|
| ProxySQL            | [2.7.1-1](https://docs.percona.com/proxysql/2.7.1-1.html)     | A high performance, high-availability, protocol-aware proxy for MySQL|
| Percona Toolkit     | [3.7.0](https://docs.percona.com/percona-toolkit/release_notes.html#v3-7-0-released-2024-12-23)     | The set of scripts to simplify and optimize database operation. |
| Percona XtraBackup  | [8.4.0-2](https://docs.percona.com/percona-xtrabackup/8.4/release-notes/8.4.0-2.html)| An open-source hot backup utility for MySQL-based servers|
| MySQL Shell         | [8.4.4](https://dev.mysql.com/doc/relnotes/mysql-shell/8.4/en/news-8-4-4.html)    | An advanced client and code editor for MySQL Server|
| MySQL Router        | [8.4.4](https://dev.mysql.com/doc/relnotes/mysql-router/8.4/en/news-8-4-4.html)    | Lightweight middleware that provides transparent routing between your application and back-end MySQL servers|
