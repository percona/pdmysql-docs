# Percona Distribution for MySQL 8.4.0-1 using Percona Server for MySQL (2024-10-25)

Percona Distribution for MySQL is the most stable, scalable, and secure open source MySQL distribution, with two download options: one based on Percona Server for MySQL and one based on Percona XtraDB Cluster. [Install Percona Distribution for MySQL](installing.md).

This release is based on [Percona Server for MySQL 8.4.0-1](https://www.percona.com/doc/percona-server/8.4/release-notes/8.4.0-1.html).


## Release highlights

In MySQL 8.0, the release model changed to include new features in patch releases, allowing MySQL to introduce new features more frequently. However, this approach was complex for projects and applications needing only critical patches with minimal changes.

MySQL then moved to a versioning model with two options: Innovation releases and Long-Term Support (LTS) releases. Both types are production-ready.

Innovation releases offer access to the latest features, making them ideal for dynamic environments with strong automated testing and continuous integration.

Changes were made to each Innovation release that are now included in the 8.4 (LTS) release. You should review the Innovation release notes for details.

* [Percona Server for MySQL 8.1.0-1 (2023-11-27)](https://docs.percona.com/percona-server/innovation-release/release-notes/8.1.0-1.html)

* [Percona Server for MySQL 8.2.0-1 (2024-02-05)](https://docs.percona.com/percona-server/innovation-release/release-notes/8.2.0-1.html)

* [Percona Server for MySQL 8.3.0-1 (2024-04-16)](https://docs.percona.com/percona-server/innovation-release/release-notes/8.3.0-1.html)

LTS releases are more suitable for stable, established environments where minimal changes are needed. These releases include only essential fixes, reducing the risk of changes in the database software’s behavior.

This 8.4.0-1 release is the first 8.4 LTS series.

Improvements and bug fixes introduced by Oracle for MySQL 8.4 and included in Percona Server for MySQL are the following:

* The MySQL native password has been deprecated and is no longer loaded by default. However, it can be loaded if needed.

* The clone plugin allows cloning between different point releases within the same series. You only must match the major and minor version numbers for cloning.

* GTIDs (Global Transaction Identifiers) can now handle groups of transactions, which helps speed up processing.

* `mysqldump` can now create output for older versions of MySQL.

* Automatic updates for histograms. When enabled, the histogram updates automatically whenever `ANALYZE TABLE` is run on the table. InnoDB's automatic recalculation of persistent statistics also updates the histogram when automatic updates are enabled.

* Adds a new privilege called FLUSH_PRIVILEGES. This privilege explicitly allows the use of FLUSH PRIVILEGES statements. Unlike the RELOAD privilege, FLUSH_PRIVILEGES only applies to FLUSH PRIVILEGES statements.

* The terms "MASTER" and "SLAVE" in replication commands are being replaced with "SOURCE" and "REPLICA". This change is part of an ongoing effort to use more inclusive language.

* Removed the the `mysqlpump` utility.

* Removed the `mysql_upgrade` utility.

* The default values for specific InnoDB server system variables have changed. See [What is new in MySQL 8.4 since 8.0](https://dev.mysql.com/doc/refman/8.4/en/mysql-nutshell.html) for details.

## Deprecation

* [PS-8963](https://perconadev.atlassian.net/browse/PS-8963): The `SEQUENCE_TABLE()` function is deprecated and may be removed in a future release. We recommend that you use `PERCONA_SEQUENCE_TABLE()` instead. To maintain compatibility with existing third-party software, `SEQUENCE_TABLE` is no longer a reserved term and can be used as a regular identifier. Find more information in [PERCONA_SEQUENCE_TABLE(n) function](https://docs.percona.com/percona-server/8.4/percona-sequence-table.html).

## Packaging notes

Percona Server for MySQL 8.4.0-1 is compatible with Ubuntu 24.04.

## Supplied components

Review each component’s release notes for What’s new, improvements, or bug fixes. The following is a list of the components supplied with the Percona Server for MySQL-based variation of the Percona Distribution for MySQL.

!!! important

    This release does not include the Percona Toolkit component. We will add it once a Percona Toolkit version compatible with MySQL 8.4 becomes available.

| Component           | Version   | Description                                |
| ------------------- | --------- | -------------------------------------------|
| Orchestrator        | [3.2.6-14](https://github.com/percona/orchestrator/releases/tag/v3.2.6-14)     | The replication topology manager for Percona Server for MySQL|
| ProxySQL            | [2.6.5](https://docs.percona.com/proxysql/2.6.5.html)     | A high performance, high-availability, protocol-aware proxy for MySQL|
| Percona XtraBackup  | [8.4.0-1](https://docs.percona.com/percona-xtrabackup/8.4/release-notes/8.4.0-1.html)| An open-source hot backup utility for MySQL-based servers|
| MySQL Shell         | [8.4.0](https://dev.mysql.com/doc/relnotes/mysql-shell/8.4/en/news-8-4-0.html)    | An advanced client and code editor for MySQL Server|
| MySQL Router        | [8.4.0](https://dev.mysql.com/doc/relnotes/mysql-router/8.4/en/news-8-4-0.html)    | Lightweight middleware that provides transparent routing between your application and back-end MySQL servers|
