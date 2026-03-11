# Upgrade Percona Distribution for MySQL

<!-- Clarify whether the following note is valid for 9.7-->

!!! important

    This release does not include the Percona Toolkit component. We will add it once a Percona Toolkit version compatible with MySQL {{vers}} becomes available.
    
    In {{vers}}.x environments, the ProxySQL binlog reader can fail to initialize because it uses legacy commands, such as SHOW MASTER STATUS. Some internal counters also use outdated terminology. To address most terminology issues, enable the [terminology_use_previous](https://dev.mysql.com/doc/refman/{{vers}}/en/replication-options-replica.html#sysvar_terminology_use_previous) system variable on the database server. This workaround addresses only terminology compatibility and may not fix all failures.

Minor releases include bug fixes and feature enhancements. We recommend to have Percona Distribution for MySQL updated to the latest version.

Though minor releases don’t change the behavior, even a minor upgrade is a risky process. We recommend to back up your data before upgrading.

## Preconditions

To upgrade Percona Distribution for MySQL, [install the `percona-release` repository management tool :octicons-link-external-16:](https://docs.percona.com/percona-software-repositories/installing.html) or [update the `percona-release` tool :octicons-link-external-16:](https://docs.percona.com/percona-software-repositories/updating.html) to the latest version.

## Procedure

!!! important

    Run the following commands as the root user or via `sudo`.

=== "Upgrade Percona Server-based variant" 

    1. Enable Percona repository

        The Major Release repository automatically includes new version packages of Percona Distribution for MySQL. If you installed Percona Distribution for MySQL from a Minor Release repository, enable the new version repository:

        ```shell
        sudo percona-release setup pdps-XXX 
        ```

        where `XXX` is the required version.

        Read more about major and Minor release repositories in [Repository overview](installing.md).

    2. Stop `mysql` service 

        ```shell
        sudo systemctl mysql stop
        ```

    3. [Install new version packages](installing.md#install-percona-distribution-for-mysql) using the package manager of your operating system.

    4. Restart `mysql` service: 

        ```shell
        sudo systemctl mysql start
        ```

=== "Upgrade Percona XtraDBCluster-based variant" 
    
    Complete these steps sequentially on all nodes:

    1. Enable Percona repository

        The Major Release repository automatically includes new version packages of Percona Distribution for MySQL. If you installed Percona Distribution for MySQL from a Minor Release repository, enable the new version repository:

         ```shell
         sudo percona-release setup pdpxc-XXX 
         ```

         where `XXX` is the required version.

         Read more about major and Minor release repositories in [Repository overview](installing.md).

    2. Stop `mysql` service

        ```shell
        sudo systemctl mysql stop
        ```

    3. [Install new version packages](installing.md#install-percona-distribution-for-mysql) using the package manager of your operating system.

    4. Back up the `grastate.dat` file

    5. Restart `mysql` service 

        ```shell
        sudo systemctl mysql start
        ```
    
    !!! admonition "See also"

        [Upgrading Percona XtraDB Cluster :octicons-link-external-16:](https://docs.percona.com/percona-xtradb-cluster/{{vers}}/upgrade-guide.html)

To upgrade the components, refer to [Installing Percona Distribution for MySQL](installing.md) for installation instructions relevant to your operating system.
