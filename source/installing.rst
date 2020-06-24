.. _installation:

**********************************************************************
Installing |pdmysql|                                                  
**********************************************************************

.. contents::
   :local:
   :depth: 2

|pdmysql| packages are available in |deb| and |rpm| formats for these supported platforms: 

.. list-table:: Supported Linux platforms
   :widths: 30 30
   :header-rows: 1
 
   * - DEB-based platforms
     - RPM-based platforms
   * - Ubuntu 16.04
     - |centos| and |RHEL| 7
   * - Ubuntu 18.04
     - |RHEL| 8
   * - Ubuntu 20.04
     - 
   * - Debian 9 (stretch)
     - 
   * - Debian 10 (buster)
     -

|pdmysql| is only available for the x86_64 platform (also
known as amd64).


Overview
================================================================================

Like other |percona| products, we recommend to install |pdmysql| from |percona|
repositories using the |percona-release| utility.

|Percona| provides two repositories for every deployment variant of |pdmysql|.

The *Major Release repository* includes the latest version packages (e.g. ``pdps-8.0`` and ``pdpxc-8.0``). Whenever a package is updated, the package manager of your operating system detects that and prompts you to update. As long as you update all Distribution packages at the same time, you can ensure that the packages you're using have been tested and verified by |Percona|. Installing |pdmysql| from the Major Release Repository is the recommended method. 

The *Minor Release repository* includes a particular minor release of the database and all of the packages that were tested and verified to work with that minor release (e.g. ``pdps-8.0.19`` and ``pdpxc-8.0.19``). You may choose to install |pdmysql| from the Minor Release repository if you have decided to standardize on a particular release which has passed rigorous testing procedures and which has been verified to work with your applications. This allows you to deploy to a new host and ensure that you'll be using the same version of all the Distribution packages, even if newer releases exist in other repositories.

The disadvantage of using a Minor Release repository is that you are locked in this particular release. When potentially critical fixes are released in a later minor version of the database, you will not be prompted for an upgrade by the package manager of your operating system. You would need to change the configured repository in order to install the upgrade.

Prerequisites
================================================================================

Install |percona-release| if you haven't done it already. Otherwise, update it to the latest version. Please refer to `Percona repositories documentation <https://www.percona.com/doc/percona-repo-config/percona-release.html>`_ for installation or update instructions.

Enable Percona repository       
================================================================================

We recommend to use the ``setup`` subcommand of |percona-release| to enable the desired repository.
 
* For |PS|-based deployment, use the following command:

  .. code-block:: bash

     $ sudo percona-release setup pdps-8.0

* For |PXC|-based deployment, use the following command:

  .. code-block:: bash

     $ sudo percona-release setup pdpxc-8.0

.. hint::

   To enable the minor version repository, use the following command:

   .. code-block:: bash
   
      $ #For PS-based deployment
      $ sudo percona-release setup pdps-8.0.19
      $ #For PXC-based deployment
      $ sudo percona-relase setup pdpxc-8.0.19

Make sure to run |percona-release| as root or via |sudo|. For the
sake of convenience, all commands that require elevated privileges start with
|sudo| in the following procedures.

Install |pdmysql|
================================================================================

Install the selected deployment of |pdmysql| using the commands of the package manager of your operating system.

.. important::

   Run all commands as root or via |sudo|.

Install |PS|-based deployment on Debian / Ubuntu
--------------------------------------------------------------------------------

1. Install |PS|:
   
   .. code-block:: bash
  
      $ sudo apt-get install percona-server-server

#. Install the components. Use the commands below to install the required components: 
   
   .. code-block:: bash
   
      $ #Install Percona XtraBackup
      $ sudo apt-get install percona-xtrabackup-80
      $ #Install Percona Toolkit
      $ sudo apt-get install percona-toolkit
      $ #Install Orchestrator
      $ sudo apt-get install percona-orchestrator percona-orchestrator-cli percona-orchestrator-client
      $ #Install MySQL Shell
      $ sudo apt-get install percona-mysql-shell
      $ #Install ProxySQL
      $ sudo apt-get install proxysql2
      $ #Install MySQL Router
      $ sudo apt-get install percona-mysql-router  
      
.. seealso::

   Percona Documentation:
       * `Installing Percona Server for MySQL on Debian and Ubuntu <https://www.percona.com/doc/percona-server/8.0/installation/apt_repo.html>`_
       * `Installing Percona XtraBackup on Debian and Ubuntu <https://www.percona.com/doc/percona-xtrabackup/8.0/installation/apt_repo.html>`_
       * `Installing Percona Toolkit <https://www.percona.com/doc/percona-toolkit/2.2/installation.html>`_
 

Install |PS|-based deployment on |RHEL| / |centos| 
--------------------------------------------------------------------------------

.. admonition:: Platform Specific Notes

   On |centos| 7, install the epel-release package. It includes the dependencies required to install Orchestrator. Use the following command:

   .. code-block:: bash

      $ sudo yum -y install epel-release

1. Install |PS|:
   
   .. code-block:: bash
  
      $ sudo yum install percona-server-server

#. Install the components. Use the commands below to install the required components: 
   
   .. code-block:: bash
   
      $ #Install Orchestrator
      $ sudo yum install percona-orchestrator percona-orchestrator-cli percona-orchestrator-client
      $ #Install Percona XtraBackup
      $ sudo yum install percona-xtrabackup-80
      $ #Install Percona Toolkit
      $ sudo yum install percona-toolkit
      $ #Install MySQL Shell
      $ sudo yum install percona-mysql-shell
      $ #Install ProxySQL
      $ sudo yum install proxysql2
      $ #Install MySQL Router
      $ sudo yum install percona-mysql-router  

.. rubric:: Running Percona Distribution for MySQL

|pdmysql| is not started automatically on |RHEL| and |centos| after the installation is complete. Start it manually using the following command:

.. code-block:: bash
   
   $ sudo systemctl start mysql

Confirm that the service is running:
   
.. code-block:: bash
      
   $ sudo systemctl status mysql

Stop the service:
   
.. code-block:: bash
      
   $ sudo systemctl stop mysql  

.. seealso::

   Percona Documentation:
       * `Installing Percona Server for MySQL on Red Hat Enterprise Linux and CentOS <https://www.percona.com/doc/percona-server/8.0/installation/yum_repo.html>`_
       * `Installing Percona XtraBackup on Red Hat Enterprise Linux and CentOS <https://www.percona.com/doc/percona-xtrabackup/8.0/installation/yum_repo.html>`_
       * `Installing Percona Toolkit <https://www.percona.com/doc/percona-toolkit/2.2/installation.html>`_

Install |PXC|-based deployment on Debian / Ubuntu
--------------------------------------------------------------------------------

1. Install |PXC|:
   
   .. code-block:: bash
   
      $ sudo apt-get install percona-xtradb-cluster


#. Install HAProxy:  

   .. code-block:: bash
   
      $ sudo apt-get install percona-haproxy

#. Install the components. Use the commands below to install the required components:
   
   .. code-block:: bash
   
      $ #Install Percona XtraBackup 
      $ sudo apt-get install percona-xtrabackup-80
      $ #Install Percona Toolkit
      $ sudo apt-get install percona-toolkit
    
.. seealso::

   Percona Documentation:
       * `Installing Percona XtraDB Cluster on Debian and Ubuntu <https://www.percona.com/doc/percona-xtradb-cluster/8.0/install/apt.html>`_
       * `Installing Percona XtraBackup on Debian and Ubuntu <https://www.percona.com/doc/percona-xtrabackup/8.0/installation/apt_repo.html>`_
       * `Installing Percona Toolkit <https://www.percona.com/doc/percona-toolkit/2.2/installation.html>`_
 
Install |PXC|-based deployment on |RHEL| / |centos|
--------------------------------------------------------------------------------

1. Install |PXC|:
   
   .. code-block:: bash
   
      $ sudo yum install percona-xtradb-cluster


#. Install HAProxy:  

   .. code-block:: bash
   
      $ sudo yum install percona-haproxy
      
#. Install the components. Use the commands below to install the required components:
   
   .. code-block:: bash
   
      $ #Install Percona XtraBackup 
      $ sudo yum install percona-xtrabackup-80
      $ #Install Percona Toolkit
      $ sudo yum install percona-toolkit
 
.. rubric:: Running Percona Distribution for MySQL

|pdmysql| is not started automatically on |RHEL| and |centos| after the installation is complete. Start it manually using the following command:

.. code-block:: bash
   
   $ sudo systemctl start mysql

Confirm that the service is running:
   
.. code-block:: bash
      
   $ sudo systemctl status mysql

Stop the service:
   
.. code-block:: bash
      
   $ sudo systemctl stop mysql

.. seealso::

   Percona Documentation:
       * `Installing Percona XtraDB Cluster on Red Hat Enterprise Linux and CentOS <https://www.percona.com/doc/percona-xtradb-cluster/8.0/install/yum.html>`_
       * `Installing Percona XtraBackup on Red Hat Enterprise Linux and CentOS <https://www.percona.com/doc/percona-xtrabackup/8.0/installation/yum_repo.html>`_
       * `Installing Percona Toolkit <https://www.percona.com/doc/percona-toolkit/2.2/installation.html>`_
 
.. include:: .res/replace.txt