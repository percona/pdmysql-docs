# Install Percona Server-based variant

We gather [Telemetry data on Percona Server for MySQL :octicons-link-external-16:](https://docs.percona.com/percona-server/{{vers}}/telemetry.html) in the Percona packages and Docker images.

## Prerequisites

To install Percona software, you need to configure the required repository. To simplify this process, use the `percona-release` repository management tool. 

1. Install GnuPG and curl

    ```shell
    sudo apt install gnupg2 curl
    ```

2. [Install percona-release :octicons-link-external-16:](https://docs.percona.com/percona-software-repositories/installing.html). If you have `percona-release` installed, [update percona-release :octicons-link-external-16:](https://docs.percona.com/percona-software-repositories/updating.html) to the latest version.

## Procedure

=== "On Debian and Ubuntu Linux"

    !!! important

        Run the following commands as the root user or via `sudo`.

    ### Enable Percona repository

    To enable the desired repository, we recommend to use the `enable` subcommand of `percona-release`.

    ```shell
    sudo percona-release enable {{majorpkg}}
    ```

    !!! tip

        To enable the minor version repository, use the following command:

        ```
        sudo percona-release enable {{minorpkg}}
        ```

    ### Install Percona Distribution for MySQL packages

    1. Install *Percona Server for MySQL*:

        ```shell
        sudo apt install percona-server-server
        ```

    2. Install the components. Use the commands below to install the required components:

        Install Percona XtraBackup:

        ```shell
        sudo apt install percona-xtrabackup-97
        ```

        Install Percona Toolkit:

        ```shell
        sudo apt install percona-toolkit
        ```

        Install Orchestrator:

        ```shell
        sudo apt install percona-orchestrator percona-orchestrator-cli percona-orchestrator-client
        ```

        Install MySQL Shell:

        ```shell
        sudo apt install percona-mysql-shell
        ```

        Install ProxySQL:

        ```shell
        sudo apt install proxysql2
        ```

        Install MySQL Router:

        ```shell
        sudo apt install percona-mysql-router
        ```

=== "On Red Hat Enterprise Linux and derivatives"
 
    !!! admonition "Platform specific notes"

        On CentOS 7, install the `epel-release` package. It includes the dependencies required to install Orchestrator. Use the following command:

        ```shell
        sudo yum -y install epel-release
        ```

    Run the following commands as the root user or via `sudo`.

    ### Enable Percona repository

    To enable the desired repository, we recommend to use the `enable` subcommand of `percona-release`.

    ```shell
    sudo percona-release enable {{majorpkg}}
    ```

    !!! tip

        To enable the minor version repository, use the following command:

        ```shell
        sudo percona-release enable {{minorpkg}}
        ```

    ### Install Percona Distribution for MySQL packages

    1. Install *Percona Server for MySQL*:
            
        ```shell
        sudo yum install percona-server-server
        ```

    2. Install the components. Use the commands below to install the required components:

        Install Percona XtraBackup

        ```shell
        sudo yum install percona-xtrabackup-97
        ```

        Install Orchestrator

        ```shell
        sudo yum install percona-orchestrator percona-orchestrator-cli percona-orchestrator-client
        ```

        Install Percona Toolkit

        ```shell
        sudo yum install percona-toolkit
        ```

        Install MySQL Shell:

        ```shell
        sudo yum install percona-mysql-shell
        ```

        Install ProxySQL:

        ```shell
        sudo yum install proxysql2
        ```

        Install MySQL Router:

        ```shell
        sudo yum install percona-mysql-router
        ```

### Run Percona Distribution for MySQL

Percona Distribution for MySQL is not started automatically on Red Hat Enterprise Linux and CentOS after the installation is complete. 

Start it manually using the following command:

```shell
sudo systemctl start mysql
```

Confirm that the service is running:

```shell
sudo systemctl status mysql
```

Stop the service:

```shell
sudo systemctl stop mysql
```

## Useful links

[Percona Software Download Instructions](download-instructions.md)