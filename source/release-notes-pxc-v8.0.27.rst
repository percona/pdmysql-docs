.. _pdpxc.release_notes_8.0.27:

********************************************************************************
|pdmysql| 8.0.27 using |PXC|
********************************************************************************

:Date: April 11, 2022
:Installation: :ref:`installation`

|pdmysql| is a single solution with the best and most critical enterprise components from the |mysql| open source community, designed and tested to work together. 

|pdmysql| provides two deployment variants: one is based on |PS| and another one is based on |PXC|. 

This release of |pdmysql| is focused on the |PXC|-based deployment variant. It is based on `Percona XtraDB Cluster 8.0.27-17.1 <https://www.percona.com/doc/percona-xtradb-cluster/8.0/release-notes/Percona-XtraDB-Cluster-8.0.27-17.1.html>`_ 

Release Highlights
==================

The following lists a number of the bug fixes for *MySQL* 8.0.27, provided by Oracle, and included in Percona Server for MySQL:

* The ``default_authentication_plugin`` is deprecated. Support for this plugin may be removed in future versions. Use the ``authentication_policy`` variable.
* The ``binary`` operator is deprecated. Support for this operator may be removed in future versions. Use ``CAST(... AS BINARY)``.
* Fix for when a parent table initiates a cascading ``SET NULL`` operation on the child table, the virtual column can be set to NULL instead of the value derived from the parent table.

Find the full list of bug fixes and changes in the `MySQL 8.0.27 Release Notes <https://dev.mysql.com/doc/relnotes/mysql/8.0/en/news-8-0-27.html>`__.

The following is the list of components supplied with the |PXC|-based deployment variant of |pdmysql|:

.. list-table::
   :widths: auto
   :header-rows: 1

   * - Component
     - Version
     - Description
   * - |PXB|
     - 8.0.27
     - An open-source hot backup utility for MySQL-based servers that doesn’t lock your database during the backup.
   * - HAProxy
     - 2.4.15
     - A high-availability and load-balancing solution for Percona XtraDB Cluster. This is a default proxy.
   * - ProxySQL
     - 2.3.2
     - A high performance, high-availability, protocol-aware proxy for MySQL.
   * - Percona Toolkit
     - 3.3.1
     - The set of scripts to simplify and optimize database operation.



.. include:: .res/replace.txt