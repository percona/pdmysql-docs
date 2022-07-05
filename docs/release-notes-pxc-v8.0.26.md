# Percona Distribution for MySQL 8.0.26 using Percona XtraDB Cluster (2022-01-17)

| Release date    | January 17, 2022 |
| :-------------- | :--------------- |
|**Installation** | [Installing Percona Distribution for MySQL](installing.md)|



Percona Distribution for MySQL is a single solution with the best and most critical enterprise components from the MySQL open source community, designed and tested to work together.

Percona Distribution for MySQL provides two deployment variants: one is based on *Percona Server for MySQL* and another one is based on *Percona XtraDB Cluster*.

This release of Percona Distribution for MySQL is focused on the *Percona XtraDB Cluster*-based deployment variant. It is based on [Percona XtraDB Cluster 8.0.26-16.1](https://www.percona.com/doc/percona-xtradb-cluster/8.0/release-notes/Percona-XtraDB-Cluster-8.0.26-16.1.html)

## Release Highlights

The following are some of the notable fixes for MySQL 8.0.26, provided by Oracle, and included in Percona XtraDB Cluster and Percona Distribution for MySQL:


* The [TLSv1 and TLSv1.1](https://tools.ietf.org/id/draft-ietf-tls-oldversions-deprecate-02.html) connection protocols are deprecated.


* Identifiers with specific terms, such as “master” or “slave” are deprecated and replaced. See the [Functionality Added or Changed section in the 8.0.26 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/news-8-0-26.html#mysqld-8-0-26-feature) for a list of updated identifiers.

    The following terms have been changed:

    * The identifier `master` is changed to `source`
    * The identifier `slave` is changed to `replica`
    * The identifier `multithreaded slave` (`mts`) is changed to `multithreaded applier` (`mta`)

* When using semisynchronous replication, either the old version or the new version of system variables and status variables are available. You cannot have both versions installed on an instance. Be aware, the new system variables are available when you use the new version, but the old values are not. The old system variables are available when you use the old version, but the new ones are not.

In an update to 8.0.26, enable the `rpl_semi_sync_source` plugin and the `rpl_semi_sync_replica` plugin after the update has completed. Enabling these plugins before all of the nodes are updated may cause data inconsistency between the nodes.

The names are the following:

* For the source, the `rpl_semi_sync_master` plugin (`seminsync_master.so` library) is the old version and the `rpl_semi_sync_source` plugin(`semisync_source.so` library) is the new version.
* For the client, the `rpl_semi_sync_slave` plugin (`semisync_slave.so` library) is the old version and the `rpl_semi_sync_replica` plugin (`semisync_replica.so` library) is the new version.

The following is the list of components supplied with the *Percona XtraDB Cluster*-based deployment variant of Percona Distribution for MySQL:

| Component           | Version   | Description                                |
| ------------------- | --------- | -------------------------------------------|
| Percona XtraBackup  | 8.0.26    | An open-source hot backup utility for MySQL-based servers that doesn’t lock your database during the backup.|
| HAProxy             | 2.4.9     | A high-availability and load-balancing solution for Percona XtraDB Cluster. This is a default proxy.|
| ProxySQL            | 2.3.2     | A high performance, high-availability, protocol-aware proxy for MySQL.          |
| Percona Toolkit     | 3.3.1     | The set of scripts to simplify and optimize database operation.|
