# Percona Distribution for MySQL 8.4.11 using Percona Server for MySQL (2026-08-20)

Percona Distribution for MySQL is more than just a version of MySQL; it is a comprehensive solution that combines Percona Server for MySQL with additional tools to create a cohesive environment. This distribution is reliable, scalable, and secure, ensuring that all components have been tested to work seamlessly together. You can choose from two download options: one that uses Percona Server for MySQL and another that utilizes Percona XtraDB Cluster. Refer to [Install Percona Distribution for MySQL](installing.md).

This release is based on [Percona Server for MySQL 8.4.11-11](https://docs.percona.com/percona-server/8.4/release-notes/8.4.11-11.html) that includes all the features and bug fixes available in the [MySQL 8.4.11 Community Edition](https://dev.mysql.com/doc/relnotes/mysql/8.4/en/news-8-4-11.html) and enterprise-grade features developed by Percona.

## Release highlights

### Percona Server for MySQL 8.4.11-11

Percona Server for MySQL 8.4.11-11 introduces the following new features and improvements:

* Adds OpenID Connect (OIDC) authentication and authorization. Users can authenticate with Identity tokens issued by external Identity Providers (IDPs) instead of MySQL passwords. The OIDC plugin supports multiple IDPs, maps IDP groups to MySQL roles, supports proxy users based on group membership, and refreshes JSON Web Key Set (JWKS) signing keys at runtime. Find more information in [OpenID Connect authentication](https://docs.percona.com/percona-server/8.4/openid-connect-authentication.html) and in [Get started with OpenID Connect authentication](https://docs.percona.com/percona-server/8.4/quickstart-openid-connect.html).

* Improves InnoDB performance for workloads limited by Least Recently Used (LRU) flush speed. The improvements reduce LRU list mutex contention, restore dedicated LRU manager threads, optimize LRU scanning, and allow single-page flushing to proceed while an LRU batch flush is running.

* Improves InnoDB buffer pool initialization on NUMA-enabled systems by using multi-threaded memory allocation. The improvement reduces initialization time and can shorten server startup for instances with large buffer pools.

* Improves InnoDB performance for highly concurrent range-select workloads by reducing `BUF_BLOCK_MUTEX` contention when multiple threads access the same buffer pool page. The improvement increases throughput for read workloads that repeatedly access the same hot pages.

* Adds timestamps to the Group Communication System (GCS) debug trace file. The timestamps make large trace files easier to analyze and help correlate Group Replication communication events with other server activity.

### MySQL 8.4.11

Improvements and bug fixes introduced by Oracle for MySQL 8.4.11 and included in Percona Server for MySQL are the following:

* Fixed an issue that could cause an InnoDB deadlock during `B-tree` page merges while concurrent searches were running. (Bug #39129182)

* Fixed an issue where stricter InnoDB row-size validation could reject or generate warnings for table definitions accepted by earlier MySQL LTS releases. (Bug #120323, Bug #39249507)

* Fixed an issue that could produce incorrect values when adding an `AUTO_INCREMENT` column to an existing InnoDB table. (Bug #115136, Bug #37105825)

* Fixed an issue that could return incorrect results when a scalar subquery and its outer query referenced the same Common Table Expression (CTE). (Bug #120403, Bug #39321676)

* Fixed an issue that could cause some `LEFT JOIN` queries with OR conditions to perform full table scans instead of index range scans. (Bug #113288, Bug #36061036)

* Fixed an issue that could prevent the server from starting on Oracle Linux 9 or Red Hat Enterprise Linux 9 when `innodb_redo_log_encrypt=ON` was configured. (Bug #39181231)

* Fixed an issue that caused memory leaks in the `statement_digest()` and `statement_digest_text()` functions. (Bug #104115, Bug #33073320)

Find the complete list of bug fixes and changes in the [MySQL 8.4.11 release notes :octicons-link-external-16:](https://dev.mysql.com/doc/relnotes/mysql/8.4/en/news-8-4-11.html).

## Known issues and limitations

* Percona Distribution for MySQL 8.4.11 includes MySQL Shell 8.4.10. Starting with MySQL Shell 26.7, Oracle uses a single-version release model and has discontinued the MySQL Shell 8.4 and 9.7 release series. As a result, MySQL Shell 8.4.11 is not available. MySQL Shell 8.4.10 remains the latest release in the 8.4 series.
    
* In 8.4.x environments, the ProxySQL binlog reader can fail to initialize because it uses legacy commands, such as SHOW MASTER STATUS. Some internal counters also use outdated terminology. To address most terminology issues, enable the [terminology_use_previous](https://dev.mysql.com/doc/refman/8.4/en/replication-options-replica.html#sysvar_terminology_use_previous) system variable on the database server. This workaround addresses only terminology compatibility and may not fix all failures.

## Supplied components

Review each component’s release notes for What’s new, improvements, or bug fixes. The following is a list of the components supplied with the Percona Server for MySQL-based variation of the Percona Distribution for MySQL.

| Component           | Version   | Description                                |
| ------------------- | --------- | -------------------------------------------|
| Orchestrator        | [3.2.6-24](https://github.com/percona/orchestrator/releases/tag/v3.2.6-24)     | The replication topology manager for Percona Server for MySQL|
| ProxySQL            | [2.7.3](https://docs.percona.com/proxysql/2.7.3.html)     | A high performance, high-availability, protocol-aware proxy for MySQL|
| Percona Toolkit     | [3.7.1-3](https://docs.percona.com/percona-toolkit/release_notes.html#v3-7-1-3-released-2026-04-17)     | The set of scripts to simplify and optimize database operation. |
| Percona XtraBackup  | [8.4.0-6](https://docs.percona.com/percona-xtrabackup/8.4/release-notes/8.4.0-6.html)| An open-source hot backup utility for MySQL-based servers|
| MySQL Shell         | [8.4.10](https://dev.mysql.com/doc/relnotes/mysql-shell/8.4/en/news-8-4-10.html)    | An advanced client and code editor for MySQL Server|
| MySQL Router        | [8.4.11](https://dev.mysql.com/doc/relnotes/mysql-router/26.7/en/news-26-7-0.html)    | Lightweight middleware that provides transparent routing between your application and back-end MySQL servers|
