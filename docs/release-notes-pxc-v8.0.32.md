# Percona Distribution for MySQL 8.0.32 using Percona XtraDB Cluster (2023-04-18)

| Release date    | April 18, 2023   |
| :-------------- | :--------------- |
|**Installation** | [Installing Percona Distribution for MySQL](installing.md)|

Percona Distribution for MySQL is the most stable, scalable and secure open-source MySQL distribution, with two download options: one based on Percona Server for MySQL and one based on Percona XtraDB Cluster.

This release is focused on the Percona XtraDB Cluster-based deployment variation. It is based on [Percona XtraDB Cluster 8.0.32-24](https://www.percona.com/doc/percona-xtradb-cluster/8.0/release-notes/8.0.32-24.html)

## Release highlights

* Percona decided to revert the following MySQL bug fix:

  The data and the GTIDs backed up by mysqldump were inconsistent when the options `--single-transaction` and `--set-gtid-purged=ON` were both used. It was because in between the transaction started by mysqldump and the fetching of GTID_EXECUTED, GTIDs on the server could have increased already. With this fixed, a FLUSH TABLES `WITH READ LOCK` is performed before the fetching of `GTID_EXECUTED` to ensure its value is consistent with the snapshot taken by mysqldump.

  The MySQL fix also added a requirement when using [--single-transaction](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_single-transaction) and executing FLUSH TABLES WITH READ LOCK for the [RELOAD](https://dev.mysql.com/doc/refman/8.0/en/privileges-provided.html#priv_reload) privilege. ([MySQL bug #109701](https://bugs.mysql.com/bug.php?id=109701), [MySQL bug #105761](https://bugs.mysql.com/bug.php?id=105761))

  The Percona Server version of the `mysqldump` utility, in some modes, can be used with MySQL Server. This utility provides a temporary workaround for the "additional RELOAD privilege" limitation introduced by Oracle MySQL Server 8.0.32. 

  For more information, see the Percona Performance Blog [A Workaround for the "RELOAD/FLUSH_TABLES privilege required" Problem When Using Oracle mysqldump 8.0.32](https://www.percona.com/blog/workaround-for-the-reload-flush_tables-privilege-required-problem-when-using-oracle-mysqldump-8-0-32/).

* The ProxySQL version is updated from 2.4.8 to [2.5.1](https://docs.percona.com/proxysql/2.5.1.html).

* The HAProxy version is updated from 2.5.12 to 2.6.12. The changes introduced by HAProxy 2.6.0 are the following:

    - The SSL engines are disabled by default. This means that the `ssl-engine` keyword does not work. The `ssl-engine` keyword may be re-enabled by building with "USE_ENGINE=1" and ignoring the warnings. 

    - openssl 0.9.8 is no longer supported.

    - The HTTP version in HTTP/1.1 requests does not accept `Real Time Streaming Protocol (RTSP)` unless you use the `accept-invalid-http-requests` option. 

    - A `h1-accept-payload-with-any-method` global directive is added. This global directive allows users using HTTP/1.0 to send a payload with `GET`, `HEAD`, and `DELETE` requests. 

    Find the full list of changes in the [HAProxy 2.6.12 release notes](https://git.haproxy.org/?p=haproxy-2.6.git;a=commit;h=f5884628ed25777fbffe9e3f097ffeff60e1fd1c), [Announcing HAProxy 2.6 blog post](https://www.haproxy.com/blog/announcing-haproxy-2-6/), and in the [HAProxy 2.6.0 release announce](https://www.mail-archive.com/haproxy@formilux.org/msg42371.html).

Improvements and bug fixes introduced by Oracle for MySQL 8.0.32 and included in Percona XtraDB Cluster and Percona Distribution for MySQL are the following:

* A replica can add a Generated Invisible Primary Keys(GIPK) to any InnoDB table. To achieve this behavior, the `GENERATE` value is added as a possible value for the `CHANGE REPLICATION SOURCE TO` statement’s `REQUIRE_TABLE_PRIMARY_KEY_CHECK` option.

* The `REQUIRE_TABLE_PRIMARY_KEY_CHECK = GENERATE` option can be used on a per-channel basis.

* Setting `sql_generate_invisible_primary_key` on the source is ignored by a replica because this variable is not replicated. This behavior is inherited from the previous releases.

* An upgrade from 8.0.28 caused undetectable problems, such as server exit and corruption.

* A fix for after an upgrade, all columns added with `ALGORITHM=INSTANT` materialized and have `version=0` for any new row inserted. Now, a column added with `ALGORITHM=INSTANT` fails if the maximum possible size of a row exceeds the row size limit, so that all new rows with materialized `ALGORITHM=INSTANT` columns are within row size limit. (Bug #34558510)

* After a drop, adding a specific column using the INSTANT algorithm could cause a data error and a server exit. (Bug #34122122)

* An online rebuild DDL no longer crashes after a column is added with `ALGORITHM=INSTANT`. Thank you Qingda Hu for reporting this bug. (Bug #33788578, Bug #106279)

Find the full list of bug fixes and changes in the [MySQL 8.0.32 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/news-8-0-32.html).

## Supplied components

Review each component’s release notes for What’s new, improvements, or bug fixes. The following is a list of the components supplied with the Percona XtraDB Cluster-based variation of the Percona Distribution for MySQL:

| Component               | Version   | Description                                |
| ----------------------- | --------- | -------------------------------------------|
| Percona XtraBackup      | [8.0.32-26](https://docs.percona.com/percona-xtrabackup/8.0/release-notes/8.0/8.0.32-26.0.html)| An open-source hot backup utility for MySQL-based servers that doesn’t lock your database during the backup.|
| HAProxy                 | [2.6.12](https://git.haproxy.org/?p=haproxy-2.6.git;a=commit;h=f5884628ed25777fbffe9e3f097ffeff60e1fd1c) | A high-availability and load-balancing solution for Percona XtraDB Cluster. This is a default proxy.|
| ProxySQL                | [2.5.1](https://docs.percona.com/proxysql/2.5.1.html)| A high performance, high-availability, protocol-aware proxy for MySQL.          |
| Percona Toolkit         | [3.5.2](https://docs.percona.com/percona-toolkit/release_notes.html#v3-5-2-released-2023-03-28)     | The set of scripts to simplify and optimize database operation. |
| relication_manager.sh   | [1.0](./replication-manager/replication-manager-for-pxc.md)  | A tool to manage multi-source replication between multiple Percona XtraDB Cluster clusters. |
