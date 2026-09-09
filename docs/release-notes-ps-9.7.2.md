# Percona Distribution for MySQL 9.7.2 using Percona Server for MySQL (2026-09-0)

Percona Distribution for MySQL is more than just a version of MySQL; it is a comprehensive solution that combines Percona Server for MySQL with additional tools to create a cohesive environment. This distribution is reliable, scalable, and secure, ensuring that all components have been tested to work seamlessly together. You can choose from two download options: one that uses Percona Server for MySQL and another that utilizes Percona XtraDB Cluster. Refer to [Install Percona Distribution for MySQL](installing.md).

!!! note "A note on MySQL 9.7.3"

    After a thorough review of the updates included in MySQL 9.7.3, Percona has decided not to release a corresponding Percona Server for MySQL 9.7.3. MySQL 9.7.3 is a Critical Security Patch Update (CSPU) — a targeted security release that Oracle can issue between quarterly Critical Patch Updates (CPUs) when needed. The fixes included in this CSPU do not affect Percona Server for MySQL.

This release is based on [Percona Server for MySQL 9.7.2-2](https://docs.percona.com/percona-server/9.7/release-notes/9.7.2-2.html) that includes all the features and bug fixes available in the [MySQL 9.7.2 Community Edition](https://dev.mysql.com/doc/relnotes/mysql/9.7/en/news-9-7-2.html) and enterprise-grade features developed by Percona.

## Release highlights

### Percona Server for MySQL 9.7.2-2

Percona Server for MySQL 9.7.2-2 introduces the following features and improvements:

* Adds OpenID Connect (OIDC) authentication and authorization. Users can authenticate with Identity tokens issued by external Identity Providers (IDPs) instead of MySQL passwords. The OIDC plugin supports multiple IDPs, maps IDP groups to MySQL roles, supports proxy users based on group membership, and refreshes JSON Web Key Set (JWKS) signing keys at runtime. Find more information in [OpenID Connect authentication](https://docs.percona.com/percona-server/9.7/openid-connect-authentication.html) and in [Get started with OpenID Connect authentication](https://docs.percona.com/percona-server/9.7/quickstart-openid-connect.html).

* Adds SQL functions for calculating the distance between vector values. Applications can use these functions to measure vector similarity and support search, recommendation, and other vector-based workloads. Find more information in [DISTANCE() Function](https://docs.percona.com/percona-server/9.7/distance-function.html).

* Improves InnoDB performance for highly concurrent range-select workloads by reducing page-level mutex contention when multiple sessions access the same buffer pool pages.

* Adds timestamps to Group Replication communication debug traces, making it easier to identify, sequence, and correlate events in large `GCS_DEBUG_TRACE` files.

* Improves validation and error logging for JSON-based OIDC configuration files. Invalid configuration sections are no longer silently ignored, and the server log provides clearer information for diagnosing configuration problems.

* Improves InnoDB performance for I/O-intensive workloads by reducing the time the buffer pool Least Recently Used (LRU) list mutex is held during physical page reads, decreasing serialization and improving scalability.

* Improves InnoDB Least Recently Used (LRU) flushing performance by restoring a dedicated LRU manager thread for each buffer pool instance and moving LRU flushing work away from page cleaner threads.

* Improves InnoDB Least Recently Used (LRU) flushing efficiency by correcting the LRU scan behavior so that scans continue through eligible pages instead of restarting unnecessarily.

* Improves InnoDB flushing performance by allowing a controlled single-page flush while an LRU batch flush is running and preventing repeated waits for an in-progress flush. Adds monitoring counters for single-page flushes and LRU flush waits.

This release addresses the list of Common Vulnerabilities and Exposures (CVE). Find the list of CVEs in [Percona Server for MySQL 9.7.1-1](https://docs.percona.com/percona-server/9.7/release-notes/9.7.1-1.html) release notes.

### MySQL 9.7.2

Improvements and bug fixes provided by Oracle for MySQL 9.7.2 and included in Percona Server for MySQL are the following:

* Under certain circumstances, when adding an AUTO_INCREMENT column to an existing table, some records in that table could be skipped, resulting in inaccurate values in the AUTO_INCREMENT column. (Bug #115136, Bug #37105825)

* During a buffer-pool resize, Adaptive Hash Index could be disabled in mysqld-auto.cnf even though innodb_adaptive_hash_index=ON. (Bug #39157211)

* Fixed a debug assertion in row_upd_rec_in_place() for non-versioned ROW_FORMAT=REDUNDANT rows. (Bug #39165747)

* Fixed an issue relating to table maintenance and clean-up. (Bug #39091376)

* Fixed an issue relating to unique indexes. (Bug #38501299)

Find the complete list of bug fixes and changes in the [MySQL 9.7.2 release notes](https://dev.mysql.com/doc/relnotes/mysql/9.7/en/news-9-7-2.html)

## Known issues

* This release does not include the Percona Toolkit component. We will add it once a Percona Toolkit version compatible with MySQL {{vers}} becomes available.
    
* In 9.7.x environments, the ProxySQL binlog reader can fail to initialize because it uses legacy commands, such as SHOW MASTER STATUS. Some internal counters also use outdated terminology. To address most terminology issues, enable the [terminology_use_previous](https://dev.mysql.com/doc/refman/9.7/en/replication-options-replica.html#sysvar_terminology_use_previous) system variable on the database server. This workaround addresses only terminology compatibility and may not fix all failures.

## Supplied components

Review each component’s release notes for What’s new, improvements, or bug fixes. The following is a list of the components supplied with the Percona Server for MySQL-based variation of the Percona Distribution for MySQL.

| Component           | Version   | Description                                |
| ------------------- | --------- | -------------------------------------------|
| Orchestrator        | [3.2.6-23](https://github.com/percona/orchestrator/releases/tag/v3.2.6-23)     | The replication topology manager for Percona Server for MySQL|
| ProxySQL            | [3.0.9](https://docs.percona.com/proxysql/3.0.9.html)     | A high performance, high-availability, protocol-aware proxy for MySQL|
| Percona XtraBackup  | [9.7.1-rc1](https://docs.percona.com/percona-xtrabackup/9.7/release-notes/9.7.1-rc1.html)| An open-source hot backup utility for MySQL-based servers|
| MySQL Shell         | [9.7.2](https://dev.mysql.com/doc/relnotes/mysql-shell/9.7/en/news-9-7-2.html)    | An advanced client and code editor for MySQL Server|
| MySQL Router        | [9.7.2](https://dev.mysql.com/doc/relnotes/mysql-router/9.7/en/news-9-7-2.html)    | Lightweight middleware that provides transparent routing between your application and back-end MySQL servers|
