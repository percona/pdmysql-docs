# Uninstalling Percona Distribution for MySQL

To uninstall Percona Distribution for MySQL, stop the `mysql` service and remove all the installed packages using the package manager of your operating system. Optionally, disable Percona repository.

!!! note

    Should you need the data files later, back up your data before uninstalling Percona Distribution for MySQL.


=== "Uninstall Percona Server-based variant" 

    !!! important

        Run all commands as the root user or via `sudo`

    === "On Debian / Ubuntu"


         1. Stop the `mysql` service.

             ```shell
             sudo systemctl stop mysql
             ```

         2. Remove *Percona Server for MySQL*.

             ```shell
             sudo apt remove percona-server*
             ```


         3. Remove the components. Use the following commands to remove the required
         components.

             * Remove Percona XtraBackup
                
                ```shell
                sudo apt remove percona-xtrabackup-97
                ```

             * Remove Percona Toolkit

                ```shell
                sudo apt remove percona-toolkit
                ```

             * Remove Orchestrator
                
                ```shell
                sudo apt remove percona-orchestrator*
                ```

             * Remove MySQL Shell

                ```shell
                sudo apt remove percona-mysql-shell
                ```

             * Remove ProxySQL

                ```shell
                sudo apt remove proxysql2
                ```

             * Remove MySQL Router

                ```shell
                sudo apt remove percona-mysql-router
                ```

    === "On Red Hat Enterprise Linux / derivatives"

         1. Stop the `mysql` service.

             ```shell
             sudo systemctl stop mysql
             ```

         2. Remove *Percona Server for MySQL*.

             ```shell
             sudo yum remove percona-server*
             ```

         3. Remove the components. Use the commands below to remove the required
         components.

             * Remove Percona XtraBackup
               
                ```shell
                sudo yum remove percona-xtrabackup-97
                ```

             * Remove Percona Toolkit

                ```shell
                sudo yum remove percona-toolkit
                ```

             * Remove Orchestrator

                ```shell
                sudo yum remove percona-orchestrator*
                ```

             * Remove MySQL Shell

                ```shell
                sudo yum remove percona-mysql-shell
                ```

             * Remove ProxySQL

                ```shell
                sudo yum remove proxysql2
                ```

             * Remove MySQL Router

                ```shell
                sudo yum remove percona-mysql-router
                ```

=== "Uninstall Percona XtraDB Cluster-based variant"

    !!! important

        Run all commands as the root user or via `sudo`


    === "On Debian / Ubuntu"

         1. Stop the `mysql` service.

             ```shell
             sudo systemctl stop mysql
             ```

         2. Remove *Percona XtraDB Cluster*.

             ```shell
             sudo apt remove percona-xtradb-cluster
             ```

         3. Remove the components. Use the commands below to remove the required
         components.

             * Remove Percona XtraBackup

                ```shell
                sudo apt remove percona-xtrabackup-97
                ```

             * Remove Percona Toolkit

                ```shell
                sudo apt remove percona-toolkit
                ```

    === "On Red Hat Enterprise Linux / derivatives"


         1. Stop the `mysql` service.

             ```shell
             sudo systemctl stop mysql
             ```


         2. Remove *Percona Server for MySQL*.

             ```shell
             sudo yum remove percona-xtradb-cluster
             ```


         3. Remove the components. Use the commands below to remove the required
         components.

            * Remove Percona XtraBackup

               ```shell
               sudo yum remove percona-xtrabackup-97
               ```

            * Remove Percona Toolkit

              ```shell
              sudo yum remove percona-toolkit
              ```
