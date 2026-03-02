# Percona Distribution for MySQL 8.0.45 using Percona XtraDB Cluster (2026-03-02)

Percona Distribution for MySQL is more than just a version of MySQL; it is a comprehensive solution that combines Percona Server for MySQL with additional tools to create a cohesive environment. This distribution is reliable, scalable, and secure, ensuring that all components have been tested to work seamlessly together. You can choose from two download options: one that uses Percona Server for MySQL and another that utilizes Percona XtraDB Cluster. Refer to [Install Percona Distribution for MySQL](installing.md).

This release is focused on the Percona XtraDB Cluster-based deployment variation. It is based on [Percona XtraDB Cluster 8.0.45-35](https://docs.percona.com/percona-xtradb-cluster/8.0/release-notes/8.0.45-36.html).

## Release highlights

Improvements and bug fixes provided by Oracle for MySQL 8.0.45 and included in Percona Server for MySQL are documented in the [MySQL 8.0.45 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/news-8-0-45.html).

## Supplied components

Review each component’s release notes for What’s new, improvements, or bug fixes. The following is a list of the components supplied with the Percona XtraDB Cluster-based variation of the Percona Distribution for MySQL:

| Component               | Version   | Description                                |
| ----------------------- | --------- | -------------------------------------------|
| Percona XtraBackup      | [8.0.35-35](https://docs.percona.com/percona-xtrabackup/8.0/release-notes/8.0/8.0.35-35.0.html)| An open-source hot backup utility for MySQL-based servers that doesn’t lock your database during the backup.|
| HAProxy                 | [2.8.18](https://git.haproxy.org/?p=haproxy-2.8.git;a=commit;h=b6e928141b16d2a5adbfa331e0639fa02305fc8a) | A high-availability and load-balancing solution for Percona XtraDB Cluster. This is a default proxy.|
| ProxySQL                | [2.7.3](https://docs.percona.com/proxysql/2.7.3.html)| A high performance, high-availability, protocol-aware proxy for MySQL.          |
| Percona Toolkit         | [3.7.1](https://docs.percona.com/percona-toolkit/release_notes.html#v3-7-1-released-2025-12-17)     | The set of scripts to simplify and optimize database operation. |
| relication_manager.sh   | [1.0](https://docs.percona.com/percona-distribution-for-mysql/8.0/replication-manager/replication-manager-for-pxc.html)  | A tool to manage multi-source replication between multiple Percona XtraDB Cluster clusters. |
