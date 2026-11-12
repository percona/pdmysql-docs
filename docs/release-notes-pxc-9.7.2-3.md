# Percona Distribution for MySQL 9.7.2-3 using Percona XtraDB Cluster (2026-11-12)

Percona Distribution for MySQL is more than just a version of MySQL; it is a comprehensive solution that combines Percona Server for MySQL with additional tools to create a cohesive environment. This distribution is reliable, scalable, and secure, ensuring that all components have been tested to work seamlessly together. You can choose from two download options: one that uses Percona Server for MySQL and another that utilizes Percona XtraDB Cluster. Refer to [Install Percona Distribution for MySQL](installing.md).

This release is based on [Percona XtraDB Cluster 9.7.3-3](https://docs.percona.com/percona-xtradb-cluster/9.7/release-notes/9.7.3-3.html).

!!! note "A note on MySQL 9.7.3"

    Percona Distribution for MySQL 9.7.2-3 is not based on the MySQL 9.7.3 release. MySQL 9.7.3 is a Critical Security Patch Update (CSPU) — a targeted security release that Oracle can issue between quarterly Critical Patch Updates (CPUs) when needed. The MySQL 9.7.3 CSPU applies to the MySQL Server Docker image only, and its fixes do not affect Percona XtraDB Cluster.

## Release highlights

Percona XtraDB Cluster 9.7.3-3 includes the following fix from [Percona Server for MySQL 9.7.3-3](https://docs.percona.com/percona-server/9.7/release-notes/9.7.3-3.html):

* [PS-11950](https://perconadev.atlassian.net/browse/PS-11950): `mysqldump` did not always dump tables with compressed columns correctly. If a column comment or another quoted string in the table definition contained text that looked like a compressed column attribute, `mysqldump` changed the table definition in the dump, so it was different from the original table. `mysqldump` also did not correctly dump or restore some compression dictionaries, such as dictionaries with names containing quotes, spaces, reserved words or non-ASCII characters, or with non-ASCII data.

## Supplied components

Review each component’s release notes for What’s new, improvements, or bug fixes. The following is a list of the components supplied with the Percona XtraDB Cluster-based variation of the Percona Distribution for MySQL:

| Component               | Version   | Description                                |
| ----------------------- | --------- | -------------------------------------------|
| Percona XtraBackup      | [9.7.1-rc1](https://docs.percona.com/percona-xtrabackup/9.7/release-notes/9.7.1-rc1.html)| An open-source hot backup utility for MySQL-based servers that doesn’t lock your database during the backup.|
| HAProxy                 | [3.4.7](https://git.haproxy.org/?p=haproxy-3.4.git;a=commit;h=8872a2604595140544774c2a6309a41186fc0f44) | A high-availability and load-balancing solution for Percona XtraDB Cluster. This is a default proxy.|
| ProxySQL                | [3.0.9](https://docs.percona.com/proxysql/3.0.9.html)| A high performance, high-availability, protocol-aware proxy for MySQL.|
| Percona Toolkit         | [3.7.2](https://docs.percona.com/percona-toolkit/release_notes.html#v3-7-2-released-2026-10-22)     | The set of scripts to simplify and optimize database operation. |
| replication_manager.sh   | [1.0](https://docs.percona.com/percona-distribution-for-mysql/9.7/replication-manager-for-pxc.html)  | A tool to manage multi-source replication between multiple Percona XtraDB Cluster clusters. |
