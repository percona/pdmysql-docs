# Percona Distribution for MySQL 8.0.43 using Percona XtraDB Cluster (2025-09-22)

Percona Distribution for MySQL is more than just a version of MySQL; it is a comprehensive solution that combines Percona Server for MySQL with additional tools to create a cohesive environment. This distribution is reliable, scalable, and secure, ensuring that all components have been tested to work seamlessly together. You can choose from two download options: one that uses Percona Server for MySQL and another that utilizes Percona XtraDB Cluster. Refer to [Install Percona Distribution for MySQL](installing.md).

This release is focused on the Percona XtraDB Cluster-based deployment variation. It is based on [Percona XtraDB Cluster 8.0.43-34](https://docs.percona.com/percona-xtradb-cluster/8.0/release-notes/8.0.43-34.html).

## Release highlights

Percona XtraDB Cluster is based on Percona Server for MySQL. Find a complete list of improvements and bug fixes in the [Percona Server for MySQL 8.0.43-34 (2025-08-28) release notes](https://docs.percona.com/percona-server/8.0/release-notes/8.0.43-34.html).

### Percona XtraDB Cluster 8.0.43-34

Improves State Snapshot Transfer (SST) by retrying Incremental State Transfer (IST) when initial SST attempts fail before any data changes, preventing unnecessary full data transfers.

### Percona Server for MySQL 8.0.43-34

Implements Link-Time Optimization (LTO) to generate more optimized release binaries, resulting in improved performance for specific workloads.

### MySQL 8.0.43

Improvements and bug fixes provided by Oracle for MySQL 8.0.43 and included in Percona Server for MySQL are the following:

* Fixed an issue where `CHECK TABLE` sometimes incorrectly reported that spatial indexes were corrupted. (Bug #37286473)

* Fixed an issue in InnoDB redo log recovery to improve data safety after a crash. (Bug #37061960)

* Fixed an issue where reading `index_id` values could lead to incorrect behavior with indexes. (Bug #36993445, Bug #37709706)

* Fixed a bug related to the `lower_case_table_names` setting that caused inconsistent behavior with table names on different systems. (Bug #32288105)

* Fixed a bug where `mysqldump` did not properly escape certain special characters in its output. (Bug #37540722, Bug #37709163)

* The `fprintf_string()` function in `mysqldump` did not use the correct quote character for escaping strings. (Bug #37607195)

Find the complete list of bug fixes and changes in the [MySQL 8.0.43 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/news-8-0-43.html).

## Build & packaging notes

* The official packages were built with the `WITH_LTO=ON` flag to enable the Link-Time Optimization (LTO) feature.

## Supplied components

Review each component’s release notes for What’s new, improvements, or bug fixes. The following is a list of the components supplied with the Percona XtraDB Cluster-based variation of the Percona Distribution for MySQL:

| Component               | Version   | Description                                |
| ----------------------- | --------- | -------------------------------------------|
| Percona XtraBackup      | [8.0.35-34](https://docs.percona.com/percona-xtrabackup/8.0/release-notes/8.0/8.0.35-34.0.html)| An open-source hot backup utility for MySQL-based servers that doesn’t lock your database during the backup.|
| HAProxy                 | [2.8.15](https://git.haproxy.org/?p=haproxy-2.8.git;a=commit;h=a9aef56cb205d6d5e910530a87219900ccbd1b91) | A high-availability and load-balancing solution for Percona XtraDB Cluster. This is a default proxy.|
| ProxySQL                | [2.7.3](https://docs.percona.com/proxysql/2.7.3.html)| A high performance, high-availability, protocol-aware proxy for MySQL.          |
| Percona Toolkit         | [3.7.0-2](https://docs.percona.com/percona-toolkit/release_notes.html#v3-7-0-2-released-2025-05-14)     | The set of scripts to simplify and optimize database operation. |
| relication_manager.sh   | [1.0](./replication-manager/replication-manager-for-pxc.md)  | A tool to manage multi-source replication between multiple Percona XtraDB Cluster clusters. |
