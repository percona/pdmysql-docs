# Percona Distribution for MySQL 8.0.34 using Percona XtraDB Cluster (2023-11-01)

Percona Distribution for MySQL is the most stable, scalable and secure open-source MySQL distribution, with two download options: one based on Percona Server for MySQL and one based on Percona XtraDB Cluster. [Install Percona Distribution for MySQL](installing.md).

This release is focused on the Percona XtraDB Cluster-based deployment variation. It is based on [Percona XtraDB Cluster 8.0.34](https://docs.percona.com/percona-xtradb-cluster/8.0/release-notes/8.0.34-26.html)

## Release highlights

Percona XtraDB Cluster 8.0.34-26 implements telemetry that fills in the gaps in our understanding of how you use Percona XtraDB Cluster to improve our products. Participation in the anonymous program is optional. You can opt-out if you prefer not to share this information. Find more information in the [Telemetry on Percona XtraDB Cluster](https://docs.percona.com/percona-xtradb-cluster/8.0/telemetry.html) document.

Improvements and bug fixes introduced by Oracle for MySQL 8.0.34 and included in Percona XtraDB Cluster are the following:

* Adds `mysql_binlog_open()`, `mysql_binlog_fetch()`, and `mysql_binlog_close()` functions to the libmysqlclient.so shared library. These functions enable developers to access a MySQL server binary log.

* For platforms on which OpenSSL libraries are bundled, the linked OpenSSL library for MySQL Server is updated from OpenSSL 1.1.1 to OpenSSL 3.0.9.

### Deprecations and removals

* The `mysqlpump` client utility program is deprecated. The use of this program causes a warning. The `mysqlpump` client may be removed in future releases. The applications that depend on `mysqlpump` will use `mysqldump` or `MySQL Shell Utilities`.

* The `sync_relay_log_info` server system variable is deprecated. Using this variable or its equivalent startup `--sync-relay-log-info` option causes a warning. This variable may be removed in future releases. The applications that use this variable should be rewritten not to depend on it before the variable is removed.

* The `binlog_format` server system variable is deprecated and may be removed in future releases. The functionality associated with this variable, which changes the binary logging format, is also deprecated. 

    When `binlog_format` is removed, MySQL server supports only row-based binary logging. Thus, new installations should use only row-based binary logging. Migrate the existing installations that use the statement-based or mixed logging format to the row-based format.

    The system variables `log_bin_trust_function_creators` and `log_statements_unsafe_for_binlog` used in the context of statement-based logging are also deprecated and may be removed in future releases.

    Setting or selecting the values of deprecated variables causes a warning.

* The `mysql_native_password` authentication plugin is deprecated and may be removed in future releases. Using `CREATE USER`, `ALTER USER`, and `SET PASSWORD` operations, insert a deprecation warning into the server error log if an account attempts to authenticate using `mysql_native_password` as an authentication method.

* The `keyring_file` and `keyring_encrypted_file` plugins are deprecated. These keyring plugins are replaced with the `component_keyring_file` and `component_keyring_encrypted_file` components.

Find the full list of bug fixes and changes in the [MySQL 8.0.33 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/news-8-0-34.html).

## Supplied components

Review each component’s release notes for What’s new, improvements, or bug fixes. The following is a list of the components supplied with the Percona XtraDB Cluster-based variation of the Percona Distribution for MySQL:

| Component               | Version   | Description                                |
| ----------------------- | --------- | -------------------------------------------|
| Percona XtraBackup      | [8.0.34-29](https://docs.percona.com/percona-xtrabackup/8.0/release-notes/8.0/8.0.34-29.0.html)| An open-source hot backup utility for MySQL-based servers that doesn’t lock your database during the backup.|
| HAProxy                 | [2.8.1](https://git.haproxy.org/?p=haproxy-2.8.git;a=commit;h=a90123aa85c78d1aa32b3cf268672ecb49929d11) | A high-availability and load-balancing solution for Percona XtraDB Cluster. This is a default proxy.|
| ProxySQL                | [2.5.5](https://docs.percona.com/proxysql/2.5.5.html)| A high performance, high-availability, protocol-aware proxy for MySQL.          |
| Percona Toolkit         | [3.5.5](https://docs.percona.com/percona-toolkit/release_notes.html#v3-5-5-released-2023-10-03)     | The set of scripts to simplify and optimize database operation. |
| relication_manager.sh   | [1.0](./replication-manager/replication-manager-for-pxc.md)  | A tool to manage multi-source replication between multiple Percona XtraDB Cluster clusters. |