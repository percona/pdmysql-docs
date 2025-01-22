# Percona Distribution for MySQL 8.0.40 using Percona XtraDB Cluster (2025-01-23)

Percona Distribution for MySQL is the most stable, scalable and secure open-source MySQL distribution, with two download options: one based on Percona Server for MySQL and one based on Percona XtraDB Cluster. [Install Percona Distribution for MySQL](installing.md).

This release is focused on the Percona XtraDB Cluster-based deployment variation. It is based on [Percona XtraDB Cluster 8.0.40-31](https://docs.percona.com/percona-xtradb-cluster/8.0/release-notes/8.0.40-31.html).

## Release highlights

Percona XtraDB Cluster is based on Percona Server for MySQL. Find a complete list of improvements and bug fixes in the [Percona Server for MySQL 8.0.40-31 (2024-12-30) release notes](https://docs.percona.com/percona-server/8.0/release-notes/8.0.40-31.html).

Improvements and bug fixes provided by Oracle for  MySQL 8.0.40 and included in Percona Server for MySQL are the following:

* Changes in MySQL 8.0.33 caused queries using joins on InnoDB tables to perform worse because refactoring affected functions that were previously inline.

* An unexpected exit ocurred if the server tried to update columns altered with NULL as the default value using the INSTANT algorithm.

* An unexpected exit during DELETE or UPDATE operations if a column, using the INSTANT algorithm, was dropped.

* Importing a table created under a different `sql_mode` sometimes led to schema mismatches, risking data corruption in secondary indexes. The fix now includes integrity checks on the imported tablespace.

* Rebuilding tables with secondary indexes required more file I/O operations compared to MySQL 8.0.26, which slowed down query performance.

Find the complete list of bug fixes and changes in the [MySQL 8.0.40 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/news-8-0-40.html).

## Supplied components

Review each component’s release notes for What’s new, improvements, or bug fixes. The following is a list of the components supplied with the Percona XtraDB Cluster-based variation of the Percona Distribution for MySQL:

| Component               | Version   | Description                                |
| ----------------------- | --------- | -------------------------------------------|
| Percona XtraBackup      | [8.0.35-32](https://docs.percona.com/percona-xtrabackup/8.0/release-notes/8.0/8.0.35-32.0.html)| An open-source hot backup utility for MySQL-based servers that doesn’t lock your database during the backup.|
| HAProxy                 | [2.8.11](https://git.haproxy.org/?p=haproxy-2.8.git;a=commit;h=01c1056a44823c5ffb8f74660b32c099d9b5355b) | A high-availability and load-balancing solution for Percona XtraDB Cluster. This is a default proxy.|
| ProxySQL                | [2.7.1-1](https://docs.percona.com/proxysql/2.7.1-1.html)| A high performance, high-availability, protocol-aware proxy for MySQL.          |
| Percona Toolkit         | [3.7.0](https://docs.percona.com/percona-toolkit/release_notes.html#v3-7-0-released-2024-12-23)     | The set of scripts to simplify and optimize database operation. |
| relication_manager.sh   | [1.0](./replication-manager/replication-manager-for-pxc.md)  | A tool to manage multi-source replication between multiple Percona XtraDB Cluster clusters. |
