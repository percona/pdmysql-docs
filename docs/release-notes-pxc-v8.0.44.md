# Percona Distribution for MySQL 8.0.44 using Percona XtraDB Cluster (2025-12-)

Percona Distribution for MySQL is more than just a version of MySQL; it is a comprehensive solution that combines Percona Server for MySQL with additional tools to create a cohesive environment. This distribution is reliable, scalable, and secure, ensuring that all components have been tested to work seamlessly together. You can choose from two download options: one that uses Percona Server for MySQL and another that utilizes Percona XtraDB Cluster. Refer to [Install Percona Distribution for MySQL](installing.md).

This release is focused on the Percona XtraDB Cluster-based deployment variation. It is based on [Percona XtraDB Cluster 8.0.44-35](https://docs.percona.com/percona-xtradb-cluster/8.0/release-notes/8.0.44-35.html).

## Release highlights

Announcement – Discontinuation of the Percona PRO Program

Percona has consolidated its build offerings. The Pro builds are no longer required, and all features have been merged into the main open source Community release.

### MySQL 8.0.44

Improvements and bug fixes provided by Oracle for MySQL 8.0.44 and included in Percona Server for MySQL are the following:

* Fixed an issue that caused excessive memory chunk usage for very large buffer pools, which could lead to allocation failures. The allocation process now includes validation to ensure sufficient and stable memory allocation. (Bug #37994397)

* Fixed an issue where assertion failures could occur due to data size and bounds mismatches during DDL file operations. (Bug #37882398)

Find the complete list of bug fixes and changes in the [MySQL 8.0.44 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/news-8-0-44.html).

## Packaging and build notes

* Percona XtraDB Cluster 8.0 does not support Debian 13 or Red Hat Enterprise Linux 10.

* Percona XtraDB Cluster 8.0 has ended support for Ubuntu 20.04.

## Supplied components

Review each component’s release notes for What’s new, improvements, or bug fixes. The following is a list of the components supplied with the Percona XtraDB Cluster-based variation of the Percona Distribution for MySQL:

| Component               | Version   | Description                                |
| ----------------------- | --------- | -------------------------------------------|
| Percona XtraBackup      | [8.0.35-34](https://docs.percona.com/percona-xtrabackup/8.0/release-notes/8.0/8.0.35-34.0.html)| An open-source hot backup utility for MySQL-based servers that doesn’t lock your database during the backup.|
| HAProxy                 | [2.8.15](https://git.haproxy.org/?p=haproxy-2.8.git;a=commit;h=a9aef56cb205d6d5e910530a87219900ccbd1b91) | A high-availability and load-balancing solution for Percona XtraDB Cluster. This is a default proxy.|
| ProxySQL                | [2.7.3](https://docs.percona.com/proxysql/2.7.3.html)| A high performance, high-availability, protocol-aware proxy for MySQL.          |
| Percona Toolkit         | [3.7.0-2](https://docs.percona.com/percona-toolkit/release_notes.html#v3-7-0-2-released-2025-05-14)     | The set of scripts to simplify and optimize database operation. |
| relication_manager.sh   | [1.0](https://docs.percona.com/percona-distribution-for-mysql/8.0/replication-manager/replication-manager-for-pxc.html)  | A tool to manage multi-source replication between multiple Percona XtraDB Cluster clusters. |
