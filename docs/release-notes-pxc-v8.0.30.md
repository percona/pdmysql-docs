# Percona Distribution for MySQL 8.0.30 using Percona XtraDB Cluster (2022-12-28)

| Release date    | December 28, 2022 |
| :-------------- | :--------------- |
|**Installation** | [Installing Percona Distribution for MySQL](installing.md)|

Percona Distribution for MySQL is a single solution with the most critical enterprise components from the MySQL open source community, designed and tested to work together.

Percona Distribution for MySQL provides two deployment variants: one is based on *Percona Server for MySQL* and another one is based on *Percona XtraDB Cluster*. 

This release of Percona Distribution for MySQL is focused on the *Percona XtraDB Cluster*-based deployment variant. It is based on [Percona XtraDB Cluster 8.0.30-22](https://www.percona.com/doc/percona-xtradb-cluster/8.0/release-notes/8.0.30-22.html)

## Release highlights

The following lists a number of the bug fixes for *MySQL* 8.0.30, provided by Oracle, and included in Percona XtraDB Cluster and Percona Distribution for MySQL:

* Supports Generated Invisible Primary Keys(GIPK). This feature automatically adds a primary key to InnoDB tables without a primary key. The generated key is always named `my_row_id`. The GIPK feature is not enabled by default. Enable the feature by setting `sql_generate_invisible_primary_key` to ON.

* The InnoDB_doublewrite system has two new settings:

  * `DETECT_ONLY`. This setting allows only metadata to be written to the doublewrite buffer. Database page content is not written to the buffer. Recovery does not use the buffer to fix incomplete page writes. Use this setting only when you need to detect incomplete page writes.

  * `DETECT_AND_RECOVER`. This setting is equivalent to the current ON setting. The doublewrite buffer is enabled. Database page content is written to the buffer and the buffer is accessed to fix incomplete page writes during recovery.

* The `--skip_host_cache` server option is deprecated and will be removed in a future release. Use `SET GLOBAL host_cache_size`= 0 or set `host_cache_size` = 0.

Find the full list of bug fixes and changes in the [MySQL 8.0.30 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/news-8-0-30.html).

!!! note

    The following Percona Server for MySQL 8.0.30 features are not supported in Percona XtraDB Cluster 8.0.30-22: 

    * [Amazon Key Management Service](https://docs.percona.com/percona-server/8.0/security/using-amz-kms.html)
  
    * [Key Management Interoperability Protocol](https://docs.percona.com/percona-server/8.0/security/using-kmip.html)

    The features will be supported in the next version of Percona XtraDB Cluster.

### Replication manager for Percona XtraDB Cluster

[PXC-4062](https://jira.percona.com/browse/PXC-4062): The [Replication manager for Percona XtraDB Cluster](replication-manager/replication-manager-for-pxc.md) is a [tech preview](glossary.md#tech-preview) feature. The replication manager helps manage [multi-source replication](glossary.md#multi-source-replication) between multiple Percona XtraDB Cluster clusters. To manage a single replica, use [Single replica manager for Percona XtraDB Cluster](replication-manager/single-replica-manager.md).

The following is the list of components supplied with the *Percona XtraDB Cluster*-based deployment variant of Percona Distribution for MySQL:

| Component           | Version   | Description                                |
| ------------------- | --------- | -------------------------------------------|
| Percona XtraBackup  | [8.0.30-23](https://docs.percona.com/percona-xtrabackup/8.0/release-notes/8.0/8.0.30-23.0.html)| An open-source hot backup utility for MySQL-based servers that doesn’t lock your database during the backup.|
| HAProxy             | [2.5.10](http://git.haproxy.org/?p=haproxy-2.5.git;a=commit;h=4b0891f385a53f5fa195c21260b289ee2a0c95e0) | A high-availability and load-balancing solution for Percona XtraDB Cluster. This is a default proxy.|
| ProxySQL            | [2.4.4](https://docs.percona.com/proxysql/2.4.4.html)| A high performance, high-availability, protocol-aware proxy for MySQL.          |
| Percona Toolkit     | [3.5.0](https://docs.percona.com/percona-toolkit/release_notes.html#v3-5-0-released-2022-11-28)     | The set of scripts to simplify and optimize database operation. |
