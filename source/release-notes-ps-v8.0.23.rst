.. _pdps.release_notes_8.0.23:

********************************************************************************
|pdmysql| 8.0.23 using Percona Server for MySQL (2021-05-12)
********************************************************************************

:Date: May 12, 2021
:Installation: :ref:`installation`

|pdmysql| is a single solution with the best and most critical enterprise components from the |mysql| open source community, designed and tested to work together. 

|pdmysql| provides two deployment variants: one is based on |PS| and another one is based on |PXC|. 

This release of |pdmysql| is focused on the |PS|-based deployment variant. It  is based on `Percona Server for MySQL 8.0.23-14 <https://www.percona.com/doc/percona-server/8.0/release-notes/Percona-Server-8.0.23-14.html>`_ and includes the following components:  

.. list-table::
   :widths: auto
   :header-rows: 1

   * - Component
     - Version
     - Description
   * - Orchestrator
     - 3.2.4
     - The replication topology manager for Percona Server for MySQL 
   * - ProxySQL
     - 2.0.18
     - A high performance, high-availability, protocol-aware proxy for MySQL
   * - Percona XtraBackup
     - 8.0.23-16.0
     - An open-source hot backup utility for MySQL-based servers
   * - Percona Toolkit
     - 3.3.1
     - The set of scripts to simplify and optimize database operation
   * - MySQL Shell
     - 8.0.23
     - An advanced client and code editor for MySQL Server
   * - MySQL Router
     - 8.0.23
     - Lightweight middleware that provides transparent routing between your application and back-end MySQL servers


.. include:: .res/replace.txt