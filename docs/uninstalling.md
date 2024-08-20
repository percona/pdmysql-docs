# Uninstalling Percona Distribution for MySQL

To uninstall Percona Distribution for MySQL, stop the `mysql` service and remove all the installed packages using the package manager of your operating system. Optionally, disable Percona repository.

!!! note

    Should you need the data files later, back up your data before uninstalling Percona Distribution for MySQL.


!!! important

    Run all commands as the root user or via `sudo`

=== "On Debian / Ubuntu"


    1. Stop the `mysql` service.

        ```{.bash data-prompt="$"}
        $ sudo systemctl stop mysql
        ```

    2. Remove *Percona Server for MySQL*.

        ```{.bash data-prompt="$"}
        $ sudo apt remove percona-server*
        ```


    3. Remove the components. Use the following commands to remove the required components.

        * Remove Percona XtraBackup
                
          ```{.bash data-prompt="$"}
          $ sudo apt remove percona-xtrabackup-84
          ```

        * Remove Percona Toolkit

          ```{.bash data-prompt="$"}
          $ sudo apt remove percona-toolkit
          ```

        * Remove Orchestrator
                
           ```{.bash data-prompt="$"}
           $ sudo apt remove percona-orchestrator*
           ```

        * Remove MySQL Shell

           ```{.bash data-prompt="$"}
           $ sudo apt remove percona-mysql-shell
           ```

        * Remove ProxySQL

           ```{.bash data-prompt="$"}
           $ sudo apt remove proxysql2
           ```

        * Remove MySQL Router

           ```{.bash data-prompt="$"}
           $ sudo apt remove percona-mysql-router
           ```

=== "On Red Hat Enterprise Linux / derivatives"

    1. Stop the `mysql` service.

        ```{.bash data-prompt="$"}
        $ sudo systemctl stop mysql
        ```

    2. Remove *Percona Server for MySQL*.

        ```{.bash data-prompt="$"}
        $ sudo yum remove percona-server*
        ```

    3. Remove the components. Use the commands below to remove the required components.

        * Remove Percona XtraBackup
               
           ```{.bash data-prompt="$"}
           $ sudo yum remove percona-xtrabackup-84
           ```

        * Remove Percona Toolkit

           ```{.bash data-prompt="$"}
           $ sudo yum remove percona-toolkit
           ```

        * Remove Orchestrator

           ```{.bash data-prompt="$"}
           $ sudo yum remove percona-orchestrator*
           ```

        * Remove MySQL Shell

           ```{.bash data-prompt="$"}
           $ sudo yum remove percona-mysql-shell
           ```

        * Remove ProxySQL

           ```{.bash data-prompt="$"}
           $ sudo yum remove proxysql2
           ```

        * Remove MySQL Router

           ```{.bash data-prompt="$"}
           $ sudo yum remove percona-mysql-router
           ```



