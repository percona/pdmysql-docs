> For the complete documentation index, see [llms.txt](https://docs.percona.com/percona-distribution-for-mysql/9.7/llms.txt).

# Install Percona Distribution for MySQL

Important

This release does not include the Percona Toolkit component. We will add it once a Percona Toolkit version compatible with MySQL 9.7 becomes available.

In 9.7.x environments, the ProxySQL binlog reader can fail to initialize because it uses legacy commands, such as SHOW MASTER STATUS. Some internal counters also use outdated terminology. To address most terminology issues, enable the [terminology_use_previous](https://dev.mysql.com/doc/refman/9.7/en/replication-options-replica.html#sysvar_terminology_use_previous) system variable on the database server. This workaround addresses only terminology compatibility and may not fix all failures.

We recommend to install Percona Distribution for MySQL from Percona repositories using the package manager of your operating system:

- `APT` - for Debian and Ubuntu Linux
- `YUM` or `DNF` - for Red Hat Enterprise Linux and compatible Linux derivatives

Find the full list of supported platforms on the [Percona Software and Platform Lifecycle](https://www.percona.com/release-lifecycle-overview/#mysql) page.

Repository overview: Major and Minor repositories

*Percona* provides two repositories for every deployment variant of Percona Distribution for MySQL.

The *Major Release repository* includes the latest version packages (for example, `pdps-97`). Whenever a package is updated, the package manager of your operating system detects that and prompts you to update. As long as you update all Distribution packages at the same time, you can ensure that the packages you’re using have been tested and verified by *Percona*. Installing Percona Distribution for MySQL from the Major Release Repository is the recommended method.

The *Minor Release repository* includes a particular minor release of the database and all of the packages that were tested and verified to work with that minor release (for example, `pdps-9.7.0`). You may choose to install Percona Distribution for MySQL from the Minor Release repository if you have decided to standardize on a particular release which has passed rigorous testing procedures and which has been verified to work with your applications. This allows you to deploy to a new host and ensure that you’ll be using the same version of all the Distribution packages, even if newer releases exist in other repositories.

The disadvantage of using a Minor Release repository is that you are locked in this particular release. When potentially critical fixes are released in a later minor version of the database, you will not be prompted for an upgrade by the package manager of your operating system. You would need to change the configured repository in order to install the upgrade.

## Next steps

Select the download option to proceed with the installation.

[Install Percona Server-based variant](https://docs.percona.com/percona-distribution-for-mysql/9.7/install-pdps.html)

[Install Percona XtraDB Cluster-based variant](https://docs.percona.com/percona-distribution-for-mysql/9.7/install-pdpxc.html)
