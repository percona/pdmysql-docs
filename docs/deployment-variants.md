# Deployment variants

Percona Distribution for MySQL provides two deployment variants: one is *Percona Server for MySQL*-based with asynchronous replication and another one is *Percona Server for MySQL*-based with group replication. The table below lists what components are available with Percona Server for MySQL:

| Components   | Percona Server for MySQL   |
| ------------ | ---------------------------|
| Orchestrator | YES                        |
| HAProxy      | NO                         |
| ProxySQL     | YES                        |
| Percona XtraBackup | YES                  |
| Percona Toolkit      | YES                |
| MySQL Shell  | YES                        |
| MySQL Router | YES                        |

## What deployment variant to choose?

The **Percona Server-based deployment variant** with [asynchronous replication](https://dev.mysql.com/doc/refman/8.1/en/replication.html) utilizes the primary / secondary replication model. It enables you to create geographically distributed infrastructures with the support for disaster recovery. However, this deployment variant does not guarantee data consistency on all nodes at the given moment and provides high availability  of up to 4 nines.

The **Percona Server-based deployment variant** with [Group Replication](https://dev.mysql.com/doc/refman/8.1/en/group-replication.html) enables you to create fault-tolerant systems with redundancy by replicating the system state to a set of servers. *Percona Server for MySQL*-based deployment with Group Replication  offers a high grade of high availability (4-5 nines) and almost instant fail over when associated with a proxy.

