# Percona Distribution for MySQL 8.4.11 using Percona XtraDB Cluster (2026-10-05)

Percona Distribution for MySQL is more than just a version of MySQL; it is a comprehensive solution that combines Percona Server for MySQL with additional tools to create a cohesive environment. This distribution is reliable, scalable, and secure, ensuring that all components have been tested to work seamlessly together. You can choose from two download options: one that uses Percona Server for MySQL and another that utilizes Percona XtraDB Cluster. Refer to [Install Percona Distribution for MySQL](installing.md).

This release is based on [Percona XtraDB Cluster 8.4.11-11](https://docs.percona.com/percona-xtradb-cluster/8.4/release-notes/8.4.11-11.html).

!!! note "A note on MySQL 8.4.12"

    After a thorough review of the updates included in MySQL 8.4.12, Percona has decided not to release a corresponding Percona Server for MySQL 8.4.12. MySQL 8.4.12 is a Critical Security Patch Update (CSPU) — a targeted security release that Oracle can issue between quarterly Critical Patch Updates (CPUs) when needed. The fixes included in this CSPU do not affect Percona Server for MySQL.

## Release highlights

### Percona XtraDB Cluster 8.4.11-11

!!! note "Upgrade to 9.7"

    To upgrade from Percona XtraDB Cluster 8.4 to 9.7, use 9.7.2 or newer as the target version. Upgrading from 8.4.11 to 9.7.1 is not supported.

Percona XtraDB Cluster 8.4.11-11 introduces the following improvements:

* When `pxc_strict_mode` is set to `ENFORCING` or `MASTER`, Percona XtraDB Cluster now also enables `sql_require_primary_key` globally, so tables without a primary key can no longer be created or altered. Previously, you could create such a table but could not run DML statements on it. While `pxc_strict_mode` is `ENFORCING` or `MASTER`, setting `sql_require_primary_key` to `OFF` returns an error. The server applies the setting at startup and whenever `pxc_strict_mode` changes to one of these modes. Existing connections keep their current session value, and new connections use the updated global value.

* Adds the `repl.force_sst_after_inconsistency` Galera provider option. When the option is enabled and a node is voted out of the cluster because of a data inconsistency, the node removes the `grastate.dat` file on shutdown. On the next start, the node performs a full State Snapshot Transfer (SST) instead of an Incremental State Transfer (IST), which ensures a consistent dataset. The option is disabled by default and can be changed at runtime with `wsrep_provider_options`.

### Percona Server for MySQL 8.4.11-11

Percona Server for MySQL 8.4.11-11 introduces the following new features and improvements:

* Adds OpenID Connect (OIDC) authentication and authorization. Users can authenticate with Identity tokens issued by external Identity Providers (IDPs) instead of MySQL passwords. The OIDC plugin supports multiple IDPs, maps IDP groups to MySQL roles, supports proxy users based on group membership, and refreshes JSON Web Key Set (JWKS) signing keys at runtime. Find more information in [OpenID Connect authentication](https://docs.percona.com/percona-server/8.4/openid-connect-authentication.html) and in [Get started with OpenID Connect authentication](https://docs.percona.com/percona-server/8.4/quickstart-openid-connect.html).

* Improves InnoDB performance for workloads limited by Least Recently Used (LRU) flush speed. The improvements reduce LRU list mutex contention, restore dedicated LRU manager threads, optimize LRU scanning, and allow single-page flushing to proceed while an LRU batch flush is running.

* Improves InnoDB buffer pool initialization on NUMA-enabled systems by using multi-threaded memory allocation. The improvement reduces initialization time and can shorten server startup for instances with large buffer pools. Starting in 8.4.11, `innodb_numa_interleave` controls only interleaved NUMA allocations. Pre-faulting buffer pool pages on startup is controlled by `innodb_buffer_pool_populate`. Both default to `ON`, so default behavior matches 8.4.10. If you set `innodb_numa_interleave=OFF` to skip pre-faulting in 8.4.10, also set `innodb_buffer_pool_populate=OFF` in 8.4.11. See [Defaults and tuning guidance for 8.4](https://docs.percona.com/percona-server/8.4/8.4-defaults-and-tuning.html#numa-interleave-and-buffer-pool-populate).

* Improves InnoDB performance for highly concurrent range-select workloads by reducing `BUF_BLOCK_MUTEX` contention when multiple threads access the same buffer pool page. The improvement increases throughput for read workloads that repeatedly access the same hot pages.

* Adds timestamps to the Group Communication System (GCS) debug trace file. The timestamps make large trace files easier to analyze and help correlate Group Replication communication events with other server activity.

### MySQL 8.4.11

Improvements and bug fixes introduced by Oracle for MySQL 8.4.11 and included in Percona Server for MySQL are the following:

* Fixed an issue that could cause an InnoDB deadlock during `B-tree` page merges while concurrent searches were running. (Bug #39129182)

* Fixed an issue where stricter InnoDB row-size validation could reject or generate warnings for table definitions accepted by earlier MySQL LTS releases. (Bug #120323, Bug #39249507)

* Fixed an issue that could produce incorrect values when adding an `AUTO_INCREMENT` column to an existing InnoDB table. (Bug #115136, Bug #37105825)

* Fixed an issue that could return incorrect results when a scalar subquery and its outer query referenced the same Common Table Expression (CTE). (Bug #120403, Bug #39321676)

* Fixed an issue that could prevent the server from starting on Oracle Linux 9 or Red Hat Enterprise Linux 9 when `innodb_redo_log_encrypt=ON` was configured. (Bug #39181231)

Find the complete list of bug fixes and changes in the [MySQL 8.4.11 release notes](https://dev.mysql.com/doc/relnotes/mysql/8.4/en/news-8-4-11.html).

## Supplied components

Review each component’s release notes for What’s new, improvements, or bug fixes. The following is a list of the components supplied with the Percona XtraDB Cluster-based variation of the Percona Distribution for MySQL:

| Component               | Version   | Description                                |
| ----------------------- | --------- | -------------------------------------------|
| Percona XtraBackup      | [8.4.0-7](https://docs.percona.com/percona-xtrabackup/8.4/release-notes/8.4.0-7.html)| An open-source hot backup utility for MySQL-based servers that doesn’t lock your database during the backup.|
| HAProxy                 | [2.8.29](https://git.haproxy.org/?p=haproxy-2.8.git;a=commit;h=ee8cc4dcba99a3ddead42f0528c8a50333acfa9d) | A high-availability and load-balancing solution for Percona XtraDB Cluster. This is a default proxy.|
| ProxySQL                | [2.7.3](https://docs.percona.com/proxysql/2.7.3.html)| A high performance, high-availability, protocol-aware proxy for MySQL.          |
| Percona Toolkit         | [3.7.1-4](https://docs.percona.com/percona-toolkit/release_notes.html#v3-7-1-4-released-2026-07-02)     | The set of scripts to simplify and optimize database operation. |
| replication_manager.sh   | [1.0](https://docs.percona.com/percona-distribution-for-mysql/8.4/replication-manager-for-pxc.html)  | A tool to manage multi-source replication between multiple Percona XtraDB Cluster clusters. |
