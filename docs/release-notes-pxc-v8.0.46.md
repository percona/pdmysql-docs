# Percona Distribution for MySQL 8.0.46 using Percona XtraDB Cluster (2026-07-23)

Percona Distribution for MySQL is more than just a version of MySQL; it is a comprehensive solution that combines Percona Server for MySQL with additional tools to create a cohesive environment. This distribution is reliable, scalable, and secure, ensuring that all components have been tested to work seamlessly together. You can choose from two download options: one that uses Percona Server for MySQL and another that utilizes Percona XtraDB Cluster. Refer to [Install Percona Distribution for MySQL](installing.md).

This release is focused on the Percona XtraDB Cluster-based deployment variation. It is based on [Percona XtraDB Cluster 8.0.46-38](https://docs.percona.com/percona-xtradb-cluster/8.0/release-notes/8.0.46-38.html).

!!! note "Final 8.0 series release"

    MySQL 8.0 has officially reached End of Life (EOL). Percona Distribution for MySQL 8.0.46 and Percona XtraDB Cluster 8.0.46-38 are the final standard releases in the 8.0 series.

    Future support depends on your product:

    **Percona Distribution for MySQL 8.0**: Fully retired. No further releases, bug fixes, security updates, or post-EOL support will be provided.

    **Percona XtraDB Cluster 8.0**: Standard public support has ended, but extended lifecycle options are available:
      * **Paid subscribers**: Access to critical updates and precompiled binaries through a private repository.
      * **Community users**: Access to source code only, published quarterly with a delay.

    **Recommendation:** Upgrade to MySQL 8.4 to ensure continued standard support and platform stability.

## Release highlights

Improvements and bug fixes provided by Oracle for MySQL 8.0.46 and included in Percona Server for MySQL are documented in the [MySQL 8.0.46 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/news-8-0-46.html).

### Security updates

This release addresses the following security vulnerabilities:

* [CVE-2026-48165](https://www.cve.org/CVERecord?id=CVE-2026-48165): A vulnerability in the handling of the `wsrep_sst_donor` and `wsrep_sst_receive_address` system variables allowed a high-privileged user to execute arbitrary shell commands with the privileges of the `mariadbd` process during State Snapshot Transfer (SST) due to improper input sanitization (CVSS 3.1 Base Score 7.2). :contentReference[oaicite:0]{index=0}. (This fix was backported from MariaDB. Thanks to the MariaDB project for identifying and fixing this issue.)

* [CVE-2026-49261](https://www.cve.org/CVERecord?id=CVE-2026-49261): A vulnerability in MariaDB Server with `wsrep_notify_cmd` enabled allowed a remote attacker to execute arbitrary shell commands by embedding commands in the name of a joiner node due to improper input sanitization (CVSS 3.1 Base Score 10.0). :contentReference[oaicite:0]{index=0}. (This fix was backported from MariaDB. Thanks to the MariaDB project for identifying and fixing this issue.)

## Packaging and builds

Percona XtraDB Cluster 8.0.46-38 adds support for Ubuntu 26.04.

## Supplied components

Review each component’s release notes for What’s new, improvements, or bug fixes. The following is a list of the components supplied with the Percona XtraDB Cluster-based variation of the Percona Distribution for MySQL:

| Component               | Version   | Description                                |
| ----------------------- | --------- | -------------------------------------------|
| Percona XtraBackup      | [8.0.35-36](https://docs.percona.com/percona-xtrabackup/8.0/release-notes/8.0/8.0.35-36.0.html)| An open-source hot backup utility for MySQL-based servers that doesn’t lock your database during the backup.|
| HAProxy                 | [2.8.26](https://git.haproxy.org/?p=haproxy-2.8.git;a=commit;h=682859627b241be60d2c26e0671c702a2681bcd2) | A high-availability and load-balancing solution for Percona XtraDB Cluster. This is a default proxy.|
| ProxySQL                | [2.7.3](https://docs.percona.com/proxysql/2.7.3.html)| A high performance, high-availability, protocol-aware proxy for MySQL.          |
| Percona Toolkit         | [3.7.1](https://docs.percona.com/percona-toolkit/release_notes.html#v3-7-1-4-released-2026-07-02)     | The set of scripts to simplify and optimize database operation. |
| relication_manager.sh   | [1.0](https://docs.percona.com/percona-distribution-for-mysql/8.0/replication-manager/replication-manager-for-pxc.html)  | A tool to manage multi-source replication between multiple Percona XtraDB Cluster clusters. |
