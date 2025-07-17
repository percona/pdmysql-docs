# Percona Distribution for MySQL 8.4.5 using Percona XtraDB Cluster (2025-07-14)

Percona Distribution for MySQL is more than just a version of MySQL; it is a comprehensive solution that combines Percona Server for MySQL with additional tools to create a cohesive environment. This distribution is reliable, scalable, and secure, ensuring that all components have been tested to work seamlessly together. You can choose from two download options: one that uses Percona Server for MySQL and another that utilizes Percona XtraDB Cluster. Refer to [Install Percona Distribution for MySQL](installing.md).

This release is based on [Percona XtraDB Cluster 8.4.5-5](https://docs.percona.com/percona-xtradb-cluster/8.4/release-notes/8.4.5-5.html).

## Release highlights

### Percona XtraDB Cluster 8.4.5-5

Improves State Snapshot Transfer (SST) failure diagnostics. `garbd` now uses distinct exit codes to differentiate between donor exit, SST script failure, and garbd-initiated termination, making SST issues easier to identify and debug.

### Percona Server for MySQL 8.4.5-5

* Updates the C++ level of the KMPI library to enhance error handling capabilities.

* Improves optimizer behavior by restoring correct handling of const tables in `test_quick_select()`. A MySQL Upstream refactor (commit [9a13c1c](https://github.com/percona/percona-server/commit/9a13c1c6971f4bd56d143179ecfb34cca8ecc018)) removed the `QEP_TAB` dependency, causing `get_quick_record_count()` to no longer pass const table information. This could lead to suboptimal range scan boundaries. The applied patch resolves the issue by explicitly passing `const_tables` to `test_quick_select()`, ensuring consistent behavior with the pre-refactor logic.


### MySQL 8.4.5

Improvements and bug fixes introduced by Oracle for MySQL 8.4.5 and included in Percona Server for MySQL are the following:

* Fixed an issue where `CHECK TABLE` sometimes incorrectly reported that spatial indexes were corrupted. (Bug #37286473)

* Fixed an issue in InnoDB redo log recovery to improve data safety after a crash. (Bug #37061960)

* Fixed an issue where reading `index_id` values could lead to incorrect behavior with indexes. (Bug #36993445, Bug #37709706)

* Fixed a bug related to the `lower_case_table_names` setting that caused inconsistent behavior with table names on different systems. (Bug #32288105)

* Fixed a bug where `mysqldump` did not properly escape certain special characters in its output. (Bug #37540722, Bug #37709163)

* The `fprintf_string()` function in `mysqldump` did not use the correct quote character for escaping strings. (Bug #37607195)

Find the complete list of bug fixes and changes in the [MySQL 8.4.5 release notes](https://dev.mysql.com/doc/relnotes/mysql/8.4/en/news-8-4-5.html).

## Supplied components

Review each component’s release notes for What’s new, improvements, or bug fixes. The following is a list of the components supplied with the Percona XtraDB Cluster-based variation of the Percona Distribution for MySQL:

| Component               | Version   | Description                                |
| ----------------------- | --------- | -------------------------------------------|
| Percona XtraBackup      | [8.4.0-3](https://docs.percona.com/percona-xtrabackup/8.4/release-notes/8.4.0-3.html)| An open-source hot backup utility for MySQL-based servers that doesn’t lock your database during the backup.|
| HAProxy                 | [2.8.14](https://git.haproxy.org/?p=haproxy-2.8.git;a=commit;h=a9aef56cb205d6d5e910530a87219900ccbd1b91) | A high-availability and load-balancing solution for Percona XtraDB Cluster. This is a default proxy.|
| ProxySQL                | [2.7.3](https://docs.percona.com/proxysql/2.7.3.html)| A high performance, high-availability, protocol-aware proxy for MySQL.          |
| Percona Toolkit         | [3.7.0-2](https://docs.percona.com/percona-toolkit/release_notes.html#v3-7-0-2-released-2025-05-14)     | The set of scripts to simplify and optimize database operation. |
| replication_manager.sh   | [1.0](replication-manager-for-pxc.md)  | A tool to manage multi-source replication between multiple Percona XtraDB Cluster clusters. |

