# Percona Distribution for MySQL 8.0.37 using Percona XtraDB Cluster (2024-09-18)

Percona Distribution for MySQL is the most stable, scalable and secure open-source MySQL distribution, with two download options: one based on Percona Server for MySQL and one based on Percona XtraDB Cluster. [Install Percona Distribution for MySQL](installing.md).

This release is focused on the Percona XtraDB Cluster-based deployment variation. It is based on [Percona XtraDB Cluster 8.0.37](https://docs.percona.com/percona-xtradb-cluster/8.0/release-notes/8.0.37-29.html)

## Release highlights

This release enhances telemetry and provides a more comprehensive explanation of how the telemetry works, including new components, metrics files, and additional methods for disabling telemetry. Find more information in the [Telemetry on Percona XtraDB Cluster](https://docs.percona.com/percona-xtradb-cluster/8.0/telemetry.html) document.

Improvements and bug fixes provided by Oracle for MySQL 8.0.37 and included in Percona Server for MySQL are the following:

* The redo log might not record a change in column order when using instant DDL, potentially leading to an inaccurate log replay during the recovery process. (Bug #35183686)

* Enhanced management of buffers has been implemented in deleting tablespaces to prevent a possible assertion failure. (Bug #35676106, Bug #36343647)

* Resolved an assertion failure associated with full-text indexes. (Bug #35836581)

Find the complete list of bug fixes and changes in the [MySQL 8.0.37 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/news-8-0-37.html).

## Packaging notes

Percona XtraDB Cluster 8.0.37-29 supports Ubuntu 24.04.

## Supplied components

Review each component’s release notes for What’s new, improvements, or bug fixes. The following is a list of the components supplied with the Percona XtraDB Cluster-based variation of the Percona Distribution for MySQL:

| Component               | Version   | Description                                |
| ----------------------- | --------- | -------------------------------------------|
| Percona XtraBackup      | [8.0.35-30](https://docs.percona.com/percona-xtrabackup/8.0/release-notes/8.0/8.0.35-30.0.html)| An open-source hot backup utility for MySQL-based servers that doesn’t lock your database during the backup.|
| HAProxy                 | [2.8.10](https://git.haproxy.org/?p=haproxy-2.8.git;a=commit;h=f28885f42e7e36215e2005cf57fae6ac118e18b9) | A high-availability and load-balancing solution for Percona XtraDB Cluster. This is a default proxy.|
| ProxySQL                | [2.6.5](https://docs.percona.com/proxysql/2.6.5.html)| A high performance, high-availability, protocol-aware proxy for MySQL.          |
| Percona Toolkit         | [3.6.0](https://docs.percona.com/percona-toolkit/release_notes.html#v3-6-0-released-2024-06-12)     | The set of scripts to simplify and optimize database operation. |
| relication_manager.sh   | [1.0](./replication-manager/replication-manager-for-pxc.md)  | A tool to manage multi-source replication between multiple Percona XtraDB Cluster clusters. |

