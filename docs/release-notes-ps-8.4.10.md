# Percona Distribution for MySQL 8.4.10 using Percona Server for MySQL (2026-06-30)

Percona Distribution for MySQL is more than just a version of MySQL; it is a comprehensive solution that combines Percona Server for MySQL with additional tools to create a cohesive environment. This distribution is reliable, scalable, and secure, ensuring that all components have been tested to work seamlessly together. You can choose from two download options: one that uses Percona Server for MySQL and another that utilizes Percona XtraDB Cluster. Refer to [Install Percona Distribution for MySQL](installing.md).

!!! note ""

    Percona Distribution for MySQL 8.4.9-9 was not released; 8.4.10-10 is the next build in this series. This release includes enhancements and bug fixes from MySQL 8.4.9 and MySQL 8.4.10.

This release is based on [Percona Server for MySQL 8.4.10-10](https://docs.percona.com/percona-server/8.4/release-notes/8.4.10-10.html) that includes all the features and bug fixes available in the [MySQL 8.4.10 Community Edition](https://dev.mysql.com/doc/relnotes/mysql/8.4/en/news-8-4-10.html) and enterprise-grade features developed by Percona.

## Release 

### Percona Server for MySQL 8.4.10-10

Percona Server for MySQL 8.4.10-10 introduces the following features and improvements:

* Integrates the new Key Management Interoperability Protocol (KMIP) library into the key management component.

* Expands Thread Pool statistics with status variables for queue monitoring and wait time analysis.

* Introduces JSONL (JSON Lines) output format for Audit Log Filter.

* Increases data dictionary upgrade logging verbosity to aid diagnosis of upgrade failures.

* Extends Audit Log Filter logging so the `table_access` class records `read` and `insert` statements.

* Changes audit log shutdown behavior to flush the buffer when the `ASYNCHRONOUS` logging strategy is in use.

* Reduces memory pressure in the Audit Log Filter component caused by virtual file system (VFS) buffering.

* Aligns `audit_log_filter.format=NEW` behavior between the 8.0 plugin and the 8.4 component.

* Suppresses nested general/status records in Audit Log Filter output when `audit_log_filter.event_mode=REDUCED` was enabled.

* Removes `format=OLD` and set JSONL as the default Audit Log Filter output format.

* Optimizes performance of `mem_root_deque`.

This release addresses the list of Common Vulnerabilities and Exposures (CVE). Find the list of CVEs in [Percona Server for MySQL 8.4.10-10](https://docs.percona.com/percona-server/8.4/release-notes/8.4.10-10.html) release notes.

### MySQL 8.4.9

Improvements and bug fixes provided by Oracle for MySQL 8.4.9 and included in Percona Server for MySQL are the following:

* Connection attribute parsing could read a length-encoded size field before verifying that the complete field was present in the packet, leading to an out-of-bounds read. A size check is now performed before reading the field. (Bug #39116965)

* A regression in row size estimation for `ROW_FORMAT=COMPRESSED` tables could cause `CREATE TABLE` to fail with `Row size too large` for tables that were accepted in earlier releases. (Bug #39129182, Bug #120323)

* Under certain circumstances, when calculating the maximum possible index record size, an assertion failure could occur. (Bug #85060, Bug #25579578)

Find the complete list of bug fixes and changes in the [MySQL 8.4.9 release notes :octicons-link-external-16:](https://dev.mysql.com/doc/relnotes/mysql/8.4/en/news-8-4-9.html).

## Builds and packaging

* Percona Server for MySQL releases include a mixture of PGO and non-PGO builds. Where Profile-Guided Optimization (PGO) is enabled, the compiler uses runtime profiling data from representative workloads to guide optimization, which can improve throughput and reduce latency compared with non-PGO builds.

* See [Profile-Guided Optimization (PGO) and non-PGO builds](https://docs.percona.com/percona-server/8.4/pgo.md) for benefits, considerations, and which build you receive for your platform.

## Known issues and limitations
    
* In 8.4.x environments, the ProxySQL binlog reader can fail to initialize because it uses legacy commands, such as SHOW MASTER STATUS. Some internal counters also use outdated terminology. To address most terminology issues, enable the [terminology_use_previous](https://dev.mysql.com/doc/refman/8.4/en/replication-options-replica.html#sysvar_terminology_use_previous) system variable on the database server. This workaround addresses only terminology compatibility and may not fix all failures.

## Supplied components

Review each component’s release notes for What’s new, improvements, or bug fixes. The following is a list of the components supplied with the Percona Server for MySQL-based variation of the Percona Distribution for MySQL.

| Component           | Version   | Description                                |
| ------------------- | --------- | -------------------------------------------|
| Orchestrator        | [3.2.6-20](https://github.com/percona/orchestrator/releases/tag/v3.2.6-20)     | The replication topology manager for Percona Server for MySQL|
| ProxySQL            | [2.7.3](https://docs.percona.com/proxysql/2.7.3.html)     | A high performance, high-availability, protocol-aware proxy for MySQL|
| Percona Toolkit     | [3.7.1](https://docs.percona.com/percona-toolkit/release_notes.html#v3-7-1-released-2025-12-17)     | The set of scripts to simplify and optimize database operation. |
| Percona XtraBackup  | [8.4.0-5](https://docs.percona.com/percona-xtrabackup/8.4/release-notes/8.4.0-5.html)| An open-source hot backup utility for MySQL-based servers|
| MySQL Shell         | [8.4.10](https://dev.mysql.com/doc/relnotes/mysql-shell/8.4/en/news-8-4-10.html)    | An advanced client and code editor for MySQL Server|
| MySQL Router        | [8.4.10](https://dev.mysql.com/doc/relnotes/mysql-router/8.4/en/news-8-4-10.html)    | Lightweight middleware that provides transparent routing between your application and back-end MySQL servers|
