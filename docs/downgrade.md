# Downgrade Percona Distribution for MySQL

<!-- Clarify whether the following note is valid for 9.7-->

!!! important

    This release does not include the Percona Toolkit component. We will add it once a Percona Toolkit version compatible with MySQL {{vers}} becomes available.
    
    In {{vers}}.x environments, the ProxySQL binlog reader can fail to initialize because it uses legacy commands, such as SHOW MASTER STATUS. Some internal counters also use outdated terminology. To address most terminology issues, enable the [terminology_use_previous](https://dev.mysql.com/doc/refman/{{vers}}/en/replication-options-replica.html#sysvar_terminology_use_previous) system variable on the database server. This workaround addresses only terminology compatibility and may not fix all failures.

You have the following downgrade options:

1. Within Same LTS Version (Example: 9.7.3 to 9.7.1):

    * Methods Available:
    
      * In-place downgrade
      
      * Logical dump and restore
      
    * MySQL Clone
    
    * Replication-based downgrade

2. From LTS to Previous LTS (Example: 9.7.x to 8.4.y):

    * Methods Available:
    
      * Logical dump and restore
      
      * Replication-based downgrade
      
    * Important: Only works for rollback if you haven't used new features

Key Points:

* You cannot downgrade to version 5.7 or earlier

* You cannot downgrade if you've used new version features

* Logical dump and restore works for most downgrade paths

* In-place downgrade only works within same LTS series