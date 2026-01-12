# Percona Distribution for MySQL 8.4.7 using Percona Server for MySQL (2025-12-22)

Percona Distribution for MySQL is more than just a version of MySQL; it is a comprehensive solution that combines Percona Server for MySQL with additional tools to create a cohesive environment. This distribution is reliable, scalable, and secure, ensuring that all components have been tested to work seamlessly together. You can choose from two download options: one that uses Percona Server for MySQL and another that utilizes Percona XtraDB Cluster. Refer to [Install Percona Distribution for MySQL](installing.md).

This release is based on [Percona Server for MySQL 8.4.7-7](https://docs.percona.com/percona-server/8.4/release-notes/8.4.7-7.html) that includes all the features and bug fixes available in the [MySQL 8.4.6 Community Edition](https://dev.mysql.com/doc/relnotes/mysql/8.4/en/news-8-4-7.html) and enterprise-grade features developed by Percona.

## Release highlights

### Percona Server for MySQL 8.4.7-7

The audit log plugin has been reintroduced in Percona Server for MySQL 8.4. However, it is already marked as deprecated and is planned for removal in a future release. This deprecation is due to the availability of the [audit log filter component](https://docs.percona.com/percona-server/8.4/audit-log-filter-overview.html), which is the recommended replacement. Users should migrate to this component, which provides equivalent functionality with enhanced flexibility, performance, and filtering capabilities, ensuring continued support for auditing and compliance requirements.

### MySQL 8.4.7

Improvements and bug fixes introduced by Oracle for MySQL 8.4.7 and included in Percona Server for MySQL are the following:

* Fixed an issue where parallel scan thread creation could fail, causing assertion failures when falling back to single-thread mode. (Bug #38325137)

* Fixed an issue where virtual index rollback could fail on 32-bit builds of MySQL Server under certain circumstances. (Bug #38167527)

* Fixed an issue where very large buffer pools could require excessive memory chunks per instance, potentially causing allocation failures. The allocation is now validated to ensure proper memory allocation. (Bug #37994397)

* Fixed an issue where assertion failures could occur due to data size and bounds mismatches during DDL file operations. (Bug #37882398)

* Fixed an issue related to modifying the internal Full-Text Search (FTS) configuration. (Bug #37792010)

* Fixed an issue related to virtual indexes. (Bug #37602657)

* Fixed an issue where confusing warning messages could appear when row sizes exceeded maximum allowed limits with `innodb_strict_mode=OFF`, such as during table selection or column dropping operations. Error messages have been improved for clarity. (Bug #37003342, Bug #36768046, Bug #36867372)

Find the complete list of bug fixes and changes in the [MySQL 8.4.7 release notes :octicons-link-external-16:](https://dev.mysql.com/doc/relnotes/mysql/8.4/en/news-8-4-7.html).

## Packaging and build notes

* Percona Server for MySQL 8.4 adds support for Debian 13.

* Percona Server for MySQL 8.4 has ended support for Ubuntu 20.04.

* Amazon Linux 2023 is not supported in Percona Distribution for MySQL. We do support Amazon Linux 2023 in Percona Server for MySQL and Percona XtraBackup.

## Known issues and limitations

* MySQL Shell is not available as a prebuilt package for Debian 11 (Bullseye) in the Percona APT repository. Recent MySQL Shell releases are built with GNU Compiler Collection (GCC) 11 or later, while Debian 11 ships with GCC 10, making these binaries incompatible.
    
* ProxySQL contains counters that have not been updated to use the new terminology. Unexpected results may occur. In an 8.4.x environment, the binlog reader errors out during initialization due to the use of old terminology, such as the SHOW MASTER STATUS command.

## Supplied components

Review each component’s release notes for What’s new, improvements, or bug fixes. The following is a list of the components supplied with the Percona Server for MySQL-based variation of the Percona Distribution for MySQL.

| Component           | Version   | Description                                |
| ------------------- | --------- | -------------------------------------------|
| Orchestrator        | [3.2.6-19](https://github.com/percona/orchestrator/releases/tag/v3.2.6-19)     | The replication topology manager for Percona Server for MySQL|
| ProxySQL            | [2.7.3](https://docs.percona.com/proxysql/2.7.3.html)     | A high performance, high-availability, protocol-aware proxy for MySQL|
| Percona Toolkit     | [3.7.1](https://docs.percona.com/percona-toolkit/release_notes.html#v3-7-1-released-2025-12-17)     | The set of scripts to simplify and optimize database operation. |
| Percona XtraBackup  | [8.4.0-5](https://docs.percona.com/percona-xtrabackup/8.4/release-notes/8.4.0-5.html)| An open-source hot backup utility for MySQL-based servers|
| MySQL Shell         | [8.4.7](https://dev.mysql.com/doc/relnotes/mysql-shell/8.4/en/news-8-4-7.html)    | An advanced client and code editor for MySQL Server|
| MySQL Router        | [8.4.7](https://dev.mysql.com/doc/relnotes/mysql-router/8.4/en/news-8-4-7.html)    | Lightweight middleware that provides transparent routing between your application and back-end MySQL servers|
