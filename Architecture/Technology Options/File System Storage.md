---
tags: 
author:
  - jacgit18
Status: Refinement
Started: 
EditDate: 
Relates:
---
-   A file is an unstructured collection of records. Typically file systems support two basic formats. These are as follows: 
    

-   Block Storage: Organize data in blocks on disk. The blocks are then divided into sectors and tracks. Current day personal computers (i.e., laptops and desktops) store data using Block Storage. 
    

-   Object Storage: Organize data into containers of flexible sizes, referred to as objects. Modern-day cloud systems use Object Storage for storing their data. E.g., Amazon S3. They are designed to be massively scalable, highly performant, and inexpensive. 
    

-   The characteristics of a distributed file system (DFS) are as follows: 
    
    -   Performance: A DFS should provide high throughput and low latency of access. The performance should be similar to what a local file system can provide. 
        
    -   Availability: Distributed file systems are built across a network. Therefore, they can have several possibilities of failure. The data should remain accessible in case of partial node failures. 
        
    -   Scalability: A DFS should scale horizontally and support the storage of petabytes of data. The system should scale as more nodes are added to the DFS. The client should not experience any disruption as more nodes are added to the system. 
        
    -   Reliability: A DFS should be highly reliable and ensure that the probability of data loss is minimized. Typically, a DFS would create backup copies of the data to prevent it from being lost permanently. 
        
    -   Ease Of Use: A DFS should provide a simple and easy-to-use interface for the client to use. Some of the common operations that clients use, such as reading, writing, copying, etc., should be easy to perform. 
        
    -   Data Integrity: A DFS should ensure that the data remains consistent and shouldn’t be lost in case multiple users access it. Typically DFS should provide atomicity and consistency of operations in some form or the other. 
        
    -   Heterogeneity: A DFS should support the storage of heterogeneous data (structured, unstructured, files, records, etc.). Different types of clients should be able to access the file system and store data on it. 
        

Atomicity – The property of a transaction that guarantees that either all or none of the changes made by the transaction are written to the database.