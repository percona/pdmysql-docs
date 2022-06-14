# Percona Distribution for MySQL 8.0.27 using Percona Server for MySQL (2022-03-03)

| Release date    | March 03, 2022 |
| :-------------- | :--------------- |
|**Installation** | [Installing Percona Distribution for MySQL](installing.md)|


Percona Distribution for MySQL is a single solution with the best and most critical enterprise components from the MySQL open-source community, designed and tested to work together.

Percona Distribution for MySQL provides two deployment variants: one is based on *Percona Server for MySQL* and another one is based on *Percona XtraDB Cluster*.

This release of Percona Distribution for MySQL is focused on the *Percona Server for MySQL*-based deployment variant. It is based on [Percona Server for MySQL 8.0.27-18](https://www.percona.com/doc/percona-server/8.0/release-notes/Percona-Server-8.0.27-18.html).

## Release Highlights

The following list are some of the bug fixes for *MySQL* 8.0.27, provided by Oracle, and included in Percona Server for MySQL and Percona Distribution for MySQL:


* The `default_authentication_plugin` is deprecated. Support for this plugin may be removed in future versions. Use the `authentication_policy` variable.


* The `binary` operator is deprecated. Support for this operator may be removed in future versions. Use `CAST(... AS BINARY)`.


* Fix for when a parent table initiates a cascading `SET NULL` operation on the child table, the virtual column can be set to NULL instead of the value derived from the parent table.

## Packaging Notes


* Red Hat Enterprise Linux 6 (and derivative Linux distributions) are no longer supported.

## Known issues

The RPM packages for Red Hat Enterprise Linux 7 (and compatible derivatives) do not support TLSv1.3, as it requires OpenSSL 1.1.1, which is currently not available on this platform.


---

The following is the list of components supplied with *Percona Server for MySQL*-based deployment variant of Percona Distribution for MySQL:

| Component           | Version   | Description                                |
| ------------------- | --------- | -------------------------------------------|
| Orchestrator        | 3.2.6     | The replication topology manager for Percona Server for MySQL|
| ProxySQL            | 2.3.2     | A high performance, high-availability, protocol-aware proxy for MySQL|
| Percona XtraBackup  | 8.0.27-17.0| An open-source hot backup utility for MySQL-based servers|
| Percona Toolkit     | 3.3.1     | The set of scripts to simplify and optimize database operation|
| MySQL Shell         | 8.0.27    | An advanced client and code editor for MySQL Server |
| MySQL Router        | 8.0.27    | Lightweight middleware that provides transparent routing between your application and back-end MySQL servers |
