# Percona Distribution for MySQL 8.4.7 using Percona XtraDB Cluster (2026-01-)

Percona Distribution for MySQL is more than just a version of MySQL; it is a comprehensive solution that combines Percona Server for MySQL with additional tools to create a cohesive environment. This distribution is reliable, scalable, and secure, ensuring that all components have been tested to work seamlessly together. You can choose from two download options: one that uses Percona Server for MySQL and another that utilizes Percona XtraDB Cluster. Refer to [Install Percona Distribution for MySQL](installing.md).

This release is based on [Percona XtraDB Cluster 8.4.7-7](https://docs.percona.com/percona-xtradb-cluster/8.4/release-notes/8.4.7-7.html).

## Release highlights

### Percona Server for MySQL 8.4.7-7

* The audit log plugin has been reintroduced in Percona Server for MySQL 8.4. However, it is already marked as deprecated and is planned for removal in a future release. This deprecation is due to the availability of the [audit log filter component](https://docs.percona.com/percona-server/8.4/audit-log-filter-overview.html), which is the recommended replacement. Users should migrate to this component, which provides equivalent functionality with enhanced flexibility, performance, and filtering capabilities, ensuring continued support for auditing and compliance requirements.

### MySQL 8.4.7

Improvements and bug fixes provided by Oracle for MySQL 8.4.7 and included in Percona Server for MySQL are the following:

* Fixed an issue that caused excessive memory chunk usage for very large buffer pools, which could lead to allocation failures. The allocation process now includes validation to ensure sufficient and stable memory allocation. (Bug #37994397)
  
* Fixed an issue where assertion failures could occur due to data size and bounds mismatches during DDL file operations. (Bug #37882398)

Find the complete list of bug fixes and changes in the [MySQL 8.4.7 release notes](https://dev.mysql.com/doc/relnotes/mysql/8.4/en/news-8-4-7.html).

## Build & packaging notes

* Percona XtraDB Cluster 8.4 adds support for Debian 13.

* Percona XtraDB Cluster 8.4 has ended support for Ubuntu 20.04.

* Percona Distribution for MySQL 8.4 is not supported on Amazon Linux 2023.

## Supplied components

Review each component’s release notes for What’s new, improvements, or bug fixes. The following is a list of the components supplied with the Percona XtraDB Cluster-based variation of the Percona Distribution for MySQL:

| Component               | Version   | Description                                |
| ----------------------- | --------- | -------------------------------------------|
| Percona XtraBackup      | [8.4.0-5](https://docs.percona.com/percona-xtrabackup/8.4/release-notes/8.4.0-5.html)| An open-source hot backup utility for MySQL-based servers that doesn’t lock your database during the backup.|
| HAProxy                 | [2.8.15](https://git.haproxy.org/?p=haproxy-2.8.git;a=commit;h=a9aef56cb205d6d5e910530a87219900ccbd1b91) | A high-availability and load-balancing solution for Percona XtraDB Cluster. This is a default proxy.|
| ProxySQL                | [2.7.3](https://docs.percona.com/proxysql/2.7.3.html)| A high performance, high-availability, protocol-aware proxy for MySQL.          |
| Percona Toolkit         | [3.7.1](https://docs.percona.com/percona-toolkit/release_notes.html#v3-7-1-released-2025-12-17)     | The set of scripts to simplify and optimize database operation. |
| replication_manager.sh   | [1.0](replication-manager-for-pxc.md)  | A tool to manage multi-source replication between multiple Percona XtraDB Cluster clusters. |
