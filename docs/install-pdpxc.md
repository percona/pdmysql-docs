# Install Percona XtraDB Cluster-based variant

We gather [Telemetry data on Percona XtraDB Cluster](https://docs.percona.com/percona-xtradb-cluster/8.4/telemetry.html) in the Percona packages and Docker images.

## Prerequisites

To install Percona software, you need to configure the required repository. To simplify this process, use the `percona-release` repository management tool. 

1. Install GnuPG and curl

    ```{.bash data-prompt="$"}
    $ sudo apt install gnupg2 curl
    ```

2. [Install percona-release](https://www.percona.com/doc/percona-repo-config/installing.html). If you have it installed, [update percona-release](https://www.percona.com/doc/percona-repo-config/updating.html) to the latest version.

## Procedure

=== "On Debian and Ubuntu Linux"

    !!! important

        Run the following commands as the root user or via `sudo`.

    ### Enable Percona repository

    To enable the desired repository, we recommend to use the `setup` subcommand of `percona-release`.

    ```{.bash data-prompt="$"}
    $ sudo percona-release setup {{majorpkgpxc}}
    ```

    !!! tip

        To enable either the `pdpxc-8.4.0` or `pdpxc-8.4.2` version repository, use the following command. The example enables the `8.4.2` repository:

        ```{.bash data-prompt="$"}
        $ sudo percona-release setup {{minorpkgpxc}}
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
        $ sudo apt install percona-xtrabackup-84
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
    $ sudo percona-release setup {{majorpkgpxc}}
    ```

    !!! tip

        To enable either the `pdpxc-8.4.0` or `pdpxc-8.4.2` version repository, use the following command. The example enables the `8.4.2` repository:

        ```{.bash data-prompt="$"}
        $ sudo percona-release setup {{minorpkgpxc}}
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
        $ sudo yum install percona-xtrabackup-84
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

## Useful links

[Percona Software Download Instructions](download-instructions.md)