# Percona Distribution for MySQL 9.7.2 using Percona XtraDB Cluster (2026-10-)

!!! note "A note on MySQL 9.7.3"

    After a thorough review of the updates included in MySQL 9.7.3, Percona has decided not to release a corresponding Percona Server for MySQL 9.7.3. MySQL 9.7.3 is a Critical Security Patch Update (CSPU) — a targeted security release that Oracle can issue between quarterly Critical Patch Updates (CPUs) when needed. The fixes included in this CSPU do not affect Percona Server for MySQL.

Percona Distribution for MySQL is more than just a version of MySQL; it is a comprehensive solution that combines Percona Server for MySQL with additional tools to create a cohesive environment. This distribution is reliable, scalable, and secure, ensuring that all components have been tested to work seamlessly together. You can choose from two download options: one that uses Percona Server for MySQL and another that utilizes Percona XtraDB Cluster. Refer to [Install Percona Distribution for MySQL](installing.md).

This release is based on [Percona XtraDB Cluster 9.7.2-2](https://docs.percona.com/percona-server/9.7/release-notes/9.7.2-2.html) that includes all the features and bug fixes available in the [MySQL 9.7.0 Community Edition](https://dev.mysql.com/doc/relnotes/mysql/9.7/en/news-9-7-0.html) and enterprise-grade features developed by Percona.

## Release highlights

### Percona Server for MySQL 9.7.2-2

Percona Server for MySQL 9.7.2-2 introduces the following new features and improvements:

* Adds OpenID Connect (OIDC) authentication through external identity providers. See [Connect OIDC](https://docs.percona.com/percona-server/9.7/openid-connect-authentication.html).

* Adds SQL functions that calculate the distance between vector values. See [`DISTANCE()`](https://docs.percona.com/percona-server/9.7/distance-function.html).

### MySQL 9.7.2

Improvements and bug fixes provided by Oracle for MySQL 9.7.2 and included in Percona Server for MySQL are the following:

* Under certain circumstances, when adding an AUTO_INCREMENT column to an existing table, some records in that table could be skipped, resulting in inaccurate values in the AUTO_INCREMENT column. (Bug #115136, Bug #37105825)

* During a buffer-pool resize, Adaptive Hash Index could be disabled in `mysqld-auto.cnf` even though `innodb_adaptive_hash_index=ON`. (Bug #39157211)

* Fixed a debug assertion in `row_upd_rec_in_place()` for non-versioned `ROW_FORMAT=REDUNDANT` rows. (Bug #39165747)

* Fixed an issue relating to table maintenance and clean-up. (Bug #39091376)

* Fixed an issue relating to unique indexes. (Bug #38501299)

Find the complete list of bug fixes and changes in the [MySQL 9.7.2 release notes](https://dev.mysql.com/doc/relnotes/mysql/9.7/en/news-9-7-2.html).

## Known issues

* This release does not include the Percona Toolkit component. We will add it once a Percona Toolkit version compatible with MySQL {{vers}} becomes available.
    
* In 9.7.x environments, the ProxySQL binlog reader can fail to initialize because it uses legacy commands, such as SHOW MASTER STATUS. Some internal counters also use outdated terminology. To address most terminology issues, enable the [terminology_use_previous](https://dev.mysql.com/doc/refman/9.7/en/replication-options-replica.html#sysvar_terminology_use_previous) system variable on the database server. This workaround addresses only terminology compatibility and may not fix all failures.

## Supplied components

Review each component’s release notes for What’s new, improvements, or bug fixes. The following is a list of the components supplied with the Percona Server for MySQL-based variation of the Percona Distribution for MySQL.

| Component               | Version   | Description                                |
| ----------------------- | --------- | -------------------------------------------|
| Percona XtraBackup      | [9.7.1-rc1](https://docs.percona.com/percona-xtrabackup/9.7/release-notes/9.7.1-rc1.html)| An open-source hot backup utility for MySQL-based servers that doesn’t lock your database during the backup.|
| HAProxy                 | [3.4.7](https://git.haproxy.org/?p=haproxy-3.4.git;a=commit;h=8872a2604595140544774c2a6309a41186fc0f44) | A high-availability and load-balancing solution for Percona XtraDB Cluster. This is a default proxy.|
| ProxySQL                | [3.0.9](https://docs.percona.com/proxysql/3.0.9.html)| A high performance, high-availability, protocol-aware proxy for MySQL.          |
| replication_manager.sh   | [1.0](https://docs.percona.com/percona-distribution-for-mysql/9.7/replication-manager-for-pxc.html)  | A tool to manage multi-source replication between multiple Percona XtraDB Cluster clusters. |
