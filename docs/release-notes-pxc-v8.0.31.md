# Percona Distribution for MySQL 8.0.31 using Percona XtraDB Cluster (2023-03-15)

| Release date            | March 15, 2023 |
| :---------------------- | :--------------- |
| Install instructions    | [Installing Percona Distribution for MySQL](installing.md)|

Percona Distribution for MySQL is the most stable, scalable and secure open-source MySQL distribution, with two download options: one based on Percona Server for MySQL and one based on Percona XtraDB Cluster.

This release is focused on the Percona XtraDB Cluster-based deployment variation. It is based on [Percona XtraDB Cluster 8.0.31-23](https://www.percona.com/doc/percona-xtradb-cluster/8.0/release-notes/8.0.31-23.html)

## Release highlights

This release adds the [GCache encryption and Write-Set cache encryption](https://docs.percona.com/percona-xtradb-cluster/8.0/management/gcache-write-set-cache-encryption.html) feature in [tech preview](./glossary.md#tech-preview).

Improvements and bug fixes introduced by Oracle for MySQL 8.0.31 and included in Percona XtraDB Cluster and Percona Distribution for MySQL are the following:

* MySQL adds support for the SQL standard [`INTERSECT`](https://dev.mysql.com/doc/refman/8.0/en/intersect.html) and [`EXCEPT`](https://dev.mysql.com/doc/refman/8.0/en/except.html) table operators.

* InnoDB supports parallel index builds. This improves index build performance. The sorted index entries are loaded into a B-tree in a multithread. In previous releases, this action was performed by a single thread.

* The Performance and sys schemas show metrics for the global and session memory limits introduced in MySQL 8.0.28.

    The following columns have been added to the Performance Schema tables:

    | Performance Schema tables                                                            | Columns                                                   |
    | ------------------------------------------------------------------------------------ | --------------------------------------------------------- |
    | SETUP_INSTRUMENTS                                                                    | FLAGS                                                     |
    | THREADS                                                                              | CONTROLLED_MEMORY, MAX_CONTROLLED_MEMORY, TOTAL_MEMORY, MAX_TOTAL_MEMORY |
    | EVENTS_STATEMENTS_CURRENT, EVENTS_STATEMENTS_HISTORY, EVENTS_STATEMENTS_HISTORY_LONG | MAX_CONTROLLED_MEMORY, MAX_TOTAL_MEMORY                   |
    | Statement Summary Tables                                                             | MAX_CONTROLLED_MEMORY, MAX_TOTAL_MEMORY                   |
    | Performance Schema Connection Tables                                                 | MAX_SESSION_CONTROLLED_MEMORY, MAX_SESSION_TOTAL_MEMORY   |
    | PREPARED_STATEMENTS_INSTANCES                                                        | MAX_CONTROLLED_MEMORY, MAX_TOTAL_MEMORY                   |

    The following columns have been added to the sys schema `STATEMENT_ANALYSIS` and `X$STATEMENT_ANALYSIS` views:

    * MAX_CONTROLLED_MEMORY

    * MAX_TOTAL_MEMORY

    The `controlled_by_default` flag has been added to the `PROPERTIES` column of the `SETUP_INSTRUMENTS` table.

    Now, you can add and remove non-global memory instruments to the set of controlled-memory instruments. To do this, set the value of the `FLAGS` column of `SETUP_INSTRUMENTS`.

    ```sql
    SQL> UPDATE PERFORMANCE_SCHEMA.SETUP_INTRUMENTS SET FLAGS="controlled" 
    WHERE NAME='memory/sql/NET::buff';
    ```

* The `audit_log_flush` variable has been deprecated and will be removed in future releases.

Find the full list of bug fixes and changes in the [MySQL 8.0.31 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/news-8-0-31.html).

## Supplied components

Review each component’s release notes for What’s new, improvements, or bug fixes. The following is a list of the components supplied with the Percona Server for MySQL-based variation of the Percona Distribution for MySQL:

| Component               | Version   | Description                                |
| ----------------------- | --------- | -------------------------------------------|
| Percona XtraBackup      | [8.0.31-24](https://docs.percona.com/percona-xtrabackup/8.0/release-notes/8.0/8.0.31-24.0.html)| An open-source hot backup utility for MySQL-based servers that doesn’t lock your database during the backup.|
| HAProxy                 | [2.5.12](https://git.haproxy.org/?p=haproxy-2.5.git;a=commit;h=7367a7ceb9494a4c463120bb065d619c8663b00a) | A high-availability and load-balancing solution for Percona XtraDB Cluster. This is a default proxy.|
| ProxySQL                | [2.4.8](https://docs.percona.com/proxysql/2.4.8.html)| A high performance, high-availability, protocol-aware proxy for MySQL.          |
| Percona Toolkit         | [3.5.1](https://www.percona.com/doc/percona-toolkit/LATEST/release_notes.html#v3-5-1-released-2022-11-28)     | The set of scripts to simplify and optimize database operation. |
| relication_manager.sh   | [1.0](./replication-manager/replication-manager-for-pxc.md)  | A tool to manage multi-source replication between multiple Percona XtraDB Cluster clusters. |
