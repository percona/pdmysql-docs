.. _pdpxc.release_notes_8.0.25:

********************************************************************************
|pdmysql| 8.0.25 using |PXC|
********************************************************************************

:Date: November 22, 2021
:Installation: :ref:`installation`

|pdmysql| is a single solution with the best and most critical enterprise components from the |mysql| open source community, designed and tested to work together. 

|pdmysql| provides two deployment variants: one is based on |PS| and another one is based on |PXC|. 

This release of |pdmysql| is focused on the |PXC|-based deployment variant. It is based on `Percona XtraDB Cluster 8.0.25-15.1 <https://www.percona.com/doc/percona-xtradb-cluster/8.0/release-notes/Percona-XtraDB-Cluster-8.0.25-15.1.html>`_ 

Release Highlights
==================

A `Non-Blocking Operation mode <https://www.percona.com/doc/percona-xtradb-cluster/8.0/features/nbo.html>`_ for the Online Schema Upgrades in Percona XtraDB Cluster. This mode is similar to the Total Order Isolation (TOI) mode, whereas the data definition language (DDL) statement (e.g., ALTER) is executed on all nodes in sync. The difference is that in the NBO mode, the DDL statement acquires a metadata lock that locks the table or schema at a late stage of the operation, which is a more efficient locking strategy. 

Note that the NBO mode is a tech preview feature. Therefore, we recommend using it in testing environments only. 

  
The following is the list of the notable fixes for MySQL 8.0.25, provided by Oracle, and included in |PXC| and |pdmysql|:

* :mysqlbug:`103980`: Fixes the allocation of too much memory when dropping a database with many partitioned tables.
* :mysqlbug:`103743`: Fixes a slow startup when the tables are encrypted.

The following is the list of components supplied with the |PXC|-based deployment variant of |pdmysql|:

.. list-table::
   :widths: auto
   :header-rows: 1

   * - Component
     - Version
     - Description
   * - |PXB|
     - 8.0.25
     - An open-source hot backup utility for MySQL-based servers that doesn’t lock your database during the backup.
   * - HAProxy
     - 2.3.14
     - A high-availability and load-balancing solution for Percona XtraDB Cluster. This is a default proxy.
   * - ProxySQL
     - 2.0.18
     - A high performance, high-availability, protocol-aware proxy for MySQL.
   * - Percona Toolkit
     - 3.3.1
     - The set of scripts to simplify and optimize database operation.



.. include:: .res/replace.txt