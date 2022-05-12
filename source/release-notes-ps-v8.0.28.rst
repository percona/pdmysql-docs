.. _pdps.release_notes_8.0.28:

********************************************************************************
|pdmysql| 8.0.28 using Percona Server for MySQL (2022-05-12)
********************************************************************************

:Date: May 12, 2022
:Installation: :ref:`installation`

|pdmysql| is a single solution with the best and most critical enterprise components from the |mysql| open-source community, designed and tested to work together. 

|pdmysql| provides two deployment variants: one is based on |PS| and another one is based on |PXC|. 

This release of |pdmysql| is focused on the |PS|-based deployment variant. It is based on `Percona Server for MySQL 8.0.28-19 <https://www.percona.com/doc/percona-server/8.0/release-notes/Percona-Server-8.0.28-19.html>`_.

Release Highlights
=================================================

The following lists a number of the bug fixes for *MySQL* 8.0.28, provided by Oracle, and included in Percona Server for MySQL and |pdmysql|:

* The ``ASCII`` shortcut for ``CHARACTER SET latin1`` and ``UNICODE`` shortcut for ``CHARACTER SET ucs2`` are deprecated and raise a warning to use ``CHARACTER SET`` instead. The shortcuts will be removed in a future version.
* A stored function and a loadable function with the same name can share the same namespace. Add the schema name when invoking a stored function in the shared namespace. The server generates a warning when function names collide.
* InnoDB supports ``ALTER TABLE ... RENAME COLUMN`` operations when using ``ALGORITHM=INSTANT``. 
* The limit for ``innodb_open_files`` now includes temporary tablespace files. The temporary tablespace files were not counted in the ``innodb_open_files`` in previous versions.

Find the full list of bug fixes and changes in the `MySQL 8.0.28 Release Notes <https://dev.mysql.com/doc/relnotes/mysql/8.0/en/news-8-0-28.html>`__.

---------------------------------------------

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
     - 8.0.28-20.0
     - An open-source hot backup utility for MySQL-based servers
   * - Percona Toolkit
     - 3.3.1
     - The set of scripts to simplify and optimize database operation
   * - MySQL Shell
     - 8.0.28
     - An advanced client and code editor for MySQL Server
   * - MySQL Router
     - 8.0.28
     - Lightweight middleware that provides transparent routing between your application and back-end MySQL servers


.. include:: .res/replace.txt