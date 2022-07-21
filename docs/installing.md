# Installing Percona Distribution for MySQL

Percona Distribution for MySQL packages are available in **DEB** and **RPM** formats for the most 64-bit Linux distributions. Find the full list of supported platforms on the [Percona Software and Platform Lifecycle](https://www.percona.com/services/policies/percona-software-support-lifecycle#mysql) page.

Like other Percona products, we recommend to install Percona Distribution for MySQL from Percona repositories using the **percona-release** utility.

??? admonition "Repository overview: Major and Minor repositories" 

    *Percona* provides two repositories for every deployment variant of Percona Distribution for MySQL.

    The *Major Release repository* includes the latest version packages (e.g. `pdps-8.0` and `pdpxc-8.0`). Whenever a package is updated, the package manager of your operating system detects that and prompts you to update. As long as you update all Distribution packages at the same time, you can ensure that the packages you’re using have been tested and verified by *Percona*. Installing Percona Distribution for MySQL from the Major Release Repository is the recommended method.

    The *Minor Release repository* includes a particular minor release of the database and all of the packages that were tested and verified to work with that minor release (e.g. `pdps-8.0.19` and `pdpxc-8.0.19`). You may choose to install Percona Distribution for MySQL from the Minor Release repository if you have decided to standardize on a particular release which has passed rigorous testing procedures and which has been verified to work with your applications. This allows you to deploy to a new host and ensure that you’ll be using the same version of all the Distribution packages, even if newer releases exist in other repositories.

    The disadvantage of using a Minor Release repository is that you are locked in this particular release. When potentially critical fixes are released in a later minor version of the database, you will not be prompted for an upgrade by the package manager of your operating system. You would need to change the configured repository in order to install the upgrade.

## Install GnuPG and curl
Install `gnupg2` and `curl`, if not already installed. Those packages are required for installing Percona Distribution for MySQL.

```sh
$ sudo apt install gnupg2 curl
```

## Install `percona-release` utility

[Install percona-release](https://www.percona.com/doc/percona-repo-config/installing.html). If you have it installed, [update percona-release](https://www.percona.com/doc/percona-repo-config/updating.html) to the latest version.

## Enable Percona repository

To enable the desired repository, we recommend to use the `setup` subcommand of `percona-release`.

Run `percona-release` as the root user or via **sudo**. For the
sake of convenience, all commands that require elevated privileges start with
**sudo** in the following procedures.


* For *Percona Server for MySQL*-based deployment, use the following command:

```sh
$ sudo percona-release setup pdps-8.0
```


* For *Percona XtraDB Cluster*-based deployment, use the following command:

```sh
$ sudo percona-release setup pdpxc-8.0
```

!!! hint

    To enable the minor version repository, use the following command:

    * For PS-based deployment: 

       ```
       $ sudo percona-release setup pdps-8.0.20
       ```

    * For PXC-based deployment:

       ```
       $ sudo percona-relase setup pdpxc-8.0.20
       ```



## Install Percona Distribution for MySQL packages

Install the selected deployment of Percona Distribution for MySQL using the commands of the package manager of your operating system.

!!! important

    Run all commands as root or via `sudo`

### Install *Percona Server for MySQL*-based deployment 

=== "On Debian / Ubuntu"


     1. Install *Percona Server for MySQL*:

         ```
         $ sudo apt install percona-server-server
         ```


     2. Install the components. Use the commands below to install the required components:

        Install Percona XtraBackup:

          ```
          $ sudo apt install percona-xtrabackup-80
          ```

        Install Percona Toolkit:

          ```
          $ sudo apt install percona-toolkit
          ```

        Install Orchestrator:

          ```
          $ sudo apt install percona-orchestrator percona-orchestrator-cli percona-orchestrator-client
          ```

        Install MySQL Shell:

          ```
          $ sudo apt install percona-mysql-shell
          ```

        Install ProxySQL:

          ```
          $ sudo apt install proxysql2
          ```

        Install MySQL Router:

          ```
          $ sudo apt install percona-mysql-router
          ```

=== "On Red Hat Enterprise Linux and derivatives"

      **Platform specific notes**

      On CentOS 7, install the `epel-release` package. It includes the dependencies required to install Orchestrator. Use the following command:

      ```
      $ sudo yum -y install epel-release
      ```
       
     --------------------------------------------------------------------------

     1. Install *Percona Server for MySQL*:

         ```
         $ sudo yum install percona-server-server
         ```


     2. Install the components. Use the commands below to install the required components:

        Install Percona XtraBackup

         ```
         $ sudo yum install percona-xtrabackup-80
         ```

        Install Orchestrator

         ```
         $ sudo yum install percona-orchestrator percona-orchestrator-cli percona-orchestrator-client
         ```

        Install Percona Toolkit

         ```
         $ sudo yum install percona-toolkit
         ```

        Install MySQL Shell:

         ```
         $ sudo yum install percona-mysql-shell
         ```

        Install ProxySQL:

         ```
         $ sudo yum install proxysql2
         ```

        Install MySQL Router:

         ```
         $ sudo yum install percona-mysql-router
         ```

     **Run Percona Distribution for MySQL**

     Percona Distribution for MySQL is not started automatically on Red Hat Enterprise Linux and CentOS after the installation is complete. 

     Start it manually using the following command:

     ```
     $ sudo systemctl start mysql
     ```

     Confirm that the service is running:

     ```
     $ sudo systemctl status mysql
     ```

     Stop the service:

     ```
     $ sudo systemctl stop mysql
     ```



### Install *Percona XtraDB Cluster*-based deployment 

!!! important

    Run all commands as root or via `sudo`
    
=== "On Debian / Ubuntu"

     1. Install *Percona XtraDB Cluster*:

         ```
         $ sudo apt install percona-xtradb-cluster
         ```


     2. Install HAProxy:

         ```
         $ sudo apt install percona-haproxy
         ```


     3. Install the components. Use the commands below to install the required components:

        Install Percona XtraBackup:

         ```
         $ sudo apt install percona-xtrabackup-80
         ```

        Install Percona Toolkit:

         ```
         $ sudo apt install percona-toolkit
         ```

     
=== "On Red Hat Enterprise Linux and derivatives"


     1. Install *Percona XtraDB Cluster*:

         ```
         $ sudo yum install percona-xtradb-cluster
         ```


     2. Install HAProxy:

         ```
         $ sudo yum install percona-haproxy
         ```


     3. Install the components. Use the commands below to install the required components:

        Install Percona XtraBackup:

         ```
         $ sudo yum install percona-xtrabackup-80
         ```

        Install Percona Toolkit:

         ```
         $ sudo yum install percona-toolkit
         ```
     
     **Run Percona Distribution for MySQL**

     Percona Distribution for MySQL is not started automatically on Red Hat Enterprise Linux and CentOS after the installation is complete. 

     Start it manually using the following command:

     ```
     $ sudo systemctl start mysql
     ```

     Confirm that the service is running:

     ```
     $ sudo systemctl status mysql
     ```

     Stop the service:

     ```
     $ sudo systemctl stop mysql
     ```


