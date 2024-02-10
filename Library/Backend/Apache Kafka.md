---
tags:
  - systemDesign
  - eventDriven
  - platform
  - distributedSystem
  - CodebaseDecision
author:
  - jacgit18
Comments: This documentation discusses Apache Kafka.
Status: Refinement
Started: 2023-11-06
EditDate: 2024-02-03
Relates:
---
![[Apache Arch.gif]]

Apache Kafka is often categorized as a distributed streaming platform or event streaming platform rather than a traditional message queue or message broker. While it shares some similarities with message queues, Kafka is designed for high-throughput, [[Fault tolerance |fault-tolerant]], and distributed event streaming. It allows you to publish and subscribe to streams of records, store those records in a fault-tolerant manner, and process them in real-time or batch.
![[Kafka Uses.gif]]



![[Kafka Performance.jpeg]]