# Percona Distribution for MySQL 8.0.34 using Percona Server for MySQL (2023-09-26)

Percona Distribution for MySQL is the most stable, scalable, and secure open source MySQL distribution, with two download options: one based on Percona Server for MySQL and one based on Percona XtraDB Cluster. [Install Percona Distribution for MySQL](installing.md).

This release is focused on the Percona Server for MySQL-based deployment variation. It is based on [Percona Server for MySQL 8.0.34-26](https://www.percona.com/doc/percona-server/8.0/release-notes/8.0.34-26.html).

## Release highlights

* Percona Server for MySQL 8.0.34-26 implements the [Audit Log Filter plugin](https://docs.percona.com/percona-server/8.0/audit-log-filter-overview.html). The plugin provides a set of features that you can use to monitor user activity on the selected server:

    * Filter audit events based on user/connection, accessed database/table name, query content, etc. Filtering rules are in JSON format.
    * Dynamically enable/disable the auditing. A server restart is not required to add or adjust existing filtering rules.
    * Use filtering rules to remove sensitive data from SQL statements written to log files.
    * Use filtering rules to block events matching specific criteria (for example, database/table name, user name).
    * Configure filtering rules to write to audit log extra information provided via Query Attributes with each query.
    * Encrypt the audit log files using AES-256 encryption. The plugin keeps a set of encryption passwords used to encrypt existing log files. External applications may use these passwords to access encrypted logs.
    * Compress audit log files to reduce the storage space used by log files.
    * Configure an automatic rotation and removal of log files. You can remove outdated log files based either on storage space used by log files or the age of log files.

* Percona Server for MySQL 8.0.34-26 implements the [data masking component](https://docs.percona.com/percona-server/8.0/install-data-masking-component.html), an improved and enchanced version of [data masking plugin](../install-data-masking-plugin.md](https://docs.percona.com/percona-server/8.0/install-data-masking-plugin.html). The data masking component adds the following features:

    * Support for multibyte character sets for random generation/masking functions
    * New masking functions for IBAN, UUID, Canada SIN, and UK NIN
    * New random generation functions for BAN, UUID, Canada SIN, and UK NIN
    * The ability to store substitution dictionaries in the database
    * The dynamic privilege `MASKING_DICTIONARIES_ADMIN` that is required for dictionary manipulation operations
    * The automated loadable-function registration/unregistration during component installation/uninstallation

This merge fixes the following issue:

* [PS-8770](https://jira.percona.com/browse/PS-8770): The `INSTANT DDL` caused Percona Server 8.0.32 exit after upgrading from 5.7.41.

Improvements and bug fixes introduced by Oracle for MySQL 8.0.34 and included in Percona Server for MySQL are the following:

* MySQL 8.0.33 added support for the `audit_log plugin` to choose which database to use to store JSON filter tables. Now, you can specify an alternative to the default system database, mysql, when running the plugin installation script. For example:

```{.bash data-prompt="mysql>"}
$> mysql -u root -D database_name -p < audit_log_filter_linux_install.sql
```

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

*  The legacy filtering mode is deprecated. New deprecation warnings are emitted for legacy audit log filtering system variables. The deprecated variables are either read-only or dynamic.

    The `audit_log_policy` read-only variable writes a warning message to the MySQL server error log during server startup when its value is set to any value except `ALL` (default value).

    The `audit_log_include_accounts`, `audit_log_exclude_accounts`, `audit_log_statement_policy`, and `audit_log_connection_policy` are dynamic variables. Dynamic variables print a warning message based on usage:

      * Passing in a `non-NULL` value to `audit_log_include_accounts` or `audit_log_exclude_accounts` during MySQL server startup writes a warning message to the server error log.

      * Passing in a `non-default` value to `audit_log_statement_policy` or `audit_log_connection_policy` during MySQL server startup now writes a warning message to the server error log. `ALL` is the default value for both variables.

      * Changing an existing value using `SET` syntax during a MySQL client session writes a warning message to the client log.

      * Persisting a variable using `SET PERSIST` syntax during a MySQL client session writes a warning message to the client log.

* The `keyring_file` and `keyring_encrypted_file` plugins are deprecated. These keyring plugins are replaced with the `component_keyring_file` and `component_keyring_encrypted_file` components.

Find the full list of bug fixes and changes in the [MySQL 8.0.34 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/news-8-0-34.html).

## Supplied components

Review each component’s release notes for What’s new, improvements, or bug fixes. The following is a list of the components supplied with the Percona Server for MySQL-based variation of the Percona Distribution for MySQL:

| Component           | Version   | Description                                |
| ------------------- | --------- | -------------------------------------------|
| Orchestrator        | [3.2.6-10](https://github.com/percona/orchestrator/releases/tag/v3.2.6-10)     | The replication topology manager for Percona Server for MySQL|
| ProxySQL            | [2.5.5](https://docs.percona.com/proxysql/2.5.5.html)     | A high performance, high-availability, protocol-aware proxy for MySQL|
| Percona XtraBackup  | [8.0.34-29](https://docs.percona.com/percona-xtrabackup/8.0/release-notes/8.0/8.0.34-29.0.html)| An open-source hot backup utility for MySQL-based servers|
| Percona Toolkit     | [3.5.4](https://docs.percona.com/percona-toolkit/release_notes.html#v3-5-4-released-2023-06-30)     | The set of scripts to simplify and optimize database operation|
| MySQL Shell         | [8.0.34](https://dev.mysql.com/doc/relnotes/mysql-shell/8.0/en/news-8-0-34.html)    | An advanced client and code editor for MySQL Server|
| MySQL Router        | [8.0.34](https://dev.mysql.com/doc/relnotes/mysql-router/en/news-8-0-34.html)    | Lightweight middleware that provides transparent routing between your application and back-end MySQL servers|
