.. _pdpxc.release_notes_8.0.23:

********************************************************************************
|pdmysql| 8.0.23 using |PXC| (2021-06-09)
********************************************************************************

:Date: June 09, 2021
:Installation: :ref:`installation`

|pdmysql| is a single solution with the best and most critical enterprise components from the |mysql| open source community, designed and tested to work together. 

|pdmysql| provides two deployment variants: one is based on |PS| and another one is based on |PXC|. 

This release of |pdmysql| is focused on the |PXC|-based deployment variant. It is based on `Percona XtraDB Cluster 8.0.23-14.1 <https://www.percona.com/doc/percona-xtradb-cluster/8.0/release-notes/Percona-XtraDB-Cluster-8.0.23-14.1.html>`_ and includes the following components:   

.. list-table::
   :widths: auto
   :header-rows: 1

   * - Component
     - Version
     - Description
   * - |PXB|
     - 8.0.23
     - An open-source hot backup utility for MySQL-based servers that doesn’t lock your database during the backup.
   * - HAProxy
     - 2.3.10
     - A high-availability and load-balancing solution for Percona XtraDB Cluster. This is a default proxy.
   * - ProxySQL
     - 2.0.18
     - A high performance, high-availability, protocol-aware proxy for MySQL.
   * - Percona Toolkit
     - 3.3.1
     - The set of scripts to simplify and optimize database operation.



.. include:: .res/replace.txt