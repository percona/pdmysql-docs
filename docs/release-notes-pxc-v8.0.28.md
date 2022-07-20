# Percona Distribution for MySQL 8.0.28 using Percona XtraDB Cluster (2022-07-19)

| Release date    | July 19, 2022 |
| :-------------- | :--------------- |
|**Installation** | [Installing Percona Distribution for MySQL](installing.md)|

Percona Distribution for MySQL is a single solution with the most critical enterprise components from the MySQL open source community, designed and tested to work together.

Percona Distribution for MySQL provides two deployment variants: one is based on *Percona Server for MySQL* and another one is based on *Percona XtraDB Cluster*. 

This release of Percona Distribution for MySQL is focused on the *Percona XtraDB Cluster*-based deployment variant. It is based on [Percona XtraDB Cluster 8.0.28-19.1](https://www.percona.com/doc/percona-xtradb-cluster/8.0/release-notes/Percona-XtraDB-Cluster-8.0.28-19.1.html)

## Release Highlights

The following lists a number of the bug fixes for *MySQL* 8.0.28, provided by Oracle, and included in Percona XtraDB Cluster and Percona Distribution for MySQL:


* The ``ASCII`` shortcut for ``CHARACTER SET latin1`` and ``UNICODE`` shortcut for ``CHARACTER SET ucs2`` are deprecated and raise a warning to use ``CHARACTER SET`` instead. The shortcuts will be removed in a future version.
* A stored function and a loadable function with the same name can share the same namespace. Add the schema name when invoking a stored function in the shared namespace. The server generates a warning when function names collide.
* InnoDB supports ``ALTER TABLE ... RENAME COLUMN`` operations when using ``ALGORITHM=INSTANT``. 
* The limit for ``innodb_open_files`` now includes temporary tablespace files. The temporary tablespace files were not counted in the ``innodb_open_files`` in previous versions. 

Find the full list of bug fixes and changes in the [MySQL 8.0.28 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/news-8-0-28.html).

The following is the list of components supplied with the *Percona XtraDB Cluster*-based deployment variant of Percona Distribution for MySQL:

| Component           | Version   | Description                                |
| ------------------- | --------- | -------------------------------------------|
| Percona XtraBackup  | [8.0.28](https://docs.percona.com/percona-xtrabackup/8.0/release-notes/8.0/8.0.28-21.0.html)    | An open-source hot backup utility for MySQL-based servers that doesn’t lock your database during the backup.|
| HAProxy             | [2.5.6](http://git.haproxy.org/?p=haproxy-2.5.git;a=commit;h=ba44b431294b6ddb65d5841632789dabf253439d) | A high-availability and load-balancing solution for Percona XtraDB Cluster. This is a default proxy.|
| ProxySQL            | [2.3.2](https://docs.percona.com/proxysql/release-notes-2.3.2-1.html)     | A high performance, high-availability, protocol-aware proxy for MySQL.          |
| Percona Toolkit     | [3.4.0](https://www.percona.com/doc/percona-toolkit/LATEST/release_notes.html#v3-4-0-released-)     | The set of scripts to simplify and optimize database operation. |
