.. _upgrade-minor.pdmysql:

***************************************************************
Upgrading |pdmysql|                                            
***************************************************************

Minor releases include bug fixes and feature enhancements. We recommend to have |pdmysql| updated to the latest version. 

Though minor releases don't change the behavior, even a minor upgrade is a risky process. We recommend to back up your data before upgrading.

As with installing |pdmysql|, the recommended way to upgrade it is via |percona| repositories. 

Enable |percona| repository
================================================================================

|percona| repositories are enabled using the |percona-release| utility. Install |percona-release| if you haven't done it already. Otherwise, update it to the latest version. Please refer to `Percona repositories documentation <https://www.percona.com/doc/percona-repo-config/percona-release.html>`_ for installation or update instructions. 

The Major Release repository automatically includes new version packages of |pdmysql|. If you installed |pdmysql| from a Minor Release repository, enable the new version repository. For more information about |pdmysql| repositories, refer to :ref:`Repository overview <repo-overview>`.

Upgrading |PS|-based deployment of |pdmysql|
============================================

.. include:: .res/run-commands-as-root.txt

The upgrade steps are:

1. Stop ``mysql`` service: :bash:`sudo systemctl mysql stop`
2. Install new version packages. Please refer to :ref:`installation` for installation instructions relevant to your operating system.
3. Restart ``mysql`` service: :bash:`sudo systemctl mysql start`

.. include:: .res/replace.txt