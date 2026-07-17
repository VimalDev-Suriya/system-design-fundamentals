# Database - Replication and Sharding

A 2 primary methods, that makes the DB to withstand the performance bottlenecks.

## Database Replication:

A process of replicating the db into its replicas (a copy of DB with its own server). The primary advantage of having the replications is to ensure the DB has **high availability** (as it can give the safety net if any db goes down) and **scales read capacity** (since each replicas can handle heavy read on its own) and **Fault Tolerance** <br>

We can make this by following methods,

### Leader-Follower Replication:
As name suggest, there will be one leader (primary / master DB) and follower (secondary / slave) replicas. So here

- All write will be handled by Primary DB
- All reads will be evently distributed accross the replicas

### Leader-Leader Replication:

Here there are no secodnary DB's, only primary... all the replicas act as Primary - every individual primary will handle both read/write. <br>

Only negative impact here was since every replica can handle both read & write, there might be lot more reduntant read / write data means any user can write the same data into differnt replicas. So we should be handling the conflicts and to increase the **write scalability**.

#### Conflict resolution Mechanism:
1. Timestamp based resolution - latest timestamp data will override the older data
2. Recent write wins
3. Custom - Application specific

### Async and Sync:

Both above type of replications can be worked in async / sync way. By considering the example of leader-follower pattern

1. Async - The write will be done in background, so the write ie effectively fast and there is the way that we might get the stale data while reading.
2. Sync - This will write all the data to replicas, this gives the gurantee of the newly written data, but this can cause the write performance impact, since all the data need to be written in all replicas.

## Sharding:

It provided the ability to distribute the data into multiple db. Unlike replication where we are replicating the individual server, here we are distributing the data accross the server. It helps us to increase the **Horizontal Scaling** and **write-throughputs**. <br>

We will be moving to shard, if the single server cannot able to perform the heavy writes (which required high CPU) and need horizontal scaling. <br> 

Consider the example of the e-commerce application, where customer data can be shard using the customers location. So its easy for the application to perfrom the geo-location based issues. These sharding will be performed by **shard key**. <br>

The process of sharding will differ entirely based on the DBMS we use,

1. SQL - by default it wont have any sharding functionality, but we can impletment by providing our own custom logic to it
2. NoSQL - provided built in Sharding mechanism

### Shard Keys:

1. Range based Shard Keys - Eg - based on the user-id's, first 1k user in one set of shard, and rest like to others
2. Hash based keys - using hash function to store the data into corresponding sharding
