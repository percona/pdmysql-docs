# Percona Distribution for MySQL 8.0.36 using Percona Server for MySQL (2024-03-04)

Percona Distribution for MySQL is the most stable, scalable, and secure open source MySQL distribution, with two download options: one based on Percona Server for MySQL and one based on Percona XtraDB Cluster. [Install Percona Distribution for MySQL](installing.md).

This release is focused on the Percona Server for MySQL-based deployment variation. It is based on [Percona Server for MySQL 8.0.36-28](https://www.percona.com/doc/percona-server/8.0/release-notes/8.0.36-28.html).

## Release highlights 

This release fixes the Orchestrator issues. Find the full list of bug fixes and changes in the [MySQL 8.0.36 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/news-8-0-36.html).

## Bug fixes

The Orchestrator version is updated from 3.2.6-11 to 3.2.6-12. The issues fixed in Orchestrator 3.2.6-12 are the following:
	
* [DISTMYSQL-396](https://perconadev.atlassian.net/browse/DISTMYSQL-396): The Orchestrator failed to handle duplicate values for alias.
	
* [DISTMYSQL-364](https://perconadev.atlassian.net/browse/DISTMYSQL-364): The Orchestrator didn't support group replication with Percona Server for MySQL.
	
* [DISTMYSQL-185](https://perconadev.atlassian.net/browse/DISTMYSQL-185): A user was receiving false errors when relocating the replicas.
	
* [DISTMYSQL-226](https://perconadev.atlassian.net/browse/DISTMYSQL-226): The Orchestrator incorrectly handled the `max_allowed_packet` setting.
	

## Supplied components

Review each component’s release notes for What’s new, improvements, or bug fixes. The following is a list of the components supplied with the Percona Server for MySQL-based variation of the Percona Distribution for MySQL:

| Component           | Version   | Description                                |
| ------------------- | --------- | -------------------------------------------|
| Orchestrator        | [3.2.6-12](https://github.com/percona/orchestrator/releases/tag/v3.2.6-12)     | The replication topology manager for Percona Server for MySQL|
| ProxySQL            | [2.5.5-1.2](https://docs.percona.com/proxysql/2.5.5-1.2.html)     | A high performance, high-availability, protocol-aware proxy for MySQL|
| Percona XtraBackup  | [8.0.35-30](https://docs.percona.com/percona-xtrabackup/8.0/release-notes/8.0/8.0.35-30.0.html)| An open-source hot backup utility for MySQL-based servers|
| Percona Toolkit     | [3.5.7](https://docs.percona.com/percona-toolkit/release_notes.html#v3-5-7-released-2023-12-22)     | The set of scripts to simplify and optimize database operation|
| MySQL Shell         | [8.0.36](https://dev.mysql.com/doc/relnotes/mysql-shell/8.0/en/news-8-0-35.html)    | An advanced client and code editor for MySQL Server|
| MySQL Router        | [8.0.36](https://dev.mysql.com/doc/relnotes/mysql-router/en/news-8-0-35.html)    | Lightweight middleware that provides transparent routing between your application and back-end MySQL servers|


