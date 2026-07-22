# Percona Distribution for MySQL 8.4.10 using Percona XtraDB Cluster (2026-07-23)

Percona Distribution for MySQL is more than just a version of MySQL; it is a comprehensive solution that combines Percona Server for MySQL with additional tools to create a cohesive environment. This distribution is reliable, scalable, and secure, ensuring that all components have been tested to work seamlessly together. You can choose from two download options: one that uses Percona Server for MySQL and another that utilizes Percona XtraDB Cluster. Refer to [Install Percona Distribution for MySQL](installing.md).

!!! note ""

    Percona Distribution for MySQL 8.4.9-9 was not released; 8.4.10-10 is the next build in this series. This release includes enhancements and bug fixes from MySQL 8.4.9 and MySQL 8.4.10.

This release is based on [Percona XtraDB Cluster 8.4.10-10](https://docs.percona.com/percona-xtradb-cluster/8.4/release-notes/8.4.10-10.html).

## Release highlights

### Percona Server for MySQL 8.4.10-10

Percona Server for MySQL 8.4.10-10 introduces the following new features and improvements:

* Integrates the new Key Management Interoperability Protocol (KMIP) library into the key management component.

* Adds JSONL (JSON Lines) output format for Audit Log Filter.

* Increases the verbosity of the data dictionary upgrade process, making it easier to diagnose issues that occur during upgrade.

* Logs SQL statements for the Audit Log Filter `table_access` class and the `read` and `insert` subclasses.

* Flushes the audit log buffer on server shutdown when the `ASYNCHRONOUS` logging strategy is in use, preventing the loss of buffered events.

* Reduces memory pressure in the Audit Log Filter component caused by VFS buffering.

* Aligns the `audit_log_filter.format=NEW` output between the 8.0 plugin and the 8.4 component.

* Optimizes performance for `mem_root_deque`.

This release addresses the following security vulnerabilities:

* [CVE-2026-46850](https://www.cve.org/CVERecord?id=CVE-2026-46850): A vulnerability in MySQL Shell (Shell for VS Code) allows a low-privileged attacker with network access via HTTP to compromise MySQL Shell, with potential scope change impact on additional products (CVSS 3.1 Base Score 9.9).

* [CVE-2026-46860](https://www.cve.org/CVERecord?id=CVE-2026-46860): A vulnerability in MySQL Router allows an unauthenticated attacker with network access via HTTP to compromise MySQL Router (CVSS 3.1 Base Score 9.8).

* [CVE-2026-46861](https://www.cve.org/CVERecord?id=CVE-2026-46861): A vulnerability in MySQL NDB Cluster (NDB Operator) allows a low-privileged attacker with network access via HTTP to access or modify critical data, with potential scope change impact (CVSS 3.1 Base Score 9.6).

* [CVE-2026-46862](https://www.cve.org/CVERecord?id=CVE-2026-46862): A vulnerability in MySQL Router allows an unauthenticated attacker with network access via TLS to cause a hang or repeatable unexpected exit of MySQL Router (CVSS 3.1 Base Score 7.5).

* [CVE-2026-46863](https://www.cve.org/CVERecord?id=CVE-2026-46863): A vulnerability in MySQL Server connection handling allows an unauthenticated attacker with network access via multiple protocols to cause a hang or repeatable unexpected exit of the server (CVSS 3.1 Base Score 7.5).

* [CVE-2026-46869](https://www.cve.org/CVERecord?id=CVE-2026-46869): A vulnerability in MySQL Shell (Dump and Load) allows an unauthenticated attacker with network access to access critical data when user interaction is required (CVSS 3.1 Base Score 6.5).

* [CVE-2026-46870](https://www.cve.org/CVERecord?id=CVE-2026-46870): A vulnerability in MySQL Shell (Shell for VS Code) allows a low-privileged attacker with network access to compromise MySQL Shell, with potential scope change impact (CVSS 3.1 Base Score 8.5).

* [CVE-2026-46871](https://www.cve.org/CVERecord?id=CVE-2026-46871): A vulnerability in MySQL Shell (Shell for VS Code) allows a low-privileged attacker with network access via multiple protocols to access critical data (CVSS 3.1 Base Score 6.5).

* [CVE-2026-48165](https://www.cve.org/CVERecord?id=CVE-2026-48165): A vulnerability in the handling of the `wsrep_sst_donor` and `wsrep_sst_receive_address` system variables allowed a high-privileged user to execute arbitrary shell commands with the privileges of the `mariadbd` process during State Snapshot Transfer (SST) due to improper input sanitization (CVSS 3.1 Base Score 7.2). :contentReference[oaicite:0]{index=0}. (This fix was backported from MariaDB. Thanks to the MariaDB project for identifying and fixing this issue.)

* [CVE-2026-49261](https://www.cve.org/CVERecord?id=CVE-2026-49261): A vulnerability in MariaDB Server with `wsrep_notify_cmd` enabled allowed a remote attacker to execute arbitrary shell commands by embedding commands in the name of a joiner node due to improper input sanitization (CVSS 3.1 Base Score 10.0). :contentReference[oaicite:0]{index=0}. (This fix was backported from MariaDB. Thanks to the MariaDB project for identifying and fixing this issue.)

### MySQL 8.4.10

Improvements and bug fixes provided by Oracle for MySQL 8.4.10 and included in Percona Server for MySQL are the following:

* Connection attribute parsing could read a length-encoded size field before verifying that the complete field was present in the packet, leading to an out-of-bounds read. A size check is now performed before reading the field. (Bug #39116965)

* A regression in row size estimation for `ROW_FORMAT=COMPRESSED` tables could cause `CREATE TABLE` to fail with `Row size too large` for tables that were accepted in earlier releases. (Bug #39129182, Bug #120323)

Find the complete list of bug fixes and changes in the [MySQL 8.4.10 release notes](https://dev.mysql.com/doc/relnotes/mysql/8.4/en/news-8-4-10.html).

## Builds and packaging

* Percona XtraDB Cluster 8.4.10-10 adds support for Ubuntu 26.04.

* Percona Server for MySQL releases include a mixture of PGO and non-PGO builds. Where Profile-Guided Optimization (PGO) is enabled, the compiler uses runtime profiling data from representative workloads to guide optimization, which can improve throughput and reduce latency compared with non-PGO builds.

* See [Profile-Guided Optimization (PGO) and non-PGO builds](https://docs.percona.com/percona-server/8.4/pgo.html) for benefits, considerations, and which build you receive for your platform.

## Supplied components

Review each component’s release notes for What’s new, improvements, or bug fixes. The following is a list of the components supplied with the Percona XtraDB Cluster-based variation of the Percona Distribution for MySQL:

| Component               | Version   | Description                                |
| ----------------------- | --------- | -------------------------------------------|
| Percona XtraBackup      | [8.4.0-6](https://docs.percona.com/percona-xtrabackup/8.4/release-notes/8.4.0-6.html)| An open-source hot backup utility for MySQL-based servers that doesn’t lock your database during the backup.|
| HAProxy                 | [2.8.18](https://git.haproxy.org/?p=haproxy-2.8.git;a=commit;h=ae90be6491cfe0cb0a16bfd5b03babfaf312b0bf) | A high-availability and load-balancing solution for Percona XtraDB Cluster. This is a default proxy.|
| ProxySQL                | [3.0.6](https://docs.percona.com/proxysql/3.0.6.html)| A high performance, high-availability, protocol-aware proxy for MySQL.          |
| Percona Toolkit         | [3.7.1-4](https://docs.percona.com/percona-toolkit/release_notes.html#v3-7-1-4-released-2026-07-02)     | The set of scripts to simplify and optimize database operation. |
| replication_manager.sh   | [1.0](https://docs.percona.com/percona-distribution-for-mysql/8.4/replication-manager-for-pxc.html)  | A tool to manage multi-source replication between multiple Percona XtraDB Cluster clusters. |
