# Glossary

## ACID
    
Set of properties that guarantee database transactions are processed reliably. Stands for [`Atomicity`](#atomicity), [`Consistency`](#consistency), [`Isolation`](#isolation), [`Durability`](#durability).

## Asynchronous replication

Asynchronous replication is a technique where data is first written to the primary node. After the primary acknowledges the write, the data is written to secondary nodes.

## Atomicity

Atomicity means that database operations are applied following an "all or nothing" rule. A transaction is either fully applied or not at all.

## Consistency

In the context of backup and restore, consistency means that the data restored will be consistent in a given point in time. Partial or incomplete writes to disk of atomic operations (for example, to table and index data structures separately) won't be served to the client after the restore. The same applies to multi-document transactions, that started but didn't complete by the time the backup was finished.
   
## Disaster recovery

Disaster recovery are means to regain access and functionality of a database infrastructure after unplanned events that caused its failure.

## Downtime
   
Downtime is the period when a database infrastructure is unavailable due to expected (maintenance) or unexpected (outage, lost connectivity, hardware failure, etc.) reasons.

## Durability

Once a transaction is committed, it will remain so.

## Failover

Failover is switching automatically and seamlessly to a reliable backup system.

## General availability (GA)

A finalized version of the product which is made available to the general public. It is the final stage in the software release cycle.

## GTID

A global transaction identifier (GTID) is a unique identifier created and associated with each transaction committed on the server of the source. This identifier is unique across all servers in a given replication topology.

## High availability
    
A high availability is the ability of a system to operate continuously without failure for a long time.

## Isolation
    
The Isolation requirement means that no transaction can interfere with another.

## Loosely-coupled cluster

A loosely-coupled cluster is the deployment where cluster nodes are independent in processing / applying transactions. Data state may not always be consistent in time on all nodes; however, a single node state does not affect the cluster. Loosely-coupled clusters use [asynchronous replication](#asyncronous-replication.md) and can be geographically distributed and/or serve as the [disaster recovery](#disaster-recovery) site.

## Multi-source replication 

A multi-source replication topology requires at least one replica synchronized with at least two sources. The transactions can be received in parallel because the replica creates a separate replication channel for each source.

Multi-source replication allows a single server to back up or consolidate data from multiple servers. This type of replication also lets you merge table shards.

## Nines of availability
    
Nines of availability refer to system availability as a percentage of total system time.

## Semi-synchronous replication

A semi-synchronous replication is a technique where the primary node wait for at least one of the secondaries to acknowledge the transaction before processing further transactions.

## Synchronous replication

A synchronous replication is a technique when data is written to the primary and secondary nodes simultaneously. Thus, both primary and secondaries are in sync and failover from the primary to one of the secondaries is possible any time.

## Tech preview 

A tech preview item can be a feature, a variable, or a value within a variable. The term designates that the item is not yet ready for production use and is not included in support by SLA. A tech preview item is included in a release so that users can provide feedback. The item is either updated and released as [general availability(GA)](#general-availability-ga) or removed if not useful. The item’s functionality can change from tech preview to GA.

## Tightly-coupled cluster

A tightly-coupled cluster is the deployment in which transactions and information is synchronously distributed, consistent and available on all cluster nodes at any time.

## Uptime

Uptime is the time when the system is continuously available.