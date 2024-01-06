---
tags: 
author:
  - jacgit18
Status: Distilling
Started: 
EditDate: 
Relates:
---



These are the famous NoSQL database types.

## ◆ Key-value databases

Key-value databases store data in pairs, each containing a unique id and a data value. These databases provide a flexible storage structure since values can store any amount of unstructured data.

## **Use cases**

Session management, user preferences, and product recommendations.

## **Examples**

Amazon DynamoDB, Azure Cosmos DB, Riak.

## ◆ In-memory key-value databases

The data is primarily stored in memory, unlike disk-based databases. By eliminating disk access, these databases enable minimal response times. Because all data is stored in main memory, in-memory databases risk losing data upon a process or server failure. In-memory databases can persist data on disks by storing each operation in a log or by taking snapshots.

## Examples

Redis, Memcached, Amazon Elasticache.

## ◆ Document databases

Document databases are structured similarly to key-value databases except that keys and values are stored in documents written in a markup language like JSON, XML, or YAML.

## Use cases

User profiles, product catalogs, and content management.

## Examples

MongoDB, Amazon DocumentDB, CouchDB.

## ◆ Wide-column databases

Wide column databases are based on tables but without a strict column format. Rows do not need a value in every column, and segments of rows and columns containing different data formats can be combined.

## Use cases

Telemetry, analytics data, messaging, and time-series data.

## Examples

Cassandra, Accumulo, Azure Table Storage, HBase.

![](https://miro.medium.com/v2/resize:fit:700/0*qgNwV2MAB92RMp7F.png)




Types of NoSQL databases


## ◆ Graph databases

Graph databases map the relationships between data using nodes and edges. Nodes are the individual data values, and edges are the relationships between those values.

## Use cases

Social graphs, recommendation engines, and fraud detection.

## Examples

Neo4j, Amazon Neptune, Cosmos DB through Azure Gremlin.




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

