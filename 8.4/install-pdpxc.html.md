> For the complete documentation index, see [llms.txt](https://docs.percona.com/percona-distribution-for-mysql/8.4/llms.txt).

# Install Percona XtraDB Cluster-based variant

We gather [Telemetry data on Percona XtraDB Cluster](https://docs.percona.com/percona-xtradb-cluster/8.4/telemetry.html) in the Percona packages and Docker images.

## Prerequisites

To install Percona software, you need to configure the required repository. To simplify this process, use the `percona-release` repository management tool.

1. Install GnuPG and curl

   ```shell
   sudo apt install gnupg2 curl
   ```

1. [Install percona-release](https://docs.percona.com/percona-software-repositories/installing.html) . If you have `percona-release` installed, [update percona-release](https://docs.percona.com/percona-software-repositories/updating.html) to the latest version.

## Procedure

**On Debian and Ubuntu Linux**

Important

Run the following commands as the root user or via `sudo`.

### Enable Percona repository

To enable the desired repository, we recommend to use the `setup` subcommand of `percona-release`.

```shell
sudo percona-release setup pdpxc-84-lts
```

Tip

To enable either the `pdpxc-8.4.0` or `pdpxc-8.4.2` version repository, use the following command. The example enables the `pdpxc-8.4.11-12` repository:

```shell
sudo percona-release setup pdpxc-8.4.11-12
```

### Install Percona Distribution for MySQL packages

1. Install *Percona XtraDB Cluster*:

   ```shell
   sudo apt install percona-xtradb-cluster
   ```

1. Install HAProxy:

   ```shell
   sudo apt install percona-haproxy
   ```

1. Install the components. Use the commands below to install the required components:

   Install Percona XtraBackup:

   ```shell
   sudo apt install percona-xtrabackup-84
   ```

   Install Percona Toolkit:

   ```shell
   sudo apt install percona-toolkit
   ```

**On Red Hat Enterprise Linux and derivatives**

Important

Run the following commands as the root user or via `sudo`.

### Enable Percona repository

To enable the desired repository, we recommend to use the `setup` subcommand of `percona-release`.

```shell
sudo percona-release setup pdpxc-84-lts
```

Tip

To enable either the `pdpxc-8.4.0` or `pdpxc-8.4.2` version repository, use the following command. The example enables the `pdpxc-8.4.11-12` repository:

```shell
sudo percona-release setup pdpxc-8.4.11-12
```

### Install Percona Distribution for MySQL packages

1. Install *Percona XtraDB Cluster*:

   ```shell
   sudo yum install percona-xtradb-cluster
   ```

1. Install HAProxy:

   ```shell
   sudo yum install percona-haproxy
   ```

1. Install the components. Use the commands below to install the required components:

   Install Percona XtraBackup:

   ```shell
   sudo yum install percona-xtrabackup-84
   ```

   Install Percona Toolkit:

   ```shell
   sudo yum install percona-toolkit
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

[Percona Software Download Instructions](https://docs.percona.com/percona-distribution-for-mysql/8.4/download-instructions.md)
