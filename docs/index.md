# Percona Distribution for MySQL {{vers}} Documentation

Percona Distribution for MySQL is a single solution with the best and most critical enterprise components from the MySQL open source community, designed and tested to work together. With [Percona Server for MySQL :octicons-link-external-16:](https://www.percona.com/mysql/software/percona-server) or [Percona XtraDB Cluster :octicons-link-external-16:](https://www.percona.com/mysql/software/percona-xtradb-cluster) as the base server, the distribution brings you the enterprise-grade [features](#features) for free. The set of carefully selected [components](components.md) helps you operate your MySQL database to meet your application and business needs.

## Features

- **Increased stability and availability** - a set of high-availability and backup options help you ensure your data is saved and available for your business applications. 

- **Improved performance and efficiency** - integrated tools help DBAs maintain, manage and monitor the database performance and timely respond to changing demands. 

- **Reduced costs** - save on purchasing software licensing by using the distribution - the open-source enterprise-grade solution.

- **Easy-to-integrate with PMM** - benefit from all the features of [PMM :octicons-link-external-16:](https://docs.percona.com/percona-monitoring-and-management/3/) for monitoring and managing the health of your database.

Percona Distribution for MySQL comes in two [deployment variants](deployment-variants.md): one is based on Percona Server for MySQL and another one - on Percona XtraDB Cluster. They differ in the set of components and how you can use them. 

<!-- Clarify whether the following note is valid for 9.7-->

!!! important

    This release does not include the Percona Toolkit component. We will add it once a Percona Toolkit version compatible with MySQL {{vers}} becomes available.
    
    In {{vers}}.x environments, the ProxySQL binlog reader can fail to initialize because it uses legacy commands, such as SHOW MASTER STATUS. Some internal counters also use outdated terminology. To address most terminology issues, enable the [terminology_use_previous](https://dev.mysql.com/doc/refman/{{vers}}/en/replication-options-replica.html#sysvar_terminology_use_previous) system variable on the database server. This workaround addresses only terminology compatibility and may not fix all failures.

<div data-grid markdown><div data-banner markdown>

### :material-progress-download: Installation guides { .title }

Find the best installation solution with our step-by-step installation instructions.

[Installation instructions](installing.md){ .md-button }

</div><div data-banner markdown>

## :material-progress-download: Solutions { .title }

Learn about solutions you can deploy with Percona Distribution for MySQL.

[Solutions](pdps-group-replication.md){ .md-button }

</div><div data-banner markdown>

### :material-backup-restore: Deployment variants { .title }

Learn about the deployment variants.

[Deployment variants](deployment-variants.md){ .md-button }

</div><div data-banner markdown>

## :fontawesome-solid-gears: Percona Distribution for MySQL components { .title }

Learn about the Percona Distribution for MySQL components.

[Components](components.md){ .md-button}

</div>
</div>
