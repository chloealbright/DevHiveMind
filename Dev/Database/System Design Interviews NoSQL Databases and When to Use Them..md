

![](https://miro.medium.com/v2/resize:fit:630/0*M-fNRUpknwVUDuq2.png)

## What are NoSQL databases?

Typically, “NoSQL database” refers to any non-relational database. Whether it stands for “non SQL” or “not only SQL,” most agree that NoSQL databases store data in a format other than relational tables.

NoSQL databases are most popular because they allow users to store data with a flexible schema.

## Why should you use a NoSQL database?

NoSQL databases are high-performance, scalable, and flexible, which makes them great for mobile, web, and gaming applications.

-   **Scalability**: As opposed to scaling up by adding expensive and robust servers, NoSQL databases typically scale out by using distributed clusters of hardware. As a fully managed service, some cloud providers handle these operations behind the scenes.
-   **Flexibility**: NoSQL databases usually have flexible schemas that enable faster and more iterative development. NoSQL databases have a flexible data model that makes them ideal for semistructured and unstructured data.
-   **High-performance**: Compared to relational databases, NoSQL databases are optimized for specific data models and access patterns; this results in higher performance.

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

## Conclusion

➡ To select the most appropriate NoSQL database for your use case, you should understand the differences between various NoSQL databases. In this post, I’ve tried to list the most important use cases of each NoSQL database.

➡ Learn more on system design interview in “[**Grokking the System Design Interview**](https://designgurus.org/course/grokking-the-system-design-interview)**”** and **“**[**Grokking the Advanced System Design Interview**](https://designgurus.org/course/grokking-the-advanced-system-design-interview).”

➡ Follow me on [Linkedin](https://www.linkedin.com/in/arslanahmad/) for tips on system design and coding interviews.

Read more on System Design Interviews: