# Percona Distribution for MySQL 8.0.29 using Percona XtraDB Cluster (2022-09-12)

| Release date    | September 12, 2022 |
| :-------------- | :--------------- |
|**Installation** | [Installing Percona Distribution for MySQL](installing.md)|

Percona Distribution for MySQL is a single solution with the most critical enterprise components from the MySQL open source community, designed and tested to work together.

Percona Distribution for MySQL provides two deployment variants: one is based on *Percona Server for MySQL* and another one is based on *Percona XtraDB Cluster*. 

This release of Percona Distribution for MySQL is focused on the *Percona XtraDB Cluster*-based deployment variant. It is based on [Percona XtraDB Cluster 8.0.29-21](https://www.percona.com/doc/percona-xtradb-cluster/8.0/release-notes/8.0.29-21.html)

## Release Highlights

The following lists a number of the bug fixes for *MySQL* 8.0.29, provided by Oracle, and included in Percona XtraDB Cluster and Percona Distribution for MySQL:

* The Performance Schema tracks if a query was processed on the PRIMARY engine, InnoDB, or a SECONDARY engine, HeatWave. An `EXECUTION_ENGINE` column, which indicates the engine used, was added to the Performance Schema statement event tables and the `sys.processlist` and the `sys.x$processlist` views.

* Added support for the `IF NOT EXISTS` option for the `CREATE FUNCTION`, `CREATE PROCEDURE`, and `CREATE TRIGGER` statements.

* Added support for `ALTER TABLE … DROP COLUMN ALGORITHM=INSTANT`.

* An anonymous user with the `PROCESS` privilege was unable to select processlist table rows.

Find the full list of bug fixes and changes in the [MySQL 8.0.29 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/news-8-0-29.html).

!!! note

    Percona Server for MySQL has changed the default for the [supported DDL column operations](https://dev.mysql.com/doc/refman/8.0/en/innodb-online-ddl-operations.html) to ALGORITHM=INPLACE. This change fixes the corruption issue with the INSTANT ADD/DROP COLUMNS (find more details in [PS-8292](https://jira.percona.com/browse/PS-8292)).

    In MySQL 8.0.29, the default setting for supported DDL operations is ALGORITHM=INSTANT. You can explicitly specify ALGORITHM=INSTANT in DDL column operations.

    For more information, see [Percona Blog: Percona XtraBackup 8.0.29 and INSTANT ADD/DROP Columns](https://www.percona.com/blog/percona-xtrabackup-8-0-29-and-instant-add-drop-columns/). 

The following is the list of components supplied with the *Percona XtraDB Cluster*-based deployment variant of Percona Distribution for MySQL:

| Component           | Version   | Description                                |
| ------------------- | --------- | -------------------------------------------|
| Percona XtraBackup  | [8.0.29](https://docs.percona.com/percona-xtrabackup/8.0/release-notes/8.0/8.0.29-22.0.html)    | An open-source hot backup utility for MySQL-based servers that doesn’t lock your database during the backup.|
| HAProxy             | [2.5.6](http://git.haproxy.org/?p=haproxy-2.5.git;a=commit;h=ba44b431294b6ddb65d5841632789dabf253439d) | A high-availability and load-balancing solution for Percona XtraDB Cluster. This is a default proxy.|
| ProxySQL            | [2.4.3](https://docs.percona.com/proxysql/2.4.3.html)| A high performance, high-availability, protocol-aware proxy for MySQL.          |
| Percona Toolkit     | [3.4.0](https://docs.percona.com/percona-toolkit/release_notes.html#v3-4-0-released-2022-07-11)     | The set of scripts to simplify and optimize database operation. |
