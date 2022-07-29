---
name: Release notes template PXC-based variant
about: 'Simplify the release notes creation '
title: Release notes PDPXC <version>
labels: ''
assignees: ''

---

# Percona Distribution for MySQL <version> using Percona XtraDB Cluster (<YYYY-MM-DD>)

**Installation**- [Installing Percona Distribution for MySQL](installing.md)

Percona Distribution for MySQL is a single solution with the most critical enterprise components from the MySQL open source community, designed and tested to work together.

Percona Distribution for MySQL provides two deployment variants: one is based on *Percona Server for MySQL* and another one is based on *Percona XtraDB Cluster*. 

This release of Percona Distribution for MySQL is focused on the *Percona XtraDB Cluster*-based deployment variant. It is based on [Percona XtraDB Cluster <version>](https://www.percona.com/doc/percona-xtradb-cluster/8.0/release-notes/Percona-XtraDB-Cluster-<version>.html)

## Release Highlights

The following lists a number of the bug fixes for *MySQL* 8.0.28, provided by Oracle, and included in Percona XtraDB Cluster and Percona Distribution for MySQL:



The following is the list of components supplied with the *Percona XtraDB Cluster*-based deployment variant of Percona Distribution for MySQL:

| Component           | Version   | Description                                |
| ------------------- | --------- | -------------------------------------------|
| Percona XtraBackup  | [<version>](https://docs.percona.com/percona-xtrabackup/8.0/release-notes/8.0/<version>.html)    | An open-source hot backup utility for MySQL-based servers that doesn’t lock your database during the backup.|
| HAProxy             | [<version>](http://git.haproxy.org/?p=haproxy-2.5.git;a=commit;h=ba44b431294b6ddb65d5841632789dabf253439d) | A high-availability and load-balancing solution for Percona XtraDB Cluster. This is a default proxy.|
| ProxySQL            | [<version>](https://docs.percona.com/proxysql/release-notes-<version>html)     | A high performance, high-availability, protocol-aware proxy for MySQL.          |
| Percona Toolkit     | [<version>](https://www.percona.com/doc/percona-toolkit/LATEST/release_notes.html#<version>)     | The set of scripts to simplify and optimize database operation. |
