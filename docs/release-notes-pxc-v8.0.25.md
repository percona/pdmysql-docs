# Percona Distribution for MySQL 8.0.25 using Percona XtraDB Cluster (2021-11-22)

| Release date    | November 22, 2021 |
| :-------------- | :--------------- |
|**Installation** | [Installing Percona Distribution for MySQL](installing.md)|


Percona Distribution for MySQL is a single solution with the best and most critical enterprise components from the MySQL open source community, designed and tested to work together.

Percona Distribution for MySQL provides two deployment variants: one is based on *Percona Server for MySQL* and another one is based on *Percona XtraDB Cluster*.

This release of Percona Distribution for MySQL is focused on the *Percona XtraDB Cluster*-based deployment variant. It is based on [Percona XtraDB Cluster 8.0.25-15.1](https://www.percona.com/doc/percona-xtradb-cluster/8.0/release-notes/Percona-XtraDB-Cluster-8.0.25-15.1.html)

## Release Highlights

A [Non-Blocking Operation mode](https://www.percona.com/doc/percona-xtradb-cluster/8.0/features/nbo.html) for the Online Schema Upgrades in Percona XtraDB Cluster. This mode is similar to the Total Order Isolation (TOI) mode, whereas the data definition language (DDL) statement (e.g., ALTER) is executed on all nodes in sync. The difference is that in the NBO mode, the DDL statement acquires a metadata lock that locks the table or schema at a late stage of the operation, which is a more efficient locking strategy.

Note that the NBO mode is a tech preview feature. Therefore, we recommend using it in testing environments only.

The following is the list of the notable fixes for MySQL 8.0.25, provided by Oracle, and included in *Percona XtraDB Cluster* and Percona Distribution for MySQL:


* [#103980](http://bugs.mysql.com/bug.php?id=103980): Fixes the allocation of too much memory when dropping a database with many partitioned tables.


* [#103743](http://bugs.mysql.com/bug.php?id=103743): Fixes a slow startup when the tables are encrypted.

The following is the list of components supplied with the *Percona XtraDB Cluster*-based deployment variant of Percona Distribution for MySQL:

| Component          | Version   | Description                                |
| ------------------ | --------- | -------------------------------------------|
| Percona XtraBackup | 8.0.25    | An open-source hot backup utility for MySQL-based servers that doesn’t lock your database during the backup. |
| HAProxy            | 2.3.14    | A high-availability and load-balancing solution for Percona XtraDB Cluster. This is a default proxy.         |
| ProxySQL           | 2.0.18    | A high performance, high-availability, protocol-aware proxy for MySQL. |
| Percona Toolkit    | 3.3.1     | The set of scripts to simplify and optimize database operation.       |
