# Percona Distribution for MySQL 8.0.26 using Percona Server for MySQL (2021-10-20)

| Release date    | October 20, 2021 |
| :-------------- | :--------------- |
|**Installation** | [Installing Percona Distribution for MySQL](installing.md)|


Percona Distribution for MySQL is a single solution with the best and most critical enterprise components from the MySQL open-source community, designed and tested to work together.

Percona Distribution for MySQL provides two deployment variants: one is based on *Percona Server for MySQL* and another one is based on *Percona XtraDB Cluster*.

This release of Percona Distribution for MySQL is focused on the *Percona Server for MySQL*-based deployment variant. It is based on [Percona Server for MySQL 8.0.26-16](https://www.percona.com/doc/percona-server/8.0/release-notes/Percona-Server-8.0.26-16.html).

## Release Highlights

The TokuDB Storage Engine has been declared deprecated starting with *Percona Server for MySQL* 8.0.26-16. The plugins are available in the binary builds and packages but are disabled. New options have been added to enable the plugins if they are needed to migrate the data to another storage engine. Read more in the [TokuDB documentation](https://www.percona.com/doc/percona-server/8.0/tokudb/tokudb_intro.html).

The following is the list of bug fixes for MySQL 8.0.26, provided by Oracle, and included in Percona Server for MySQL and Percona Distribution for MySQL:


* [#104575](http://bugs.mysql.com/bug.php?id=104575): In the PERFORMANCE_SCHEMA.Threads table, the `srv_purge_thread` and `srv_worker_thread` values are duplicated.


* [#104387](http://bugs.mysql.com/bug.php?id=104387): When using REGEX comparison, a CHARACTER_SET_MISMATCH error is thrown.


* [#104576](http://bugs.mysql.com/bug.php?id=104576): Accessing the second index in a partition table with many columns can create a high CPU load.

The following is the list of components supplied with *Percona Server for MySQL*-based deployment variant of Percona Distribution for MySQL:

| Component          | Version   | Description                                |
| ------------------- | --------- | -------------------------------------------|
| Orchestrator        | 3.2.5     | The replication topology manager for Percona Server for MySQL |
| ProxySQL            | 2.2.0     | A high performance, high-availability, protocol-aware proxy for MySQL   |
| Percona XtraBackup  | 8.0.26-17.0 | An open-source hot backup utility for MySQL-based servers       |
| Percona Toolkit     | 3.3.1     | The set of scripts to simplify and optimize database operation          |
| MySQL Shell         | 8.0.26    | An advanced client and code editor for MySQL Server       |
| MySQL Router        | 8.0.26    | Lightweight middleware that provides transparent routing between your application and back-end MySQL servers |
