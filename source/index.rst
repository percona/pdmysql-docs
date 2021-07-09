.. _index:

==========================================================
Percona Distribution for MySQL |version| Documentation
==========================================================

|pdmysql| is a  single solution with the best and most critical enterprise components from the |mysql| open source community, designed and tested to work together. By leveraging the distribution, you get the exact combination of software and tools required to successfully deploy, run and operate your MySQL databases to meet your application and business needs.

.. _pdmysql.components:

Components
===========

|pdmysql| consists of the following **components**:

* `Percona Server for MySQL <https://www.percona.com/doc/percona-server/8.0/index.html>`_ is a drop-in replacement for |mysql-ce| with the enterprise-grade features embedded by Percona.
* `Percona XtraDB Cluster <https://www.percona.com/doc/percona-xtradb-cluster/8.0/index.html>`_ is the high-available clustering solution for MySQL. It is based on |PS| and uses |PXB| for node provisioning.
* `Percona XtraBackup <https://www.percona.com/doc/percona-xtrabackup/8.0/index.html>`_ is an open-source hot backup utility for MySQL-based servers that doesn't lock your database during the backup.
* `Orchestrator <https://github.com/openark/orchestrator>`_ is the replication topology manager for |PS|.
* `HAProxy <http://www.haproxy.org/>`_ is the default high-availability and load-balancing solution for |PXC|.
* `ProxySQL <https://proxysql.com/>`_ is a high performance, high-availability, protocol-aware proxy for |mysql|.
* `Percona Toolkit <https://www.percona.com/doc/percona-toolkit/3.0/index.html>`_ is the set of scripts to simplify and optimize database operation.
* `MySQL Shell <https://dev.mysql.com/doc/mysql-shell/8.0/en/>`_ is an advanced client and code editor for MySQL Server.
* `MySQL Router <https://dev.mysql.com/doc/mysql-router/8.0/en/>`_ is lightweight middleware that provides transparent routing between your application and back-end MySQL servers.
  
|pdmysql| provides two deployment variants: one is |PS|-based and another one is |PXC|-based. Each deployment is available via its own repository and includes the base server (|PS| or |PXC|) and components.  The table below lists what components are available  with each server:




.. list-table:: 
   :widths: 30 20 20
   :header-rows: 1
 
   * - Components
     - |PS|
     - |PXC|
   * - Orchestrator
     - YES
     - NO
   * - HAProxy
     - NO    
     - YES
   * - ProxySQL
     - YES
     - YES
   * - |PXB|
     - YES
     - YES
   * - Percona Toolkit
     - YES
     - YES
   * - MySQL Shell
     - YES
     - NO
   * - MySQL Router
     - YES
     - NO
 

What deployment variant to choose?
================================================================================

The **Percona Server-based deployment variant** with `asynchronous replication <https://dev.mysql.com/doc/refman/8.0/en/replication.html>`_ utilizes the primary / secondary replication model. It enables you to create geographically distributed infrastructures with the support for disaster recovery. However, this deployment variant does not guarantee data consistency on all nodes at the given moment and provides high availability  of up to 4 nines. 

The **Percona Server-based deployment variant** with `Group Replication <https://dev.mysql.com/doc/refman/8.0/en/group-replication.html>`_ enables you to create fault-tolerant systems with redundancy by replicating the system state to a set of servers. |PS|-based deployment with Group Replication  offers a high grade of high availability (4-5 nines) and almost instant fail over when associated with a proxy.  

The **Percona XtraDB Cluster-based deployment variant** guarantees data consistency on all nodes and zero data loss. The Percona XtraDB Cluster-based deployment provides a high grade of high availability  (4-5 nines) and almost instant failover.

.. seealso::

   |percona| Blog Posts:
       - `MySQL High Availability On-Premises: A Geographically Distributed Scenario <https://www.percona.com/blog/2018/11/15/mysql-high-availability-on-premises-a-geographically-distributed-scenario/>`_
       - `Choosing MySQL High Availability Solutions <https://www.percona.com/blog/2016/06/07/choosing-mysql-high-availability-solutions/>`_

========================
Installation and Upgrade
========================

.. toctree::
   :maxdepth: 1
   :glob:

   installing
   minor-upgrade

========================
Architecture solutions
========================

.. toctree::
   :maxdepth: 1

   pdps-group-replication

========================
How to
========================

.. toctree::
   :maxdepth: 1
   :glob:

   deploy-pdps-group-replication
   uninstalling

========================
Release Notes
========================

.. toctree::
   :maxdepth: 2
   :glob:

   release-notes

========================
Reference
========================

.. toctree::
   :maxdepth: 2
   

   glossary

.. include:: .res/replace.txt

