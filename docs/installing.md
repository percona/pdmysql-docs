# Install Percona Distribution for MySQL

We recommend to install Percona Distribution for MySQL from Percona repositories using the package manager of your operating system:

* `apt` - for Debian and Ubuntu Linux
* `yum` - for Red Hat Enterprise Linux and compatible Linux derivatives

Find the full list of supported platforms on the [Percona Software and Platform Lifecycle](https://www.percona.com/services/policies/percona-software-support-lifecycle#mysql) page.

??? admonition "Repository overview: Major and Minor repositories" 

    *Percona* provides two repositories for every deployment variant of Percona Distribution for MySQL.

    The *Major Release repository* includes the latest version packages (e.g. `pdps-8.0` and `pdpxc-8.0`). Whenever a package is updated, the package manager of your operating system detects that and prompts you to update. As long as you update all Distribution packages at the same time, you can ensure that the packages you’re using have been tested and verified by *Percona*. Installing Percona Distribution for MySQL from the Major Release Repository is the recommended method.

    The *Minor Release repository* includes a particular minor release of the database and all of the packages that were tested and verified to work with that minor release (e.g. `pdps-8.0.19` and `pdpxc-8.0.19`). You may choose to install Percona Distribution for MySQL from the Minor Release repository if you have decided to standardize on a particular release which has passed rigorous testing procedures and which has been verified to work with your applications. This allows you to deploy to a new host and ensure that you’ll be using the same version of all the Distribution packages, even if newer releases exist in other repositories.

    The disadvantage of using a Minor Release repository is that you are locked in this particular release. When potentially critical fixes are released in a later minor version of the database, you will not be prompted for an upgrade by the package manager of your operating system. You would need to change the configured repository in order to install the upgrade.

## Prerequisites

To install Percona software, you need to configure the required repository. To simplify this process, use the `percona-release` repository management tool. 

1. Install GnuPG and curl

    ```{.bash data-prompt="$"}
    $ sudo apt install gnupg2 curl
    ```

2. [Install percona-release](https://www.percona.com/doc/percona-repo-config/installing.html). If you have it installed, [update percona-release](https://www.percona.com/doc/percona-repo-config/updating.html) to the latest version.

## Procedure

=== "Install Percona Server-based variant"

    === "On Debian and Ubuntu Linux"

        !!! important

            Run the following commands as the root user or via `sudo`.

        ### Enable Percona repository

        To enable the desired repository, we recommend to use the `setup` subcommand of `percona-release`.

          ```{.bash data-prompt="$"}
          $ sudo percona-release setup pdps-8.0
          ```

        !!! tip

            To enable the minor version repository, use the following command:

            ```{.bash data-prompt="$"}
            $ sudo percona-release setup pdps-8.0.20
            ```

        ### Install Percona Distribution for MySQL packages

          1. Install *Percona Server for MySQL*:

              ```{.bash data-prompt="$"}
              $ sudo apt install percona-server-server
              ```

          2. Install the components. Use the commands below to install the required components:

              Install Percona XtraBackup:

               ```{.bash data-prompt="$"}
               $ sudo apt install percona-xtrabackup-80
               ```

              Install Percona Toolkit:

               ```{.bash data-prompt="$"}
               $ sudo apt install percona-toolkit
               ```

              Install Orchestrator:

               ```{.bash data-prompt="$"}
               $ sudo apt install percona-orchestrator percona-orchestrator-cli percona-orchestrator-client
               ```

              Install MySQL Shell:

               ```{.bash data-prompt="$"}
               $ sudo apt install percona-mysql-shell
               ```

              Install ProxySQL:

               ```{.bash data-prompt="$"}
               $ sudo apt install proxysql2
               ```

              Install MySQL Router:

               ```{.bash data-prompt="$"}
               $ sudo apt install percona-mysql-router
               ```

    === "On Red Hat Enterprise Linux and derivatives"
 
        !!! admonition "Platform specific notes"

            On CentOS 7, install the `epel-release` package. It includes the dependencies required to install Orchestrator. Use the following command:

            ```{.bash data-prompt="$"}
            $ sudo yum -y install epel-release
            ```

        Run the following commands as the root user or via `sudo`.

        ### Enable Percona repository

        To enable the desired repository, we recommend to use the `setup` subcommand of `percona-release`.

          ```{.bash data-prompt="$"}
          $ sudo percona-release setup pdps-8.0
          ```

        !!! tip

            To enable the minor version repository, use the following command:

            ```{.bash data-prompt="$"}
            $ sudo percona-release setup pdps-8.0.20
            ```

        ### Install Percona Distribution for MySQL packages

          1. Install *Percona Server for MySQL*:

              ```{.bash data-prompt="$"}
              $ sudo yum install percona-server-server
              ```


          2. Install the components. Use the commands below to install the required components:

             Install Percona XtraBackup

              ```{.bash data-prompt="$"}
              $ sudo yum install percona-xtrabackup-80
              ```

             Install Orchestrator

              ```{.bash data-prompt="$"}
              $ sudo yum install percona-orchestrator percona-orchestrator-cli percona-orchestrator-client
              ```

             Install Percona Toolkit

              ```{.bash data-prompt="$"}
              $ sudo yum install percona-toolkit
              ```

             Install MySQL Shell:

              ```{.bash data-prompt="$"}
              $ sudo yum install percona-mysql-shell
              ```

             Install ProxySQL:

              ```{.bash data-prompt="$"}
              $ sudo yum install proxysql2
              ```

             Install MySQL Router:

              ```{.bash data-prompt="$"}
              $ sudo yum install percona-mysql-router
              ```

=== "Install Percona XtraDB Cluster-based variant"

    === "On Debian and Ubuntu Linux"

        !!! important

            Run the following commands as the root user or via `sudo`.

        ### Enable Percona repository

        To enable the desired repository, we recommend to use the `setup` subcommand of `percona-release`.

          ```{.bash data-prompt="$"}
          $ sudo percona-release setup pdps-8.0
          ```

        !!! tip

            To enable the minor version repository, use the following command:

            ```{.bash data-prompt="$"}
            $ sudo percona-release setup pdpxc-8.0.20
            ```

        ### Install Percona Distribution for MySQL packages

         1. Install *Percona XtraDB Cluster*:

             ```{.bash data-prompt="$"}
             $ sudo apt install percona-xtradb-cluster
             ```


         2. Install HAProxy:

             ```{.bash data-prompt="$"}
             $ sudo apt install percona-haproxy
             ```


         3. Install the components. Use the commands below to install the required components:

            Install Percona XtraBackup:

             ```{.bash data-prompt="$"}
             $ sudo apt install percona-xtrabackup-80
             ```

            Install Percona Toolkit:

             ```{.bash data-prompt="$"}
             $ sudo apt install percona-toolkit
             ```

    === "On Red Hat Enterprise Linux and derivatives"

        !!! important

            Run the following commands as the root user or via `sudo`.

        ### Enable Percona repository

        To enable the desired repository, we recommend to use the `setup` subcommand of `percona-release`.

          ```{.bash data-prompt="$"}
          $ sudo percona-release setup pdps-8.0
          ```

        !!! tip

            To enable the minor version repository, use the following command:

            ```{.bash data-prompt="$"}
            $ sudo percona-release setup pdpxc-8.0.20
            ```

        ### Install Percona Distribution for MySQL packages


         1. Install *Percona XtraDB Cluster*:

             ```{.bash data-prompt="$"}
             $ sudo yum install percona-xtradb-cluster
             ```


         2. Install HAProxy:

             ```{.bash data-prompt="$"}
             $ sudo yum install percona-haproxy
             ```


         3. Install the components. Use the commands below to install the required components:

            Install Percona XtraBackup:

             ```{.bash data-prompt="$"}
             $ sudo yum install percona-xtrabackup-80
             ```

            Install Percona Toolkit:

             ```{.bash data-prompt="$"}
             $ sudo yum install percona-toolkit
             ```
         

### Run Percona Distribution for MySQL

Percona Distribution for MySQL is not started automatically on Red Hat Enterprise Linux and CentOS after the installation is complete. 

Start it manually using the following command:

```{.bash data-prompt="$"}
$ sudo systemctl start mysql
```

Confirm that the service is running:

```{.bash data-prompt="$"}
$ sudo systemctl status mysql
```

Stop the service:

```{.bash data-prompt="$"}
$ sudo systemctl stop mysql
```


