# Percona Distribution for MySQL 8.0.29 using Percona Server for MySQL (2022-08-09)

| Release date    | August 8, 2022 |
| :-------------- | :--------------- |
|**Installation** | [Installing Percona Distribution for MySQL](installing.md)|


Percona Distribution for MySQL is a single solution with the best and most critical enterprise components from the MySQL open-source community, designed and tested to work together.

Percona Distribution for MySQL provides two deployment variants: one is based on *Percona Server for MySQL* and another one is based on *Percona XtraDB Cluster*.

This release is focused on the *Percona Server for MySQL*-based deployment variant. It is based on [Percona Server for MySQL 8.0.29-21](https://www.percona.com/doc/percona-server/8.0/release-notes/8.0.29-21.html).

## Release Highlights

The following lists a number of the bug fixes for *MySQL* 8.0.29, provided by Oracle, and included in Percona Server for MySQL and Percona Distribution for MySQL:


* The Performance Schema tracks if a query was processed on the PRIMARY engine, InnoDB, or a SECONDARY engine, HeatWave. An EXECUTION_ENGINE column, which indicates the engine used, was added to the Performance Schema statement event tables and the `sys.processlist` and the `sys.x$processlist` views.
* Added support for the `IF NOT EXISTS` option for the `CREATE FUNCTION`, `CREATE PROCEDURE`, and `CREATE TRIGGER` statements.
* Added support for `ALTER TABLE ... DROP COLUMN ALGORITHM=INSTANT`. 
* An anonymous user with the `PROCESS` privilege was unable to select `processlist` table rows.

Find the full list of bug fixes and changes in the [MySQL 8.0.29 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/news-8-0-29.html).

!!! note

    Percona Server for MySQL has changed the default for [supported DDL column operations](https://dev.mysql.com/doc/refman/8.0/en/innodb-online-ddl-operations.html) to `ALGORITHM=INPLACE`. This fixes  corruption issue and several other issues with the INSTANT ADD/DROP COLUMN DDL (Find more details in [PS-8292](https://jira.percona.com/browse/PS-8292), [PS-8291](https://jira.percona.com/browse/PS-8291) and [PS-8303](https://jira.percona.com/browse/PS-8303)).

    In MySQL 8.0.29, the default setting for supported DDL operations is `ALGORITHM=INSTANT`. You can explicitly specify `ALGORITHM=INSTANT` in DDL column operations. 

    For more information, see [Percona Blog: Percona XtraBackup 8.0.29 and INSTANT ADD/DROP Columns](https://www.percona.com/blog/percona-xtrabackup-8-0-29-and-instant-add-drop-columns/). 

## Orchestrator

* [DISTMYSQL-198](https://jira.percona.com/browse/DISTMYSQL-198): orchestrator client packages were missing for RPM based distributions. Starting from v8.0.29 they are now built and available for download.
* [DISTMYSQL-197](https://jira.percona.com/browse/DISTMYSQL-197): Option `--version` now returns a more understandable version number (in addition to the commit hash).

## Packaging Notes

Debian 9 (“Stretch”) is no longer supported.  To learn more, see [Percona Blog: OS Platform End of Life (EOL) Announcement for Debian Linux 9](https://www.percona.com/blog/os-platform-end-of-life-eol-announcement-for-debian-linux-9/)  


---

The following is the list of components supplied with *Percona Server for MySQL*-based deployment variant of Percona Distribution for MySQL:

| Component           | Version   | Description                                |
| ------------------- | --------- | -------------------------------------------|
| Orchestrator        | [3.2.6-3](https://github.com/percona/orchestrator/releases/tag/v3.2.6-3)     | The replication topology manager for Percona Server for MySQL|
| ProxySQL            | [2.3.2](https://docs.percona.com/proxysql/release-notes-2.3.2-1.html)     | A high performance, high-availability, protocol-aware proxy for MySQL|
| Percona XtraBackup  | [8.0.29-22](https://docs.percona.com/percona-xtrabackup/latest/release-notes/8.0/8.0.29-22.0.html)| An open-source hot backup utility for MySQL-based servers|
| Percona Toolkit     | 3.4.0     | The set of scripts to simplify and optimize database operation|
| MySQL Shell         | [8.0.29](https://dev.mysql.com/doc/relnotes/mysql-shell/8.0/en/news-8-0-29.html)    | An advanced client and code editor for MySQL Server|
| MySQL Router        | [8.0.29](https://dev.mysql.com/doc/relnotes/mysql-router/en/news-8-0-29.html)    | Lightweight middleware that provides transparent routing between your application and back-end MySQL servers|
