# Percona Distribution for MySQL 8.4.3 using Percona XtraDB Cluster (2025-01-)

Percona Distribution for MySQL is the most stable, scalable, and secure open source MySQL distribution, with two download options: one based on Percona Server for MySQL and one based on Percona XtraDB Cluster. [Install Percona Distribution for MySQL](installing.md).

This release is based on [Percona XtraDB Cluster 8.4.3-3](https://docs.percona.com/percona-xtradb-cluster/8.4/release-notes/8.4.3-3.html).

## Release highlights

Percona XtraDB Cluster is based on Percona Server for MySQL. Find a complete list of improvements and bug fixes in the [Percona Server for MySQL 8.4.3-3 (2024-12-18) release notes](https://docs.percona.com/percona-server/8.4/release-notes/8.4.3-3.html).

## Supplied components

Review each component’s release notes for What’s new, improvements, or bug fixes. The following is a list of the components supplied with the Percona XtraDB Cluster-based variation of the Percona Distribution for MySQL:

| Component               | Version   | Description                                |
| ----------------------- | --------- | -------------------------------------------|
| Percona XtraBackup      | [8.4.0-2](https://docs.percona.com/percona-xtrabackup/8.4/release-notes/8.4.0-2.html)| An open-source hot backup utility for MySQL-based servers that doesn’t lock your database during the backup.|
| HAProxy                 | [2.8.11](https://git.haproxy.org/?p=haproxy-2.8.git;a=commit;h=01c1056a44823c5ffb8f74660b32c099d9b5355b) | A high-availability and load-balancing solution for Percona XtraDB Cluster. This is a default proxy.|
| ProxySQL                | [2.7.1-1](https://docs.percona.com/proxysql/2.7.1-1.html)| A high performance, high-availability, protocol-aware proxy for MySQL.          |
| Percona Toolkit         | [3.7.0](https://docs.percona.com/percona-toolkit/release_notes.html#v3-7-0-released-2024-12-23)     | The set of scripts to simplify and optimize database operation. |
| replication_manager.sh   | [1.0](./replication-manager/replication-manager-for-pxc.md)  | A tool to manage multi-source replication between multiple Percona XtraDB Cluster clusters. |

