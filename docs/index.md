# Percona Distribution for MySQL {{vers}} Documentation

Percona Distribution for MySQL is a single solution with the best and most critical enterprise components from the MySQL open source community, designed and tested to work together. With [Percona Server for MySQL](https://www.percona.com/software/mysql-database/percona-server) as the base server, the distribution brings you the enterprise-grade [features](#features) for free. The set of carefully selected [components](components.md) helps you operate your MySQL database to meet your application and business needs.

## Features

- **Increased stability and availability** - a set of high-availability and backup options help you ensure your data is saved and available for your business applications. 

- **Improved performance and efficiency** - integrated tools help DBAs maintain, manage and monitor the database performance and timely respond to changing demands. 

- **Reduced costs** - save on purchasing software licensing by using the distribution - the open-source enterprise-grade solution.

- **Easy-to-integrate with PMM** - benefit from all the features of [PMM](https://docs.percona.com/percona-monitoring-and-management/index.html) for monitoring and managing the health of your database. 

!!! important

    This release does not include the Percona Toolkit component. We will add it once a Percona Toolkit version compatible with MySQL 8.4 becomes available.
    
    ProxySQL contains counters that have not been updated to use the new terminology. Unexpected results may occur. In an 8.4.x environment, the binlog reader errors out during initialization due to the use of old terminology, such as the SHOW MASTER STATUS command.

## Get started

Follow the [installation instructions](installing.md) to get started with Percona Distribution for MySQL.

Read more about solutions you can deploy with Percona Distribution for MySQL in [High availability solution with Group Replication](pdps-group-replication.md).

Learn more about what's new in Percona Distribution for MySQL in the [release notes](release-notes.md).

## Read more

* [Deployment variants](deployment-variants.md)
* [Percona Distribution for MySQL components](components.md)