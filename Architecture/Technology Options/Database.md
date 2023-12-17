---
tags: 
author:
  - jacgit18
Status: Refinement
Started: 
EditDate: 
Relates:
---
## Database and Search Server, third party Api 

-   A database is a structured system to put your data under a pre-specified format and constraints. Some of the requirements when a database is needed are as follows: 
    
    -   Scalability: Applications that have billions of rows or terabytes of data use DBMS. 
        
    -   Security: Applications that require a strict deposit of access to data in an organization use DBMS. 
        
    -   Consistency: Applications that require the data to remain consistent use DBMS. Some of how the data can become corrupt are as follows: 
        
        -   — Lack of consistency constraints 
            
        -   — Unsafe deletes 
            
        -   — Overwriting 
            
-   A typical DBMS provides ACID capabilities to ensure that the data remains consistent. 
    
-   Availability: Applications that require the data to remain available throughout the lifetime use DBMS. A typical DBMS provides replication of servers to ensure the availability of data. 
    
-   Data redundancy is a situation in a database in which copies of a given piece of data are housed in 2 different places. This redundancy can be achieved if data is held in multiple places in the same database, in multiple databases on the same computer, or in multiple databases across multiple computers, perhaps even using different database management server software. This redundancy can be leveraged for both data access and permanence. 
    

Sharding is a technique for partitioning data. A database shard is a horizontal (think rows, not columns) partition of data within a database, with each partition being referred to as a shard. These shards are then spread across computer nodes, in order to balance the load. Data may then be included in one or more of these shards.