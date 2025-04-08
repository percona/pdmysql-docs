# Install Percona Distribution for MySQL

We gather [Telemetry data on Percona XtraDB Cluster](https://docs.percona.com/percona-xtradb-cluster/8.0/telemetry.html) and [Telemetry data on Percona Server for MySQL](https://docs.percona.com/percona-server/8.4/telemetry.html) in the Percona packages and Docker images.

We recommend installing Percona Distribution for MySQL from Percona repositories using the package manager of your operating system:

* `apt` - for Debian and Ubuntu Linux
* `yum` - for Red Hat Enterprise Linux and compatible Linux derivatives

Find the full list of supported platforms on the [Percona Software and Platform Lifecycle](https://www.percona.com/services/policies/percona-software-support-lifecycle#mysql) page.

??? admonition "Repository overview: Major and Minor repositories" 

    *Percona* provides two repositories for every deployment variant of Percona Distribution for MySQL.

    The *Major Release repository* includes the latest version packages (for example, `pdps-8.0` and `pdpxc-8.0`). Whenever a package is updated, the package manager of your operating system detects that and prompts you to update. As long as you update all Distribution packages at the same time, you can ensure that the packages you’re using have been tested and verified by *Percona*. Installing Percona Distribution for MySQL from the Major Release Repository is the recommended method.

    The *Minor Release repository* includes a particular minor release of the database and all of the packages that were tested and verified to work with that minor release (for example, `pdps-8.0.40` and `pdpxc-8.0.40`). You may choose to install Percona Distribution for MySQL from the Minor Release repository if you have decided to standardize on a particular release which has passed rigorous testing procedures and which has been verified to work with your applications. This allows you to deploy to a new host and ensure that you’ll be using the same version of all the Distribution packages, even if newer releases exist in other repositories.

    The disadvantage of using a Minor Release repository is that you are locked in this particular release. When potentially critical fixes are released in a later minor version of the database, you will not be prompted for an upgrade by the package manager of your operating system. You would need to change the configured repository in order to install the upgrade.

## Next steps

Select the download option to proceed with the installation.

[Install Percona Server-based variant:material-arrow-right:](install-pdps.md){.md-button}

[Install Percona XtraDB Cluster-based variant:material-arrow-right:](install-pdpxc.md){.md-button}
