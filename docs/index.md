# Percona Distribution for MySQL 8.0 Documentation

Percona Distribution for MySQL is a  single solution with the best and most critical enterprise components from the MySQL open source community, designed and tested to work together. By leveraging the distribution, you get the exact combination of software and tools required to successfully deploy, run and operate your MySQL databases to meet your application and business needs.

## Components

Percona Distribution for MySQL consists of the following **components**:


* [Percona Server for MySQL](https://www.percona.com/doc/percona-server/8.0/index.html) is a drop-in replacement for MySQL Community Edition with the enterprise-grade features embedded by Percona.


* [Percona XtraDB Cluster](https://www.percona.com/doc/percona-xtradb-cluster/8.0/index.html) is the high-available clustering solution for MySQL. It is based on [Percona Server for MySQL](https://www.percona.com/doc/percona-server/8.0/index.html) and uses [Percona XtraBackup](https://www.percona.com/doc/percona-xtrabackup/8.0/index.html) for node provisioning.


* [Percona XtraBackup](https://www.percona.com/doc/percona-xtrabackup/8.0/index.html) is an open-source hot backup utility for MySQL-based servers that doesn’t lock your database during the backup.


* [Orchestrator](https://github.com/openark/orchestrator) is the replication topology manager for *Percona Server for MySQL*.


* [HAProxy](http://www.haproxy.org/) is the default high-availability and load-balancing solution for *Percona XtraDB Cluster*.


* [ProxySQL](https://proxysql.com/) is a high performance, high-availability, protocol-aware proxy for MySQL.


* [Percona Toolkit](https://www.percona.com/doc/percona-toolkit/3.0/index.html) is the set of scripts to simplify and optimize database operation.


* [MySQL Shell](https://dev.mysql.com/doc/mysql-shell/8.0/en/) is an advanced client and code editor for MySQL Server.


* [MySQL Router](https://dev.mysql.com/doc/mysql-router/8.0/en/) is lightweight middleware that provides transparent routing between your application and back-end MySQL servers.

## Deployment variants

Percona Distribution for MySQL provides two deployment variants: one is *Percona Server for MySQL*-based and another one is *Percona XtraDB Cluster*-based. Each deployment is available via its own repository and includes the base server (*Percona Server for MySQL* or *Percona XtraDB Cluster*) and components.  The table below lists what components are available with each server:

| Components   | Percona Server for MySQL   | Percona XtraDB Cluster |
| ------------ | ---------------------------| ---------------------- |
| Orchestrator | YES                        | NO                     |
| HAProxy      | NO                         | YES                    |
| ProxySQL     | YES                        | YES                    |
| Percona XtraBackup | YES                | YES                    |
| Percona Toolkit      | YES                | YES                    |
| MySQL Shell  | YES                        | NO                     |
| MySQL Router | YES                        | NO                     |

### What deployment variant to choose?

The **Percona Server-based deployment variant** with [asynchronous replication](https://dev.mysql.com/doc/refman/8.0/en/replication.html) utilizes the primary / secondary replication model. It enables you to create geographically distributed infrastructures with the support for disaster recovery. However, this deployment variant does not guarantee data consistency on all nodes at the given moment and provides high availability  of up to 4 nines.

The **Percona Server-based deployment variant** with [Group Replication](https://dev.mysql.com/doc/refman/8.0/en/group-replication.html) enables you to create fault-tolerant systems with redundancy by replicating the system state to a set of servers. *Percona Server for MySQL*-based deployment with Group Replication  offers a high grade of high availability (4-5 nines) and almost instant fail over when associated with a proxy.

The **Percona XtraDB Cluster-based deployment variant** guarantees data consistency on all nodes and zero data loss. The Percona XtraDB Cluster-based deployment provides a high grade of high availability  (4-5 nines) and almost instant failover.

!!! admonition "See also"

    Percona Blog posts:

    * [MySQL High Availability On-Premises: A Geographically Distributed Scenario](https://www.percona.com/blog/2018/11/15/mysql-high-availability-on-premises-a-geographically-distributed-scenario/)
    * [Choosing MySQL High Availability Solutions](https://www.percona.com/blog/2016/06/07/choosing-mysql-high-availability-solutions/)

## Get started

Follow the [installation instructions](installing.md) to get started with Percona Distribution for MySQL.

Read more about solutions you can deploy with Percona Distribution for MySQL, see [solutions](solutions.md).

To learn more about what's changed in Percona Distribution for MySQL, see the [release notes](release-notes.md).