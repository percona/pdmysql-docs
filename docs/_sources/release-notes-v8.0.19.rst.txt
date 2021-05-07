.. _pdmysql.release_notes_8.0.18:

********************************************************************************
|pdmysql| |version|
********************************************************************************

:Date: June 22, 2020
:Installation: :ref:`installation`

|pdmysql| is a  single solution with the best and most critical enterprise components from the |mysql| open source community, designed and tested to work together. By leveraging the distribution, you get the exact combination of software and tools required to successfully deploy, run and operate your MySQL databases to meet your application and business needs.

|pdmysql| consists of the following components:

* `Percona Server for MySQL <https://www.percona.com/doc/percona-server/8.0/index.html>`_ is a drop-in replacement for |mysql-ce| with the enterprise-grade features embedded by Percona.
* `Percona XtraDB Cluster <https://www.percona.com/doc/percona-xtradb-cluster/8.0/index.html>`_ is the high-available clustering solution for MySQL. It is based on |PS| and uses |PXB| for node provisioning.
* `Percona XtraBackup <https://www.percona.com/doc/percona-xtrabackup/8.0/index.html>`_ is an open-source hot backup utility for MySQL-based servers that doesn't lock your database during the backup.
* `Orchestrator <https://github.com/openark/orchestrator>`_ is the replication topology manager for |PS|.
* `HAProxy <http://www.haproxy.org/>`_ is the default high-availability and load-balancing solution for |PXC|.
* `ProxySQL <https://proxysql.com/>`_ is a high performance, high-availability, protocol-aware proxy for |mysql|.
* `Percona Toolkit <https://www.percona.com/doc/percona-toolkit/3.0/index.html>`_ is the set of scripts to simplify and optimize database operation.
* `MySQL Shell <https://dev.mysql.com/doc/mysql-shell/8.0/en/>`_ is an advanced client and code editor for MySQL Server.
* `MySQL Router <https://dev.mysql.com/doc/mysql-router/8.0/en/>`_ is lightweight middleware that provides transparent routing between your application and back-end MySQL Servers.
  
|pdmysql| provides two deployment variants: one is |PS|-based and another one is |PXC|-based. This enables you to build MySQL ecosystem that meets your specific needs. Each variant is available via its own repository and includes the base server (|PS| or |PXC|) and compatible components.

This release of |pdmysql| is based on |PS| |version| and |PXC| |version|.

.. |version| replace:: 8.0.19
.. include:: .res/replace.txt