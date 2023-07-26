# Percona Distribution for MySQL 8.0.33 using Percona XtraDB Cluster (2023-08-02)

Percona Distribution for MySQL is the most stable, scalable and secure open-source MySQL distribution, with two download options: one based on Percona Server for MySQL and one based on Percona XtraDB Cluster. [Install Percona Distribution for MySQL](installing.md).

This release is focused on the Percona XtraDB Cluster-based deployment variation. It is based on [Percona XtraDB Cluster 8.0.33](https://www.percona.com/doc/percona-xtradb-cluster/8.0/release-notes/8.0.33.html)

## Release highlights

The HAProxy version is updated from 2.6.12 to 2.8.1. The changes introduced by HAProxy 2.7.0 are the following: 

- The `bind-process` directive is removed.

- The `process` argument on a bind line is removed.

HAProxy 2.8 introduces two new preprocessor functions:

- The `strstr` function returns `true` when a given string is found within another string.

- The `enabled` function returns `true` when the passed in option is enabled at runtime. You can check the following options: `POLL`, `EPOLL`, `KQUEUE`, `EVPORTS`, `SPLICE`, `GETADDRINFO`, `REUSEPORT`, `FAST-FORWARD`, and `SERVER-SSL-VERIFY-NONE`.

Find the full list of changes in the [HAProxy 2.8.1 release notes](https://git.haproxy.org/?p=haproxy-2.8.git;a=commit;h=a90123aa85c78d1aa32b3cf268672ecb49929d11), [Announcing HAProxy 2.7 blog post](https://www.haproxy.com/blog/announcing-haproxy-2-7), and in the [Announcing HAProxy 2.8 blog post](https://www.haproxy.com/blog/announcing-haproxy-2-8).

Improvements and bug fixes introduced by Oracle for MySQL 8.0.33 and included in Percona XtraDB Cluster and Percona Distribution for MySQL are the following:

* The `INSTALL COMPONENT` includes the `SET` clause. The `SET` clause sets the values of component system variables when installing one or several components. This reduces the inconvenience and limitations associated with assigning variable values in other ways.

* The mysqlbinlog `--start-position` accepts values up to `18446744073709551615`. If the `--read-from-remote-server` or `--read-from-remote-source` option is used, the maximum is `4294967295`. (Bug #77818, Bug #21498994)

* Using a generated column with `DEFAULT(col_name)` to specify the default value for a named column is not allowed and throws an error message. (Bug #34463652, Bug #34369580)

* Not all possible error states were reported during the binary log recovery process. (Bug #33658850)

* User-defined collations are deprecated. The usage of the following user-defined collations causes a warning that is written to the log:

  * When `COLLATE` is followed by the name of a user-defined collation in an SQL statement.

  * When the name of a user-defined collation is used as the value of `collation_server`, `collation_database`, or `collation_connection`.

The support for user-defined collations will be removed in a future releases of MySQL.

Find the full list of bug fixes and changes in the [MySQL 8.0.33 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/news-8-0-33.html).

## Supplied components

Review each component’s release notes for What’s new, improvements, or bug fixes. The following is a list of the components supplied with the Percona XtraDB Cluster-based variation of the Percona Distribution for MySQL:

| Component               | Version   | Description                                |
| ----------------------- | --------- | -------------------------------------------|
| Percona XtraBackup      | [8.0.33-28](https://docs.percona.com/percona-xtrabackup/8.0/release-notes/8.0/8.0.33-28.0.html)| An open-source hot backup utility for MySQL-based servers that doesn’t lock your database during the backup.|
| HAProxy                 | [2.8.1](https://git.haproxy.org/?p=haproxy-2.8.git;a=commit;h=a90123aa85c78d1aa32b3cf268672ecb49929d11) | A high-availability and load-balancing solution for Percona XtraDB Cluster. This is a default proxy.|
| ProxySQL                | [2.5.4](https://docs.percona.com/proxysql/2.5.4.html)| A high performance, high-availability, protocol-aware proxy for MySQL.          |
| Percona Toolkit         | [3.5.4](https://docs.percona.com/percona-toolkit/release_notes.html#v3-5-4-released-2023-06-30)     | The set of scripts to simplify and optimize database operation. |
| relication_manager.sh   | [1.0](./replication-manager/replication-manager-for-pxc.md)  | A tool to manage multi-source replication between multiple Percona XtraDB Cluster clusters. |