# Downgrade Percona Distribution for MySQL

!!! important

    This release does not include the Percona Toolkit component. We will add it once a Percona Toolkit version compatible with MySQL 8.4 becomes available.
    
    ProxySQL contains counters that have not been updated to use the new terminology. Unexpected results may occur. In an 8.4.x environment, the binlog reader errors out during initialization due to the use of old terminology, such as the SHOW MASTER STATUS command.

You have the following downgrade options:

1. Within Same LTS Version (Example: 8.4.5 to 8.4.3):

    * Methods Available:
    
      * In-place downgrade
      
      * Logical dump and restore
      
    * MySQL Clone
    
    * Replication-based downgrade

2. From LTS to Previous LTS (Example: 8.4.x to 8.0.y):

    * Methods Available:
    
      * Logical dump and restore
      
      * Replication-based downgrade
      
    * Important: Only works for rollback if you haven't used new features

3. From LTS to Innovation Release (Example: 8.4.x to 8.3.0):

    * Methods Available:
    
      * Logical dump and restore
      
      * Replication-based downgrade
      
    * Important: Only works for rollback if you haven't used new features

Key Points:

* You cannot downgrade to version 5.7 or earlier

* You cannot downgrade if you've used new version features

* Logical dump and restore works for most downgrade paths

* In-place downgrade only works within same LTS series