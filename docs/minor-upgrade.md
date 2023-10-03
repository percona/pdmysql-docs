# Upgrade Percona Distribution for MySQL

Minor releases include bug fixes and feature enhancements. We recommend to have Percona Distribution for MySQL updated to the latest version.

Though minor releases don’t change the behavior, even a minor upgrade is a risky process. We recommend to back up your data before upgrading.

## Preconditions

To upgrade Percona Distribution for MySQL, [install the `percona-release` repository management tool](https://www.percona.com/doc/percona-repo-config/installing.html) or [update it](https://www.percona.com/doc/percona-repo-config/updating.html) to the latest version.

## Procedure

!!! important

    Run the following commands as the root user or via `sudo`.


1. Enable Percona repository

    The Major Release repository automatically includes new version packages of Percona Distribution for MySQL. If you installed Percona Distribution for MySQL from a Minor Release repository, enable the new version repository:

    ```{.bash data-prompt="$"}
    $ sudo percona-release setup pdps-XXX 
    ```

    where `XXX` is the required version.

    Read more about major and Minor release repositories in [Repository overview](installing.md).

2. Stop `mysql` service 

    ```{.bash data-prompt="$"}
    $ sudo systemctl mysql stop
    ```

3. [Install new version packages](installing.md#procedure) using the package manager of your operating system.

4. Restart `mysql` service: 

    ```{.bash data-prompt="$"}
    $ sudo systemctl mysql start
    ```

To upgrade the components, refer to [Installing Percona Distribution for MySQL](installing.md) for installation instructions relevant to your operating system.
