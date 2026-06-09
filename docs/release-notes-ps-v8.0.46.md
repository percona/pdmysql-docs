# Percona Distribution for MySQL 8.0.46 using Percona Server for MySQL (2026-06-10)

Percona Distribution for MySQL is the most stable, scalable, and secure open source MySQL distribution, with two download options: one based on Percona Server for MySQL and one based on Percona XtraDB Cluster. [Install Percona Distribution for MySQL](installing.md).

This release is based on [Percona Server for MySQL 8.0.46-37](https://docs.percona.com/percona-server/8.0/release-notes/8.0.46-37.html) that includes all the features and bug fixes available in the [MySQL 8.0.46 Community Edition](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/news-8-0-46.html) and enterprise-grade features developed by Percona.

!!! note "Final 8.0 series release"

    MySQL 8.0 has officially reached End of Life (EOL). Percona Distribution for MySQL 8.0.46 and Percona Server for MySQL 8.0.46-37 are the final standard releases in the 8.0 series.

    Future support depends on your product:

    **Percona Distribution for MySQL 8.0**: Fully retired. No further releases, bug fixes, security updates, or post-EOL support will be provided.

    **Percona Server for MySQL 8.0**: Standard public support has ended, but extended lifecycle options are available:
      * **Paid subscribers**: Access to critical updates and precompiled binaries through a private repository.
      * **Community users**: Access to source code only, published quarterly with a delay.

    **Recommendation:** Upgrade to MySQL 8.4 to ensure continued standard support and platform stability.

## Release highlights

### MySQL 8.0.46

Improvements and bug fixes provided by Oracle for MySQL 8.0.46 and included in Percona Server for MySQL are the following:

* Building full-text search indexes on very large InnoDB tables now uses noticeably less memory, lowering the risk of out-of-memory conditions during index creation. (Bug #39040226)

* When an undo tablespace was truncated, the purge thread previously left the `undo_{space_number}_trunc.log` marker file behind on disk; this cleanup step now runs reliably as part of the truncate operation. (Bug #38871808)

* Running `CREATE INDEX` with a high `--innodb_parallel_read_threads` value could, under some workloads, consume all available disk space on the data volume. The parallel index build path has been adjusted to keep its on-disk footprint bounded. (Bug #38370155)

Find the complete list of bug fixes and changes in the [MySQL 8.0.46 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/news-8-0-46.html).

## Supplied components

Review each component’s release notes for What’s new, improvements, or bug fixes. The following is a list of the components supplied with the Percona Server for MySQL-based variation of the Percona Distribution for MySQL:

| Component           | Version   | Description                                |
| ------------------- | --------- | -------------------------------------------|
| Orchestrator        | [3.2.6-22](https://github.com/percona/orchestrator/releases/tag/v3.2.6-22)     | The replication topology manager for Percona Server for MySQL|
| ProxySQL            | [2.7.3](https://docs.percona.com/proxysql/2.7.3.html)     | A high performance, high-availability, protocol-aware proxy for MySQL|
| Percona XtraBackup  | [8.0.35-36](https://docs.percona.com/percona-xtrabackup/8.0/release-notes/8.0/8.0.35-36.0.html)| An open-source hot backup utility for MySQL-based servers|
| Percona Toolkit     | [3.7.1-3](https://docs.percona.com/percona-toolkit/release_notes.html#v3-7-1-3-released-2026-04-17)     | The set of scripts to simplify and optimize database operation|
| MySQL Shell         | [8.0.46](https://dev.mysql.com/doc/relnotes/mysql-shell/8.0/en/news-8-0-46.html)    | An advanced client and code editor for MySQL Server|
| MySQL Router        | [8.0.46](https://dev.mysql.com/doc/relnotes/mysql-router/8.0/en/news-8-0-46.html)    | Lightweight middleware that provides transparent routing between your application and back-end MySQL servers|
