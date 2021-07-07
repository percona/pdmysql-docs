.. _glossary:

********
Glossary
********

.. glossary::
  
   ACID
    Set of properties that guarantee database transactions are
    processed reliably. Stands for :term:`Atomicity`,
    :term:`Consistency`, :term:`Isolation`, :term:`Durability`.
   
   Asynchronous replication
    Asynchronous replication is a technique where data is first written to the primary node. After the primary acknowledges the write, the data is written to secondary nodes.

   Atomicity
    Atomicity means that database operations are applied following a
    "all or nothing" rule. A transaction is either fully applied or not
    at all.

   Consistency
    Consistency means that each transaction that modifies the database
    takes it from one consistent state to another.

   Disaster recovery
    Disaster recovery are means to regain access and functionality of a database infrastructure after unplanned events that caused its failure. 

   Downtime
    Downtime is the period when a database infrastructure is unavailable due to expected (maintenance) or unexpected (outage, lost connectivity, hardware failure, etc.) reasons.

   Durability
    Once a transaction is committed, it will remain so.

   Failover
    Failover is switching automatically and seamlessly to a reliable backup system.

   High availability
    A high availability is the ability of a system to operate continuously without failure for a long time.

   Isolation
    The Isolation requirement means that no transaction can interfere
    with another.

   Loosely-coupled cluster
    A loosely-coupled cluster is the deployment where cluster nodes are independent in processing / applying transactions. Data state may not always be consistent in time on all nodes; however, a single node state does not affect the cluster. Loosely-coupled clusters use :term:`asynchronous replication` and can be geographically distributed and/or serve as the :term:`disaster recovery` site. 

   Nines of availability
    Nines of availability refer to system availability as a percentage of total system time.

   Semi-synchronous replication
    A semi-synchronous replication is a technique where the primary node wait for at least one of the secondaries to acknowledge the transaction before processing further transactions.

   Synchronous replication
    A synchronous replication is a technique when data is written to the primary and secondary nodes simultaneously. Thus, both primary and secondaries are in sync and failover from the primary to one of the secondaries is possible any time.

   Tightly-coupled cluster 
    A tightly-coupled cluster is the deployment in which transactions and information is synchronously distributed, consistent and available on all cluster nodes at any time.

   Uptime
    Uptime is the time when the system is continuously available.



