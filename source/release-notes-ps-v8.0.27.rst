.. _pdps.release_notes_8.0.27:

********************************************************************************
|pdmysql| 8.0.27 using Percona Server for MySQL
********************************************************************************

:Date: March 2, 2022
:Installation: :ref:`installation`

|pdmysql| is a single solution with the best and most critical enterprise components from the |mysql| open-source community, designed and tested to work together. 

|pdmysql| provides two deployment variants: one is based on |PS| and another one is based on |PXC|. 

This release of |pdmysql| is focused on the |PS|-based deployment variant. It is based on `Percona Server for MySQL 8.0.27-18 <https://www.percona.com/doc/percona-server/8.0/release-notes/Percona-Server-8.0.27-18.html>`_.

Release Highlights
==================

* CentOS 6 is no longer supported.

The following list are some of the bug fixes for *MySQL* 8.0.27, provided by Oracle, and included in Percona Server for MySQL and |pdmysql|:

* The ``default_authentication_plugin`` is deprecated. Support for this plugin may be removed in future versions. Use the ``authentication_policy`` variable.
* The ``binary`` operator is deprecated. Support for this operator may be removed in future versions. Use ``CAST(... AS BINARY)``.
* Fix for when a parent table initiates a cascading ``SET NULL`` operation on the child table, the virtual column can be set to NULL instead of the value derived from the parent table.

Known issues
============

The CentOS 7 packages do not support TLS v1.3.

The following is the list of components supplied with |PS|-based deployment variant of |pdmysql|:  

.. list-table::
   :widths: auto
   :header-rows: 1

   * - Component
     - Version
     - Description
   * - Orchestrator
     - 3.2.6
     - The replication topology manager for Percona Server for MySQL 
   * - ProxySQL
     - 2.3.2
     - A high performance, high-availability, protocol-aware proxy for MySQL
   * - Percona XtraBackup
     - 8.0.27-17.0
     - An open-source hot backup utility for MySQL-based servers
   * - Percona Toolkit
     - 3.3.1
     - The set of scripts to simplify and optimize database operation
   * - MySQL Shell
     - 8.0.27
     - An advanced client and code editor for MySQL Server
   * - MySQL Router
     - 8.0.27
     - Lightweight middleware that provides transparent routing between your application and back-end MySQL servers


.. include:: .res/replace.txt