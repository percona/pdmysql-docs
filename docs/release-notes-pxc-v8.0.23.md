# Percona Distribution for MySQL 8.0.23 using Percona XtraDB Cluster (2021-06-09)


| Release date    | June 09, 2021 |
| :-------------- | :--------------- |
|**Installation** | [Installing Percona Distribution for MySQL](installing.md)|



Percona Distribution for MySQL is a single solution with the best and most critical enterprise components from the MySQL open source community, designed and tested to work together.

Percona Distribution for MySQL provides two deployment variants: one is based on *Percona Server for MySQL* and another one is based on *Percona XtraDB Cluster*.

This release of Percona Distribution for MySQL is focused on the *Percona XtraDB Cluster*-based deployment variant. It is based on [Percona XtraDB Cluster 8.0.23-14.1](https://www.percona.com/doc/percona-xtradb-cluster/8.0/release-notes/Percona-XtraDB-Cluster-8.0.23-14.1.html) and includes the following components:

| Component          | Version   | Description                                |
| ------------------ | --------- | -------------------------------------------|
| *Percona XtraBackup* | 8.0.23  | An open-source hot backup utility for MySQL-based servers that doesn’t lock your database during the backup. |
| HAProxy            | 2.3.10    | A high-availability and load-balancing solution for Percona XtraDB Cluster. This is a default proxy.          |
| ProxySQL           | 2.0.18    | A high performance, high-availability, protocol-aware proxy for MySQL.  |
| Percona Toolkit    | 3.3.1     | The set of scripts to simplify and optimize database operation.|
