# Uninstalling Percona Distribution for MySQL

To uninstall Percona Distribution for MySQL, stop the `mysql` service and remove all the installed packages using the package manager of your operating system. Optionally, disable Percona repository.

!!! note

    Should you need the data files later, back up your data before uninstalling Percona Distribution for MySQL.

## Uninstalling *Percona Server for MySQL*-based deployment of Percona Distribution for MySQL

!!! important

    Run all commands as the root user or via `sudo`

=== "On Debian / Ubuntu"


     1. Stop the `mysql` service.

         ```
         $ sudo systemctl stop mysql
         ```

     2. Remove *Percona Server for MySQL*.

         ```
         $ sudo apt remove percona-server*
         ```


     3. Remove the components. Use the following commands to remove the required
     components.

         * Remove Percona XtraBackup
            
            ```
            $ sudo apt remove percona-xtrabackup-80
            ```

         * Remove Percona Toolkit

            ```
            $ sudo apt remove percona-toolkit
            ```

         * Remove Orchestrator
            ```
            $ sudo apt remove percona-orchestrator*
            ```

         * Remove MySQL Shell

            ```
            $ sudo apt remove percona-mysql-shell
            ```

         * Remove ProxySQL

            ```
            $ sudo apt remove proxysql2
            ```

         * Remove MySQL Router

            ```
            $ sudo apt remove percona-mysql-router
            ```

=== "On Red Hat Enterprise Linux / derivatives"

     1. Stop the `mysql` service.

         ```
         $ sudo systemctl stop mysql
         ```

     2. Remove *Percona Server for MySQL*.

         ```
         $ sudo yum remove percona-server*
         ```

     3. Remove the components. Use the commands below to remove the required
     components.

         * Remove Percona XtraBackup
           
            ```
            $ sudo yum remove percona-xtrabackup-80
            ```

         * Remove Percona Toolkit

            ```
            $ sudo yum remove percona-toolkit
            ```

         * Remove Orchestrator

            ```
            $ sudo yum remove percona-orchestrator*
            ```

         * Remove MySQL Shell

            ```
            $ sudo yum remove percona-mysql-shell
            ```

         * Remove ProxySQL

            ```
            $ sudo yum remove proxysql2
            ```

         * Remove MySQL Router

            ```
            $ sudo yum remove percona-mysql-router
            ```

## Uninstalling *Percona XtraDB Cluster*-based deployment of Percona Distribution for MySQL

=== "On Debian / Ubuntu"

     1. Stop the `mysql` service.

         ```
         $ sudo systemctl stop mysql
         ```

     2. Remove *Percona XtraDB Cluster*.

         ```
         $ sudo apt remove percona-xtradb-cluster
         ```

     3. Remove the components. Use the commands below to remove the required
     components.

         * Remove Percona XtraBackup

            ```
            $ sudo apt remove percona-xtrabackup-80
            ```

         * Remove Percona Toolkit

            ```
            $ sudo apt remove percona-toolkit
            ```

=== "On Red Hat Enterprise Linux / derivatives"


     1. Stop the `mysql` service.

         ```
         $ sudo systemctl stop mysql
         ```


     2. Remove *Percona Server for MySQL*.

         ```
         $ sudo yum remove percona-xtradb-cluster
         ```


     3. Remove the components. Use the commands below to remove the required
     components.

        * Remove Percona XtraBackup

           ```
           $ sudo yum remove percona-xtrabackup-80
           ```

        * Remove Percona Toolkit

          ```
          $ sudo yum remove percona-toolkit
          ```

