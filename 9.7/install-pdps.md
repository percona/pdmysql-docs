> For the complete documentation index, see [llms.txt](https://docs.percona.com/percona-distribution-for-mysql/9.7/llms.txt).

# Install Percona Server-based variant

We gather [Telemetry data on Percona Server for MySQL](https://docs.percona.com/percona-server/9.7/telemetry.html) in the Percona packages and Docker images.

## Prerequisites

To install Percona software, you need to configure the required repository. To simplify this process, use the `percona-release` repository management tool.

1. Install GnuPG and curl

   ```
   sudo apt install gnupg2 curl
   ```

1. [Install percona-release](https://docs.percona.com/percona-software-repositories/installing.html) . If you have `percona-release` installed, [update percona-release](https://docs.percona.com/percona-software-repositories/updating.html) to the latest version.

## Procedure

**On Debian and Ubuntu Linux**

Important

Run the following commands as the root user or via `sudo`.

### Enable Percona repository

To enable the desired repository, we recommend to use the `enable` subcommand of `percona-release`.

```
sudo percona-release enable pdps-97-lts
```

Tip

To enable the minor version repository, use the following command:

```
sudo percona-release enable pdps-9.7.3
```

### Install Percona Distribution for MySQL packages

1. Install *Percona Server for MySQL*:

   ```
   sudo apt install percona-server-server
   ```

1. Install the components. Use the commands below to install the required components:

   Install Percona XtraBackup:

   ```
   sudo apt install percona-xtrabackup-97
   ```

   Install Percona Toolkit:

   ```
   sudo apt install percona-toolkit
   ```

   Install Orchestrator:

   ```
   sudo apt install percona-orchestrator percona-orchestrator-cli percona-orchestrator-client
   ```

   Install MySQL Shell:

   ```
   sudo apt install percona-mysql-shell
   ```

   Install ProxySQL:

   ```
   sudo apt install proxysql2
   ```

   Install MySQL Router:

   ```
   sudo apt install percona-mysql-router
   ```

**On Red Hat Enterprise Linux and derivatives**

Platform specific notes

On CentOS 7, install the `epel-release` package. It includes the dependencies required to install Orchestrator. Use the following command:

```
sudo yum -y install epel-release
```

Run the following commands as the root user or via `sudo`.

### Enable Percona repository

To enable the desired repository, we recommend to use the `enable` subcommand of `percona-release`.

```
sudo percona-release enable pdps-97-lts
```

Tip

To enable the minor version repository, use the following command:

```
sudo percona-release enable pdps-9.7.3
```

### Install Percona Distribution for MySQL packages

1. Install *Percona Server for MySQL*:

   ```
   sudo yum install percona-server-server
   ```

1. Install the components. Use the commands below to install the required components:

   Install Percona XtraBackup

   ```
   sudo yum install percona-xtrabackup-97
   ```

   Install Orchestrator

   ```
   sudo yum install percona-orchestrator percona-orchestrator-cli percona-orchestrator-client
   ```

   Install Percona Toolkit

   ```
   sudo yum install percona-toolkit
   ```

   Install MySQL Shell:

   ```
   sudo yum install percona-mysql-shell
   ```

   Install ProxySQL:

   ```
   sudo yum install proxysql2
   ```

   Install MySQL Router:

   ```
   sudo yum install percona-mysql-router
   ```

### Run Percona Distribution for MySQL

Percona Distribution for MySQL is not started automatically on Red Hat Enterprise Linux and CentOS after the installation is complete.

Start it manually using the following command:

```
sudo systemctl start mysql
```

Confirm that the service is running:

```
sudo systemctl status mysql
```

Stop the service:

```
sudo systemctl stop mysql
```

## Useful links

[Percona Software Download Instructions](https://docs.percona.com/percona-distribution-for-mysql/9.7/download-instructions.html)
