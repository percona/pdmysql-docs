# Percona Distribution for MySQL 8.0.36 using Percona XtraDB Cluster (2024-04-03)

Percona Distribution for MySQL is the most stable, scalable and secure open-source MySQL distribution, with two download options: one based on Percona Server for MySQL and one based on Percona XtraDB Cluster. [Install Percona Distribution for MySQL](installing.md).

This release is focused on the Percona XtraDB Cluster-based deployment variation. It is based on [Percona XtraDB Cluster 8.0.36](https://docs.percona.com/percona-xtradb-cluster/8.0/release-notes/8.0.36-28.html)

## Release highlights

Improvements and bug fixes provided by Oracle for MySQL 8.0.36 and included in Percona XtraDB Cluster are the following:

* The hashing algorithm employed yielded poor performance when using a HASH field to check for uniqueness. (Bug #109548, Bug #34959356)

* All [statement instrument elements] that begin with `statement/sp/%`, except `statement/sp/stmt`, are disabled by default.

Find the complete list of bug fixes and changes in the [MySQL 8.0.36 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/news-8-0-36.html).

## Supplied components

Review each component’s release notes for What’s new, improvements, or bug fixes. The following is a list of the components supplied with the Percona XtraDB Cluster-based variation of the Percona Distribution for MySQL:

| Component               | Version   | Description                                |
| ----------------------- | --------- | -------------------------------------------|
| Percona XtraBackup      | [8.0.35-30](https://docs.percona.com/percona-xtrabackup/8.0/release-notes/8.0/8.0.35-30.0.html)| An open-source hot backup utility for MySQL-based servers that doesn’t lock your database during the backup.|
| HAProxy                 | [2.8.5](https://git.haproxy.org/?p=haproxy-2.8.git;a=commit;h=aaba8d090ec663906af1fecbad83c26bbccf0761) | A high-availability and load-balancing solution for Percona XtraDB Cluster. This is a default proxy.|
| ProxySQL                | [2.5.0](https://docs.percona.com/proxysql/2.5.0.html)| A high performance, high-availability, protocol-aware proxy for MySQL.          |
| Percona Toolkit         | [3.5.7](https://docs.percona.com/percona-toolkit/release_notes.html#v3-5-7-released-2023-12-23)     | The set of scripts to simplify and optimize database operation. |
| relication_manager.sh   | [1.0](./replication-manager/replication-manager-for-pxc.md)  | A tool to manage multi-source replication between multiple Percona XtraDB Cluster clusters. |
