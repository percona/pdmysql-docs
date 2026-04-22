# Percona Distribution for MySQL 8.4.8 using Percona XtraDB Cluster (2026-04-22)

Percona Distribution for MySQL is more than just a version of MySQL; it is a comprehensive solution that combines Percona Server for MySQL with additional tools to create a cohesive environment. This distribution is reliable, scalable, and secure, ensuring that all components have been tested to work seamlessly together. You can choose from two download options: one that uses Percona Server for MySQL and another that utilizes Percona XtraDB Cluster. Refer to [Install Percona Distribution for MySQL](installing.md).

This release is based on [Percona XtraDB Cluster 8.4.8-8](https://docs.percona.com/percona-xtradb-cluster/8.4/release-notes/8.4.8-8.html).

## Release highlights

### MySQL 8.4.8

Improvements and bug fixes provided by Oracle for MySQL 8.4.8 and included in Percona Server for MySQL are the following:

* The warning associated with redo logging being disabled is no longer present, as the underlying condition that triggered the warning has been eliminated. (Bug #37645185)

* A problem affecting the handling of large insert operations has been corrected, improving stability during bulk data loads. (Bug #38208188)

* An error that could arise when running certain SQL statements has been resolved. (Bug #38573285)

* Issues encountered when generating table definitions via `SHOW CREATE TABLE` have been fixed. (Bug #38448700)

* Bug #38298692 was addressed as part of the same fix set as Bug #38448700, resolving related inconsistencies in table metadata handling. (Bug #38298692)

* Performance regressions affecting queries that rely on regular expression matching have been corrected. (Bug #114056, Bug #36326728)

* The bundled OpenSSL dependency has been updated, addressing the issue tracked under Bug #38632932. (Bug #38632932)

* A concurrency flaw in InnoDB that could occur when executing SQL through the `que_eval_sql` interface has been removed. (Bug #118705, Bug #38310595)

* A timing issue that allowed binary logs to be removed before persisted expiration settings were fully applied has been fixed. (Bug #38554467)

* Several defects that prevented connections from closing properly when using the Thread Pool have been resolved. (Bug #38170188, Bug #36782728, Bug #38549372)

* An issue that caused gaps in GTID sequences when the `replica_skip_errors` option was enabled has been fixed. (Bug #28590993)

Find the complete list of bug fixes and changes in the [MySQL 8.4.8 release notes](https://dev.mysql.com/doc/relnotes/mysql/8.4/en/news-8-4-8.html).

## Supplied components

Review each component’s release notes for What’s new, improvements, or bug fixes. The following is a list of the components supplied with the Percona XtraDB Cluster-based variation of the Percona Distribution for MySQL:

| Component               | Version   | Description                                |
| ----------------------- | --------- | -------------------------------------------|
| Percona XtraBackup      | [8.4.0-5](https://docs.percona.com/percona-xtrabackup/8.4/release-notes/8.4.0-5.html)| An open-source hot backup utility for MySQL-based servers that doesn’t lock your database during the backup.|
| HAProxy                 | [2.8.18](https://git.haproxy.org/?p=haproxy-2.8.git;a=commit;h=ae90be6491cfe0cb0a16bfd5b03babfaf312b0bf) | A high-availability and load-balancing solution for Percona XtraDB Cluster. This is a default proxy.|
| ProxySQL                | [3.0.6](https://docs.percona.com/proxysql/3.0.6.html)| A high performance, high-availability, protocol-aware proxy for MySQL.          |
| Percona Toolkit         | [3.7.1-3](https://docs.percona.com/percona-toolkit/release_notes.html#v3-7-1-3-released-2026-04-17)     | The set of scripts to simplify and optimize database operation. |
| replication_manager.sh   | [1.0](https://docs.percona.com/percona-distribution-for-mysql/8.4/replication-manager-for-pxc.html)  | A tool to manage multi-source replication between multiple Percona XtraDB Cluster clusters. |
