.. _upgrade-minor.pdmysql:

***************************************************************
Upgrading |pdmysql|                                            
***************************************************************

Minor releases include bug fixes and feature enhancements. We recommend to have |pdmysql| updated to the latest version. 

Though minor releases don't change the behavior, even a minor upgrade is a risky process. We recommend to back up your data before upgrading.

As with installing |pdmysql|, the recommended way to upgrade it is from |percona| repositories. 

Enable |percona| repository
================================================================================

|percona| repositories are enabled using the |percona-release| utility. Install |percona-release| if you haven't done it already. Otherwise, update it to the latest version. Please refer to `Percona repositories documentation <https://www.percona.com/doc/percona-repo-config/percona-release.html>`_ for installation and update instructions. 

The Major Release repository automatically includes new version packages of |pdmysql|. If you installed |pdmysql| from a Minor Release repository, enable the new version repository. For more information about |pdmysql| repositories, refer to :ref:`Repository overview <repo-overview>`.

Upgrading |PS|-based deployment of |pdmysql|
============================================

.. include:: .res/run-commands-as-root.txt

The upgrade steps are:

1. Stop ``mysql`` service: :bash:`sudo systemctl mysql stop`
2. Install new version packages. Please refer to :ref:`installation` for installation instructions relevant to your operating system.
3. Restart ``mysql`` service: :bash:`sudo systemctl mysql start`

Upgrading |PXC|-based deployment of |pdmysql|
========================================================================

.. include:: .res/run-commands-as-root.txt

To upgrade |PXC|, complete these steps sequentially on all nodes:

1. Make sure that all |PXC| nodes are in sync.
#. Stop ``mysql`` service: :bash:`sudo systemctl mysql stop`
#. Install new version packages. Please refer to :ref:`installation` for installation instructions relevant to your operating system.
#. Back up the :file:`grastate.dat` file
#. Start ``mysql`` service: :bash:`sudo systemctl mysql start`

.. seealso::

   `Upgrading Percona XtraDB Cluster <https://www.percona.com/doc/percona-xtradb-cluster/LATEST/howtos/upgrade_guide.html#minor-upgrade>`_

To upgrade the components, refer to :ref:`installation` for installation instructions relevant to your operating system. 


.. include:: .res/replace.txt