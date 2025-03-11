# Percona Distribution for MySQL 8.0.41 using Percona XtraDB Cluster (2025-03-)

Percona Distribution for MySQL is more than just a version of MySQL; it is a comprehensive solution that combines Percona Server for MySQL with additional tools to create a cohesive environment. This distribution is reliable, scalable, and secure, ensuring that all components have been tested to work seamlessly together. You can choose from two download options: one that uses Percona Server for MySQL and another that utilizes Percona XtraDB Cluster. Refer to [Install Percona Distribution for MySQL](installing.md).

This release is focused on the Percona XtraDB Cluster-based deployment variation. It is based on [Percona XtraDB Cluster 8.0.41-32](https://docs.percona.com/percona-xtradb-cluster/8.0/release-notes/8.0.41-32.html).

## Release highlights

Percona XtraDB Cluster is based on Percona Server for MySQL. Find a complete list of improvements and bug fixes in the [Percona Server for MySQL 8.0.41-32 (2025-03-) release notes](https://docs.percona.com/percona-server/8.0/release-notes/8.0.41-32.html).

### Percona XtraDB Cluster 8.0.41-32

Implements the [Clone plugin for State Snapshot Transfer (SST) Method](https://docs.percona.com/percona-xtradb-cluster/8.0/clone-sst.html). The Clone SST is a modern and efficient method that leverages MySQL's native cloning capabilities to transfer data from a donor node to a Joiner node. It is faster and more resource-efficient compared to traditional methods like xtrabackup or rsync.

### Percona Server for MySQL 8.0.41-32

* Extends the [Encryption user-defined functions](https://docs.percona.com/percona-server/8.0/encryption-functions.html) with the following:

     * Added support for `pkcs1`, `oaep`, or `no` padding for RSA encrypt and decrypt operations

     * Added support for `pkcs1` or `pkcs1_pss` padding for RSA sign and verify operations

     * Added the `encryption_udf.legacy_padding_scheme` system variable to manage legacy padding schemes

     * Added the character set awareness

* Improves the [Data masking](https://docs.percona.com/percona-server/8.0/data-masking-overview.html) performance by introducing an internal term cache. The new cache speeds up lookups for `gen_blocklist()` and `gen_dictionary()` functions by storing dictionary data in memory.

    Find more detailed information in the [Data masking overview](https://docs.percona.com/percona-server/8.0/data-masking-overview.html) and in the [Data masking component functions](https://docs.percona.com/percona-server/8.0/data-masking-function-list.html).

### MySQL 8.0.41

Improvements and bug fixes provided by Oracle for MySQL 8.0.41 and included in Percona Server for MySQL are the following:

* Fixed an assertion in debug builds where certain IO buffer serializations caused system hangs. (Bug #37139618)

* Resolved a failure when dropping the primary key and adding a new `AUTO_INCREMENT` column as the primary key in descending order using the `INPLACE` algorithm resulted in failure. (Bug #36658450)

* Fixed incorrect results, including missing rows, in queries that used a descending primary key with the `index_merge` optimization. (Bug #106207, Bug #33767814)

* Addressed a replication channel issue where MySQL failed to stop the channel properly when large transactions were being processed, and `STOP REPLICA` was requested. This issue also prevented graceful server shutdown, requiring process termination or system restart. (Bug #115966, Bug #37008345)

Find the complete list of bug fixes and changes in the [MySQL 8.0.41 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/news-8-0-41.html).

## Supplied components

Review each component’s release notes for What’s new, improvements, or bug fixes. The following is a list of the components supplied with the Percona XtraDB Cluster-based variation of the Percona Distribution for MySQL:

| Component               | Version   | Description                                |
| ----------------------- | --------- | -------------------------------------------|
| Percona XtraBackup      | [8.0.35-32](https://docs.percona.com/percona-xtrabackup/8.0/release-notes/8.0/8.0.35-32.0.html)| An open-source hot backup utility for MySQL-based servers that doesn’t lock your database during the backup.|
| HAProxy                 | [2.8.14](https://git.haproxy.org/?p=haproxy-2.8.git;a=commit;h=c23fe91db3ae6b3b80b5f08774e41730cbba13fb) | A high-availability and load-balancing solution for Percona XtraDB Cluster. This is a default proxy.|
| ProxySQL                | [2.7.1-1](https://docs.percona.com/proxysql/2.7.1-1.html)| A high performance, high-availability, protocol-aware proxy for MySQL.          |
| Percona Toolkit         | [3.7.0](https://docs.percona.com/percona-toolkit/release_notes.html#v3-7-0-released-2024-12-23)     | The set of scripts to simplify and optimize database operation. |
| relication_manager.sh   | [1.0](./replication-manager/replication-manager-for-pxc.md)  | A tool to manage multi-source replication between multiple Percona XtraDB Cluster clusters. |
