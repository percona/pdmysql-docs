# Upgrading Percona Distribution for MySQL

Minor releases include bug fixes and feature enhancements. We recommend to have Percona Distribution for MySQL updated to the latest version.

Though minor releases don’t change the behavior, even a minor upgrade is a risky process. We recommend to back up your data before upgrading.

As with installing Percona Distribution for MySQL, the recommended way to upgrade it is from Percona repositories.

!!! admonition "Assumptions"

    We assume that you have [installed](https://www.percona.com/doc/percona-repo-config/installing.html) or [updated](https://www.percona.com/doc/percona-repo-config/updating.html) `percona-release` utility to the latest version.

## Enable Percona repository

The Major Release repository automatically includes new version packages of Percona Distribution for MySQL. If you installed Percona Distribution for MySQL from a Minor Release repository, enable the new version repository:

```
$ sudo percona-release setup pdps-XXX 
```

or

```
$ sudo percona-release setup pdpxc-XXX 
```

where `XXX` is the required version.

Read more about major and Minor release repositories in [Repository overview](installing.md).

## Upgrade *Percona Server for MySQL*-based deployment of Percona Distribution for MySQL

!!! important

    Run all commands as root or via `sudo`


The upgrade steps are:


1. Stop `mysql` service: 

    ```
    $ sudo systemctl mysql stop
    ```

2. [Install new version packages](installing.md#install-percona-distribution-for-mysql-packages) using the package manager of your operating system.


3. Restart `mysql` service: 

   ```
   $ sudo systemctl mysql start
   ```

## Upgrade *Percona XtraDB Cluster*-based deployment of Percona Distribution for MySQL


!!! important

    Run all commands as root or via `sudo`

To upgrade *Percona XtraDB Cluster*, complete these steps sequentially on all nodes:


1. Make sure that all *Percona XtraDB Cluster* nodes are in sync.


2. Stop `mysql` service: 

    ```
    $ sudo systemctl mysql stop
    ```


3. [Install new version packages](installing.md#install-percona-xtradb-cluster-based-deployment) using the package manager of your operating system.


4. Back up the `grastate.dat` file


5. Start `mysql` service: 

    ```
    $ sudo systemctl mysql start
    ```

!!! admonition "See also"

    [Upgrading Percona XtraDB Cluster](https://www.percona.com/doc/percona-xtradb-cluster/LATEST/howtos/upgrade_guide.html#minor-upgrade)

To upgrade the components, refer to [Installing Percona Distribution for MySQL](installing.md) for installation instructions relevant to your operating system.
