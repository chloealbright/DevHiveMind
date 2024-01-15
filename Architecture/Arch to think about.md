---
tags: 
author:
  - jacgit18
Status: Refinement
Started: 
EditDate: 
Relates:
---
The next thing you implement is database replication which addresses the problem with fail over and redundancy 

Databases have a Master slave relationships where the master has the original data and the slave have the copy 

The master supports the write operation and the slave that's a copy of data and only supports read operation 

All the commands to modify the data are sent to the master most applications have a higher ratio of retail rights so did tend to have a lot of more slave databases then master 

The advantage of database replication is better performance because all the writes and updates happen in the master and the reads are distributed to the slave meaning this model is very good because it allows queries to be processed in parallel. 

Battery replication is also very reliable and has high availability which makes it so that if you have a website you can have the website running if a server goes offline because of the data is stored on another server 

•A user gets the IP address of the load balancer from DNS. 

•A user connects the load balancer with this IP address. 

•The HTTP request is routed to either Server 1 or Server 2. 

•A web server reads user data from a slave database. 

•A web server routes any data-modifying operations to the master database.  

CRUD(Create Read Update Delete) 

This includes write, update, and delete operations Improving load response time which can be done by adding a cache layer and shifting static content by using a CDN Network 






