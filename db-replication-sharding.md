# Database - Replication and Sharding

A 2 primary methods, that makes the DB to withstand the performance bottlenecks.

## Database Replication:

A process of replicating the db into its replicas (a copy of DB with its own server). The primary advantage of having the replications is to ensure the DB has **high availability** (as it can give the safety net if any db goes down) and **scales read capacity** (since each replicas can handle heavy read on its own). <br>

We can make this by following methods,

### Leader-Follower Replication:
As name suggest, there will be one leader (primary / master DB) and follower (secondary / slave) replicas. So here

- All write will be handled by Primary DB
- All reads will be evently distributed accross the replicas

### Leader-Leader Replication:

Here there are no secodnary DB's, only primary... all the replicas as Primary - every individual primary will handle both read/write. <br>

Only negative impact here was since every replica can handle both read & write, there might be lot more reduntant read / write data.

### Async and Sync:

Both above type of replications can be worked in async / sync way. By considering the example of leader-follower pattern

1. Async - The write will be done in background, so the write ie effectively fast and there is the way that we might get the stale data while reading.
2. Sync - This will write all the data to replicas, this gives the gurantee of the newly written data, but this can cause the write performance impact, since all the data need to be written in all replicas.
