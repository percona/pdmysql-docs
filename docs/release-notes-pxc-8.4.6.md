# Percona Distribution for MySQL 8.4.6 using Percona XtraDB Cluster (2025-10-06)

Percona Distribution for MySQL is more than just a version of MySQL; it is a comprehensive solution that combines Percona Server for MySQL with additional tools to create a cohesive environment. This distribution is reliable, scalable, and secure, ensuring that all components have been tested to work seamlessly together. You can choose from two download options: one that uses Percona Server for MySQL and another that utilizes Percona XtraDB Cluster. Refer to [Install Percona Distribution for MySQL](installing.md).

This release is based on [Percona XtraDB Cluster 8.4.6-6](https://docs.percona.com/percona-xtradb-cluster/8.4/release-notes/8.4.6-6.html).

## Release highlights

### Percona XtraDB Cluster 8.4.6-6

Improves State Snapshot Transfer (SST) by retrying Incremental State Transfer (IST) when initial SST attempts fail before any data changes, preventing unnecessary full data transfers.

### Percona Server for MySQL 8.4.6-6

Implements Link-Time Optimization (LTO) to generate more optimized release binaries, resulting in improved performance for specific workloads.

### MySQL 8.4.6

Bug fixes introduced by Oracle for MySQL 8.4.6 and included in Percona Server for MySQL are the following:

* Fixed an issue where rebuilding a primary key with duplicate entries could cause the server to stop unexpectedly. (Bug #37822992)

* Fixed an issue related to dropping columns that were part of an index. (Bug #37726881)

* Fixed an issue with indexing spatial datatype columns. (Bug #36682518)

* Fixed an issue where creating a secondary index on a `VARCHAR` column could exceed configured memory limits, with the amount allocated being directly related to the `value of innodb_ddl_buffer_size`, leading to errors such as ERROR 1136 (21S01): Column count doesn't match value count at row 1. (Bug #37233273)

Find the complete list of bug fixes and changes in the [MySQL 8.4.6 release notes](https://dev.mysql.com/doc/relnotes/mysql/8.4/en/news-8-4-6.html).

## Build & packaging notes

* The official packages were built with the `WITH_LTO=ON` flag to enable the Link-Time Optimization (LTO) feature.

* This release adds support for Red Hat Enterprise Linux 10.

## Supplied components

Review each component’s release notes for What’s new, improvements, or bug fixes. The following is a list of the components supplied with the Percona XtraDB Cluster-based variation of the Percona Distribution for MySQL:

| Component               | Version   | Description                                |
| ----------------------- | --------- | -------------------------------------------|
| Percona XtraBackup      | [8.4.0-4](https://docs.percona.com/percona-xtrabackup/8.4/release-notes/8.4.0-4.html)| An open-source hot backup utility for MySQL-based servers that doesn’t lock your database during the backup.|
| HAProxy                 | [2.8.15](https://git.haproxy.org/?p=haproxy-2.8.git;a=commit;h=a9aef56cb205d6d5e910530a87219900ccbd1b91) | A high-availability and load-balancing solution for Percona XtraDB Cluster. This is a default proxy.|
| ProxySQL                | [[2.7.3](https://docs.percona.com/proxysql/2.7.3.html)| A high performance, high-availability, protocol-aware proxy for MySQL.          |
| Percona Toolkit         | [3.7.0-2](https://docs.percona.com/percona-toolkit/release_notes.html#v3-7-0-2-released-2025-05-14)     | The set of scripts to simplify and optimize database operation. |
| replication_manager.sh   | [1.0](replication-manager-for-pxc.md)  | A tool to manage multi-source replication between multiple Percona XtraDB Cluster clusters. |
