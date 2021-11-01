.. _pdmysql.uninstall:

********************************************************************************
Uninstalling |pdmysql|
********************************************************************************

.. contents::
   :local:
   :depth: 2

To uninstall |pdmysql|, stop the ``mysql`` service and remove all the installed packages using the package manager of your operating system. Optionally, disable |percona| repository.

.. note::

   Should you need the data files later, back up your data before uninstalling |pdmysql|.

Uninstalling |PS|-based deployment of |pdmysql|
================================================================================

.. important::

   Run all commands as root or via |sudo|.

On Debian / Ubuntu
--------------------------------------------------------------------------------

1. Stop the ``mysql`` service.
   
   .. code-block:: bash
   
      $ sudo systemctl stop mysql 
       
#. Remove |PS|.
   
   .. code-block:: bash
    
      $ sudo apt remove percona-server*

#. Remove the components. Use the commands below to remove the required 
   components.

   .. code-block:: bash
          
      $ #Remove Percona XtraBackup
      $ sudo apt remove percona-xtrabackup-80
      $ #Remove Percona Toolkit
      $ sudo apt remove percona-toolkit
      $ #Remove Orchestrator
      $ sudo apt remove percona-orchestrator* 
      $ #Remove MySQL Shell
      $ sudo apt remove percona-mysql-shell
      $ #Remove ProxySQL
      $ sudo apt remove proxysql2
      $ #Remove MySQL Router
      $ sudo apt remove percona-mysql-router        
   
On |RHEL| / |centos|
--------------------------------------------------------------------------------

1. Stop the ``mysql`` service.
   
   .. code-block:: bash
   
      $ sudo systemctl stop mysql 
       
#. Remove |PS|.
   
   .. code-block:: bash
    
      $ sudo yum remove percona-server*

#. Remove the components. Use the commands below to remove the required 
   components.

   .. code-block:: bash
          
      $ #Remove Percona XtraBackup
      $ sudo yum remove percona-xtrabackup-80
      $ #Remove Percona Toolkit
      $ sudo yum remove percona-toolkit
      $ #Remove Orchestrator
      $ sudo yum remove percona-orchestrator* 
      $ #Remove MySQL Shell
      $ sudo yum remove percona-mysql-shell
      $ #Remove ProxySQL
      $ sudo yum remove proxysql2
      $ #Remove MySQL Router
      $ sudo yum remove percona-mysql-router     
  
.. seealso::

   * Uninstall |PS|:
   
     - `On Debian and Ubuntu <https://www.percona.com/doc/percona-server/8.0/installation/apt_repo.html#unRemoveing-percona-server>`_
     - `On Red Hat Enterprise Linux and CentOS <https://www.percona.com/doc/percona-server/8.0/installation/yum_repo.html#unRemoveing-percona-server>`_
   * Uninstall |PXB|:
   
     - `On Debian and Ubuntu <https://www.percona.com/doc/percona-xtrabackup/8.0/installation/apt_repo.html#uninstalling-percona-xtrabackup>`_
     -  `On Red Hat Enterprise Linux and CentOS <https://www.percona.com/doc/percona-xtrabackup/8.0/installation/yum_repo.html#uninstalling-percona-xtrabackup>`_

Uninstalling |PXC|-based deployment of |pdmysql|
================================================================================

.. important::

   Run all commands as root or via |sudo|.

On Debian / Ubuntu
--------------------------------------------------------------------------------

1. Stop the ``mysql`` service.
   
   .. code-block:: bash
   
      $ sudo systemctl stop mysql 
       
#. Remove |PXC|.
   
   .. code-block:: bash
    
      $ sudo apt remove percona-xtradb-cluster

#. Remove the components. Use the commands below to remove the required 
   components.

   .. code-block:: bash
          
      $ #Remove Percona XtraBackup
      $ sudo apt remove percona-xtrabackup-80
      $ #Remove Percona Toolkit
      $ sudo apt remove percona-toolkit
      
On |RHEL| / |centos|
--------------------------------------------------------------------------------

1. Stop the ``mysql`` service.
   
   .. code-block:: bash
   
      $ sudo systemctl stop mysql 
       
#. Remove |PS|.
   
   .. code-block:: bash
    
      $ sudo yum remove percona-xtradb-cluster

#. Remove the components. Use the commands below to remove the required 
   components.

   .. code-block:: bash
          
      $ #Remove Percona XtraBackup
      $ sudo yum remove percona-xtrabackup-80
      $ #Remove Percona Toolkit
      $ sudo yum remove percona-toolkit

.. include:: .res/replace.txt