# Percona Distribution for MySQL 8.0.19 (2020-06-22)


| Release date    |   June 22, 2020 |
| :-------------- | :--------------- |
|**Installation** | [Installing Percona Distribution for MySQL](installing.md)|

    
Percona Distribution for MySQL is a  single solution with the best and most critical enterprise components from the MySQL open source community, designed and tested to work together. By leveraging the distribution, you get the exact combination of software and tools required to successfully deploy, run and operate your MySQL databases to meet your application and business needs.

Percona Distribution for MySQL consists of the following components:


* [Percona Server for MySQL](https://www.percona.com/doc/percona-server/8.0/index.html) is a drop-in replacement for MySQL Community Edition with the enterprise-grade features embedded by Percona.


* [Percona XtraDB Cluster](https://www.percona.com/doc/percona-xtradb-cluster/8.0/index.html) is the high-available clustering solution for MySQL. It is based on *Percona Server for MySQL* and uses *Percona XtraBackup* for node provisioning.


* [Percona XtraBackup](https://www.percona.com/doc/percona-xtrabackup/8.0/index.html) is an open-source hot backup utility for MySQL-based servers that doesn’t lock your database during the backup.


* [Orchestrator](https://github.com/openark/orchestrator) is the replication topology manager for *Percona Server for MySQL*.


* [HAProxy](http://www.haproxy.org/) is the default high-availability and load-balancing solution for *Percona XtraDB Cluster*.


* [ProxySQL](https://proxysql.com/) is a high performance, high-availability, protocol-aware proxy for MySQL.


* [Percona Toolkit](https://www.percona.com/doc/percona-toolkit/3.0/index.html) is the set of scripts to simplify and optimize database operation.


* [MySQL Shell](https://dev.mysql.com/doc/mysql-shell/8.0/en/) is an advanced client and code editor for MySQL Server.


* [MySQL Router](https://dev.mysql.com/doc/mysql-router/8.0/en/) is lightweight middleware that provides transparent routing between your application and back-end MySQL Servers.

Percona Distribution for MySQL provides two deployment variants: one is *Percona Server for MySQL*-based and another one is *Percona XtraDB Cluster*-based. This enables you to build MySQL ecosystem that meets your specific needs. Each variant is available via its own repository and includes the base server (*Percona Server for MySQL* or *Percona XtraDB Cluster*) and compatible components.

This release of Percona Distribution for MySQL is based on *Percona Server for MySQL* 8.0.19 and *Percona XtraDB Cluster* 8.0.19.
