# When should we use SQL vs NoSQL:

1. SQL - When we need **Strict Data Consistency**, **regid Schema** and **complex multi-table relationships**.
    - Follows ACID principles
    - When we need to rely on high data consistency flows like bank transfer, policy change flows etc, as it supports (Transaction queries)
2. NoSQL - When we need **Massive horizontal Sacaling**, **write throughputs** and **flexible schema**
    - Follows BASE (eventually consistent)
    - When we need heavy writes, with horizontal scalling

Polygot - a combination of 2 set of DBMS
