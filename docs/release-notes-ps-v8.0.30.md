# Percona Distribution for MySQL 8.0.30 using Percona Server for MySQL (2022-11-28)

| Release date    | November 28, 2022 |
| :-------------- | :--------------- |
|**Installation** | [Installing Percona Distribution for MySQL](installing.md)|


Percona Distribution for MySQL is a single solution with the best and most critical enterprise components from the MySQL open-source community, designed and tested to work together.

Percona Distribution for MySQL provides two deployment variants: one is based on *Percona Server for MySQL* and another one is based on *Percona XtraDB Cluster*.

This release is focused on the *Percona Server for MySQL*-based deployment variant. It is based on [Percona Server for MySQL 8.0.30-22](https://www.percona.com/doc/percona-server/8.0/release-notes/8.0.30-22.html).

## Release Highlights

The following features are [Generally Available (GA)](https://docs.percona.com/percona-server/8.0/glossary.md#generally-available):

* [Amazon Key Management Service](https://docs.percona.com/percona-server/8.0/security/using-amz-kms.md)

* [Key Management Interoperability Protocol](https://docs.percona.com/percona-server/8.0/security/using-kmip.md)

The following features, variables, or options are available only in [tech preview](https://docs.percona.com/percona-server/8.0/glossary.md#tech-preview):

* [SASL-based LDAP plugin](https://docs.percona.com/percona-server/8.0/security/ldap-authentication.md)

* [SASL-based LDAP variables](https://docs.percona.com/percona-server/8.0/security/ldap-system-variables.md)

* [Fallback server variables for simple LDAP and SASL-based LDAP](https://docs.percona.com/percona-server/8.0/security/ldap-system-variables.md)

* [FIDO authentication plugin](https://docs.percona.com/percona-server/8.0/security/fido-authentication-plugin.md)

* Group Replication options

Improvements and bug fixes introduced by Oracle for *MySQL* 8.0.30 and included in *Percona Server for MySQL* are the following:

* Support of Generated Invisible Primary Keys(GIPK). This feature automatically adds a primary key to InnoDB tables without a primary key. The generated key is always named `my_row_id`. The GIPK feature is not enabled by default. Enable the feature by setting `sql_generate_invisible_primary_key` to ON.

* Added two new settings to the InnoDB_doublewrite system:

  * `DETECT_ONLY`. This setting allows only metadata to be written to the doublewrite buffer. Database page content is not written to the buffer. Recovery does not use the buffer to fix incomplete page writes. Use this setting only when you need to detect incomplete page writes.

  * `DETECT_AND_RECOVER`. This setting is equivalent to the current ON setting. The doublewrite buffer is enabled. Database page content is written to the buffer and the buffer is accessed to fix incomplete page writes during recovery.

* The `-skip_host_cache` server option is deprecated and will be removed in a future release. Use `SET GLOBAL host_cache_size`= 0 or set `host_cache_size` = 0.

Find the full list of bug fixes and changes in the [MySQL 8.0.30 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/news-8-0-30.html/).

---

The following is the list of components supplied with *Percona Server for MySQL*-based deployment variant of Percona Distribution for MySQL:

| Component           | Version   | Description                                |
| ------------------- | --------- | -------------------------------------------|
| Orchestrator        | [3.2.6-6](https://github.com/percona/orchestrator/releases/tag/v3.2.6-6)     | The replication topology manager for Percona Server for MySQL|
| ProxySQL            | [2.4.4-1.2](https://docs.percona.com/proxysql/2.4.4-1.2.html)     | A high performance, high-availability, protocol-aware proxy for MySQL|
| Percona XtraBackup  | [8.0.30-23](https://docs.percona.com/percona-xtrabackup/8.0/release-notes/8.0/8.0.30-23.0.html)| An open-source hot backup utility for MySQL-based servers|
| Percona Toolkit     | [3.5.0](https://www.percona.com/doc/percona-toolkit/LATEST/release_notes.html#v3-5-0-released-2022-11-28)     | The set of scripts to simplify and optimize database operation|
| MySQL Shell         | [8.0.30](https://dev.mysql.com/doc/relnotes/mysql-shell/8.0/en/news-8-0-30.html)    | An advanced client and code editor for MySQL Server|
| MySQL Router        | [8.0.30](https://dev.mysql.com/doc/relnotes/mysql-router/en/news-8-0-30.html)    | Lightweight middleware that provides transparent routing between your application and back-end MySQL servers|


## Packaging notes

Percona Distribution for MySQL 8.0.30 using Percona Server for MySQL is available on  Ubuntu 22.04 (jammy).