# Database - Replication and Sharding

A 2 primary methods, that makes the DB to withstand the performance bottlenecks.

## Database Replication:

A process of replicating the db into its replicas (a copy of DB with its own server). The primary advantage of having the replications is to ensure the DB has **high availability** (as it can give the safety net if any db goes down) and **scales read capacity** (since each replicas can handle heavy read on its own). <br>

We can make this by following methods

### Leader-Follower Replication:
As name suggest, there will be one leader (primary / master DB) and follower (secondary / slave) replicas. So here

- All write will be handled by Primary DB
- All reads will be evently distributed accross the replicas

### Leader-Leader Replication

Here there are no secodnary DB's, only primary... all the replicas as Primary - every individual primary will handle both read/write. <br>

Only negative impact here was since every replica can handle both read & write, 
