.. _pdps.release_notes_8.0.26:

********************************************************************************
|pdmysql| 8.0.26 using Percona Server for MySQL (2021-10-20)
********************************************************************************

:Date: October 20, 2021
:Installation: :ref:`installation`

|pdmysql| is a single solution with the best and most critical enterprise components from the |mysql| open-source community, designed and tested to work together. 

|pdmysql| provides two deployment variants: one is based on |PS| and another one is based on |PXC|. 

This release of |pdmysql| is focused on the |PS|-based deployment variant. It is based on `Percona Server for MySQL 8.0.26-16 <https://www.percona.com/doc/percona-server/8.0/release-notes/Percona-Server-8.0.26-16.html>`_.

Release Highlights
==================

The TokuDB Storage Engine has been declared deprecated starting with |PS| 8.0.26-16. The plugins are available in the binary builds and packages but are disabled. New options have been added to enable the plugins if they are needed to migrate the data to another storage engine. Read more in the `TokuDB documentation <https://www.percona.com/doc/percona-server/8.0/tokudb/tokudb_intro.html>`_.

The following is the list of bug fixes for MySQL 8.0.26, provided by Oracle, and included in Percona Server for MySQL and |pdmysql|:

* :mysqlbug:`104575`: In the PERFORMANCE_SCHEMA.Threads table, the ``srv_purge_thread`` and ``srv_worker_thread`` values are duplicated.
* :mysqlbug:`104387`: When using REGEX comparison, a CHARACTER_SET_MISMATCH error is thrown.
* :mysqlbug:`104576`: Accessing the second index in a partition table with many columns can create a high CPU load.

The following is the list of components supplied with |PS|-based deployment variant of |pdmysql|:  

.. list-table::
   :widths: auto
   :header-rows: 1

   * - Component
     - Version
     - Description
   * - Orchestrator
     - 3.2.5
     - The replication topology manager for Percona Server for MySQL 
   * - ProxySQL
     - 2.2.0
     - A high performance, high-availability, protocol-aware proxy for MySQL
   * - Percona XtraBackup
     - 8.0.26-17.0
     - An open-source hot backup utility for MySQL-based servers
   * - Percona Toolkit
     - 3.3.1
     - The set of scripts to simplify and optimize database operation
   * - MySQL Shell
     - 8.0.26
     - An advanced client and code editor for MySQL Server
   * - MySQL Router
     - 8.0.26
     - Lightweight middleware that provides transparent routing between your application and back-end MySQL servers


.. include:: .res/replace.txt