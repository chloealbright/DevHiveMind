---
tags: 
author:
  - jacgit18
Status: Capture
Started: 
EditDate: 
Relates:
---
## CAP
The CAP Theorem, representing Consistency, Availability, and Partition Tolerance, asserts that in database systems, achieving all three elements simultaneously is not possible. These components are pivotal in shaping a database's performance characteristics, and the selection of an appropriate combination is crucial based on specific requirements. Here's a breakdown of these elements:

1. **Consistency:**
   - In the context of the CAP Theorem, consistency ensures uniformity of data throughout the system. This is especially critical in scenarios where precision, such as in banking or high-stakes transactions, is paramount.

2. **Availability:**
   - Availability concerns users' ability to read and write data, even when faced with network failures. It underscores uninterrupted access to the system, regardless of network issues.

3. **Partition Tolerance:**
   - Partition tolerance indicates the system's ability to function seamlessly, even if segments of the network are offline. It ensures the system remains operational despite potential disruptions.

The CAP Theorem aids in making informed decisions when selecting a database system, necessitating a careful consideration of trade-offs among these three factors. Relational databases, while providing consistency, often lack partition tolerance and high availability, leading to potential downtime during updates.


![[DB Popularity.png]]


NoSQL databases, a diverse category, offer varied trade-offs based on the specific type chosen. For example:

- **AP Systems (Partition Tolerance + Availability):** Examples include CouchDB, Cassandra, and DynamoDB. These prioritize partition tolerance and availability, accepting eventual consistency as data replicates across machines.

- **CA Systems (Consistency + Availability):** Examples include traditional relational databases like MySQL, PostgreSQL, and Oracle Database. Suited for scenarios where maintaining data consistency is critical, coupled with a high level of availability, commonly used in applications such as financial systems.

- **CP Systems (Partition Tolerance + Consistency):** Examples include MongoDB, Hbase, and Redis. These focus on partition tolerance and consistency, ensuring accuracy at the expense of immediate availability.

The term NoSQL encompasses various non-relational databases, with four main types: key-value, document, wide-column, and graph databases. The choice among these depends on specific needs:

- **Key-Value Stores:** Suited for fast retrieval of unstructured data, used in caching, user preference storage, and scenarios prioritizing simplicity (e.g., Redis, DynamoDB).


Key-value databases store data in pairs, each containing a unique id and a data value. These databases provide a flexible storage structure since values can store any amount of unstructured data.

## **Use cases**

Session management, user preferences, and product recommendations.

## **Examples**

Amazon DynamoDB, Azure Cosmos DB, Riak.

## ◆ In-memory key-value databases

The data is primarily stored in memory, unlike disk-based databases. By eliminating disk access, these databases enable minimal response times. Because all data is stored in main memory, in-memory databases risk losing data upon a process or server failure. In-memory databases can persist data on disks by storing each operation in a log or by taking snapshots.

## Examples

Redis, Memcached, Amazon Elasticache.



- **Document Databases:** Useful for flexible data storage, especially in scenarios requiring agile development and a variety of data types (e.g., MongoDB, CouchDB).

Document databases are structured similarly to key-value databases except that keys and values are stored in documents written in a markup language like JSON, XML, or YAML.

## Use cases

User profiles, product catalogs, and content management.

## Examples

MongoDB, Amazon DocumentDB, CouchDB.


- **Wide-Column Stores:** Ideal for scenarios with known queries and large data volumes, offering fast querying of specific data parts (e.g., Cassandra, HBase).


Wide column databases are based on tables but without a strict column format. Rows do not need a value in every column, and segments of rows and columns containing different data formats can be combined.

## Use cases

Telemetry, analytics data, messaging, and time-series data.

## Examples

Cassandra, Accumulo, Azure Table Storage, HBase.


- **Graph Databases:** Designed for illustrating multidimensional relationships, suitable for social networks, fraud detection, and recommendation engines (e.g., Neo4j, JanusGraph, Amazon Neptune, Cosmos DB through Azure Gremlin).



Unique databases



## ◆ Time series databases

These databases store data in time-ordered streams. Data is not sorted by value or id but by the time of collection, ingestion, or other timestamps included in the metadata.

## Use cases

Industrial telemetry, DevOps, and Internet of Things (IOT) applications.

## Examples

Graphite, Prometheus, Amazon Timestream.




## ◆ **Ledger databases**

Ledger databases are based on logs that record events related to data values. These databases store data changes that are used to verify the integrity of data.

## Use cases

Banking systems, registrations, supply chains, and systems of record.

## Examples

Amazon Quantum Ledger Database (QLDB).

