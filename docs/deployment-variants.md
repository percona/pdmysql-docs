# Deployment variants

Percona Distribution for MySQL provides two deployment variants: one is Percona Server for MySQL-based and another one is Percona XtraDB Cluster-based. Each deployment is available via its own repository and includes the base server (Percona Server for MySQL or Percona XtraDB Cluster) and [components](components.md). The table below lists what components are available with each server:

| Components   | Percona Server for MySQL   |
| ------------ | ---------------------------|
| Orchestrator | YES                        |
| HAProxy      | NO                         |
| ProxySQL     | YES                        |
| Percona XtraBackup | YES                  |
| Percona Toolkit      | YES                |
| MySQL Shell  | YES                        |
| MySQL Router | YES                        |

!!! important

    This release does not include the Percona Toolkit component. We will add it once a Percona Toolkit version compatible with MySQL 8.4 becomes available.
    
    ProxySQL contains counters that have not been updated to use the new terminology. Unexpected results may occur. In an 8.4.x environment, the binlog reader errors out during initialization due to the use of old terminology, such as the SHOW MASTER STATUS command.

## What deployment variant to choose?

The **Percona Server-based deployment variant** with [asynchronous replication](https://dev.mysql.com/doc/refman/{{vers}}/en/replication.html) utilizes the primary / secondary replication model. It enables you to create geographically distributed infrastructures with the support for disaster recovery. However, this deployment variant does not guarantee data consistency on all nodes at the given moment and provides high availability  of up to 4 nines.

The **Percona Server-based deployment variant** with [Group Replication](https://dev.mysql.com/doc/refman/{{vers}}/en/group-replication.html) enables you to create fault-tolerant systems with redundancy by replicating the system state to a set of servers. *Percona Server for MySQL*-based deployment with Group Replication  offers a high grade of high availability (4-5 nines) and almost instant fail over when associated with a proxy.

The **Percona XtraDB Cluster-based deployment variant** guarantees data consistency on all nodes and zero data loss. The Percona XtraDB Cluster-based deployment provides a high grade of high availability (4-5 nines) and almost instant failover.


