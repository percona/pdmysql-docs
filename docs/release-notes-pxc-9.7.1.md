# Percona Distribution for MySQL 9.7.1 using Percona XtraDB Cluster (2026-08-05)

Percona Distribution for MySQL is more than just a version of MySQL; it is a comprehensive solution that combines Percona Server for MySQL with additional tools to create a cohesive environment. This distribution is reliable, scalable, and secure, ensuring that all components have been tested to work seamlessly together. You can choose from two download options: one that uses Percona Server for MySQL and another that utilizes Percona XtraDB Cluster. Refer to [Install Percona Distribution for MySQL](installing.md).

!!! note ""

    Percona Distribution for MySQL 9.7.0 using Percona XtraDB Cluster was not released; 9.7.1 is the next build in this series. This release includes enhancements and bug fixes from MySQL 9.7.0 and MySQL 9.7.1.

This release is based on [Percona XtraDB Cluster 9.7.1-1](https://docs.percona.com/percona-server/9.7/release-notes/9.7.1-1.html) that includes all the features and bug fixes available in the [MySQL 9.7.0 Community Edition](https://dev.mysql.com/doc/relnotes/mysql/9.7/en/news-9-7-0.html) and enterprise-grade features developed by Percona.

## Release highlights

### Percona Server for MySQL 9.7.1-1

Percona Server for MySQL 9.7.1-1 introduces the following new features and improvements:

* Integrates the new Key Management Interoperability Protocol (KMIP) library into the key management component.

* Adds JSONL (JSON Lines) output format for Audit Log Filter.

* Increases the verbosity of the data dictionary upgrade process, making it easier to diagnose issues that occur during upgrade.

* Logs SQL statements for the Audit Log Filter `table_access` class and the `read` and `insert` subclasses.

* Flushes the audit log buffer on server shutdown when the `ASYNCHRONOUS` logging strategy is in use, preventing the loss of buffered events.

* Reduces memory pressure in the Audit Log Filter component caused by VFS buffering.

* Aligns the `audit_log_filter.format=NEW` output between the 8.0 plugin and the 8.4 component.

* Optimizes performance for `mem_root_deque`.

This release addresses the list of Common Vulnerabilities and Exposures (CVE). Find the list of CVEs in [Percona Server for MySQL 9.7.1-1](https://docs.percona.com/percona-server/9.7/release-notes/9.7.1-1.html) release notes.

### MySQL 9.7.0

Improvements and bug fixes provided by Oracle for MySQL 9.7.0 and included in Percona Server for MySQL are the following:

* Connection attribute parsing could read a length-encoded size field before verifying that the complete field was present in the packet, leading to an out-of-bounds read. A size check is now performed before reading the field. (Bug #39116965)

* A regression in row size estimation for `ROW_FORMAT=COMPRESSED` tables could cause `CREATE TABLE` to fail with `Row size too large` for tables that were accepted in earlier releases. (Bug #39129182, Bug #120323)

Find the complete list of bug fixes and changes in the [MySQL 9.7.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/9.7/en/news-9-7-0.html).

## Builds and packaging

* Percona Server for MySQL releases include a mixture of Profile-Guided Optimization (PGO) and non-PGO builds. Where PGO is enabled, the compiler uses runtime profiling data from representative workloads to guide optimization, which can improve throughput and reduce latency compared with non-PGO builds.

* See [Profile-Guided Optimization (PGO) and non-PGO builds](https://docs.percona.com/percona-server/9.7/pgo.md) for benefits, considerations, and which build is published for each platform.

* In Percona Server for MySQL 9.7.1-1 only, Debian and Ubuntu (APT) packaging was reorganized to align more closely with upstream MySQL. Several packages were split into separate components, which may affect upgrades and dependency resolution compared with earlier Percona Server releases. The APT packages are:

    * percona-server-client-core
    * percona-server-client-plugins
    * percona-server-client
    * percona-server-common
    * percona-server-server-core
    * percona-server-server
    * percona-telemetry-agent

## Known issues

* This release does not include the Percona Toolkit component. We will add it once a Percona Toolkit version compatible with MySQL {{vers}} becomes available.
    
* In 9.7.x environments, the ProxySQL binlog reader can fail to initialize because it uses legacy commands, such as SHOW MASTER STATUS. Some internal counters also use outdated terminology. To address most terminology issues, enable the [terminology_use_previous](https://dev.mysql.com/doc/refman/9.7/en/replication-options-replica.html#sysvar_terminology_use_previous) system variable on the database server. This workaround addresses only terminology compatibility and may not fix all failures.

## Supplied components

Review each component’s release notes for What’s new, improvements, or bug fixes. The following is a list of the components supplied with the Percona Server for MySQL-based variation of the Percona Distribution for MySQL.

| Component               | Version   | Description                                |
| ----------------------- | --------- | -------------------------------------------|
| Percona XtraBackup      | [8.4.0-6](https://docs.percona.com/percona-xtrabackup/8.4/release-notes/8.4.0-6.html)| An open-source hot backup utility for MySQL-based servers that doesn’t lock your database during the backup.|
| HAProxy                 | [2.8.26](https://git.haproxy.org/?p=haproxy-2.8.git;a=commit;h=682859627b241be60d2c26e0671c702a2681bcd2) | A high-availability and load-balancing solution for Percona XtraDB Cluster. This is a default proxy.|
| ProxySQL                | [2.7.3](https://docs.percona.com/proxysql/2.7.3.html)| A high performance, high-availability, protocol-aware proxy for MySQL.          |
| Percona Toolkit         | [3.7.1-4](https://docs.percona.com/percona-toolkit/release_notes.html#v3-7-1-4-released-2026-07-02)     | The set of scripts to simplify and optimize database operation. |
| replication_manager.sh   | [1.0](https://docs.percona.com/percona-distribution-for-mysql/8.4/replication-manager-for-pxc.html)  | A tool to manage multi-source replication between multiple Percona XtraDB Cluster clusters. |
