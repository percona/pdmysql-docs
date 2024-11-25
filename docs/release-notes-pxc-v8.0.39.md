# Percona Distribution for MySQL 8.0.39 using Percona XtraDB Cluster (2024-11-)

Percona Distribution for MySQL is the most stable, scalable and secure open-source MySQL distribution, with two download options: one based on Percona Server for MySQL and one based on Percona XtraDB Cluster. [Install Percona Distribution for MySQL](installing.md).

This release is focused on the Percona XtraDB Cluster-based deployment variation. It is based on [Percona XtraDB Cluster 8.0.39-30](https://docs.percona.com/percona-xtradb-cluster/8.0/release-notes/8.0.39-30.html). [Percona XtraDB Cluster 8.0.38](https://docs.percona.com/percona-xtradb-cluster/8.0/release-notes/8.0.38.html) was skipped.

## Release highlights

Percona XtraDB Cluster is based on Percona Server for MySQL. Find a complete list of improvements and bug fixes in the [Percona Server for MySQL 8.0.39-30 (2024-10-08) release notes](https://docs.percona.com/percona-server/8.0/release-notes/8.0.39-30.html).

The release also installs Percona Telemetry. Find more information in the [Telemetry on Percona XtraDB Cluster](https://docs.percona.com/percona-xtradb-cluster/8.0/telemetry.html) document.

Improvements and bug fixes provided by Oracle for  MySQL 8.0.38 and MySQL 8.0.39 and included in Percona XtraDB Cluster are the following:

* The server could not restart successfully after creating a large number of tables (8001 or more). This issue, Bug #36808732, is a regression of Bug #33398681.

* Enhanced performance of tablespace file scanning during startup. (Bug #110402, Bug #35200385)

* InnoDB file system operations now consistently perform an fsync on the parent directory when carrying out directory-altering tasks. (Bug #36174938)

* Worker jobs now include details about the relay log file that initiated the transaction, rather than relying on the default specified by `relay_log`.

Find the complete list of bug fixes and changes in the [MySQL 8.0.38 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/news-8-0-38.html) and [MySQL 8.0.39 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/news-8-0-39.html).

## Supplied components

Review each component’s release notes for What’s new, improvements, or bug fixes. The following is a list of the components supplied with the Percona XtraDB Cluster-based variation of the Percona Distribution for MySQL:

| Component               | Version   | Description                                |
| ----------------------- | --------- | -------------------------------------------|
| Percona XtraBackup      | [8.0.35-30](https://docs.percona.com/percona-xtrabackup/8.0/release-notes/8.0/8.0.35-30.0.html)| An open-source hot backup utility for MySQL-based servers that doesn’t lock your database during the backup.|
| HAProxy                 | [2.8.11](https://git.haproxy.org/?p=haproxy-2.8.git;a=commit;h=01c1056a44823c5ffb8f74660b32c099d9b5355b) | A high-availability and load-balancing solution for Percona XtraDB Cluster. This is a default proxy.|
| ProxySQL                | [2.7.1](https://docs.percona.com/proxysql/2.7.1.html)| A high performance, high-availability, protocol-aware proxy for MySQL.          |
| Percona Toolkit         | [3.6.0](https://docs.percona.com/percona-toolkit/release_notes.html#v3-6-0-released-2024-06-12)     | The set of scripts to simplify and optimize database operation. |
| relication_manager.sh   | [1.0](./replication-manager/replication-manager-for-pxc.md)  | A tool to manage multi-source replication between multiple Percona XtraDB Cluster clusters. |
