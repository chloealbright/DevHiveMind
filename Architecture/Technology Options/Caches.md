---
tags:
  - servers
author:
  - jacgit18
Status: Refinement
Started: 
EditDate: 
Relates:
---
The main difference between unstructured data and structured data is that structured data is typically used for general stuff and it's very organized like user accounts and the information associated with that as for unstructured is typically did I like media audio, geo-location, and weather 

Besides that, you want the other servers for database application you would want a master that handles the crud(Create Read Update Delete) processes and the copies would handle the reading operation you'll probably have more slaves databases and proportion to master the reason we want this because it allows queries to be processed in parallel Which is good for performance 



A cache is temporary storage that is relatively smaller in size with faster access time. Caches are used to reduce latency and reduce the load on your servers and databases. There are several levels at which caches are implemented. These are as follows: 
    
-   Client Caching: Caches are located on the client-side like browser, file system, and servers acting as reverse-proxy. 
	
-   CDN Caching: CDN (Content Delivery Network) is also used as a cache for serving static content (e.g. HTML, CSS, JavaScript, Images, Videos, etc.). 
	
-   Web Server Caching: Webservers also implement local caches and can retrieve, and return information without contacting downstream servers. 
	
-   Database Caching: Databases by default include some level of caching so that they do not have to run queries repeatedly. This can boost the performance of databases when they are under a lot of load. 
	
-   Application Caching: In application caching, the cache is placed between the application and data stores. These caches usually store database query results and/or objects that the application uses. Typical application caches include Memcached, Redis, DynamoDB, etc. 
	
-   One of the challenges with caching is ensuring consistency of the data between the cache and the underlying data layer (i.e. server or database).




## Caching

Another skill that a backend developer **needs to have is using caching techniques**. Caching is the process of storing frequently used or recently accessed data in a fast and temporary storage location, such as memory or disk. It is useful for backend development because it improves the performance and efficiency of the backend code and data.

Caching involves various aspects such as:

- Cache types: There are different types of caches, such as application cache, database cache, web cache, etc. Application cache is the cache that is stored within the backend application itself, such as variables, arrays, objects, etc. Database cache is the cache that is stored within the database system itself, such as query results, indexes, etc. Web cache is the cache that is stored outside the backend application or database system, such as proxies, CDNs (Content Delivery Networks), browsers, etc.
- Cache strategies: There are different strategies for caching data, such as cache-aside, read-through, write-through, write-behind, etc. Cache-aside is the strategy where the backend application checks the cache first before querying the database. If the data is not in the cache, it fetches it from the database and stores it in the cache for future use. Read-through is the strategy where the backend application queries the cache first before querying the database. If the data is not in the cache, it fetches it from the database and updates the cache automatically. Write-through is the strategy where the backend application writes data to both the cache and the database simultaneously. Write-behind is the strategy where the backend application writes data to the cache first and then asynchronously writes it to the database later.
- Cache policies: There are different policies for managing cached data, such as LRU (Least Recently Used), LFU (Least Frequently Used), FIFO (First-In-First-Out), etc. LRU is the policy where the cached data that has not been accessed for the longest time is evicted first when the cache is full. LFU is the policy where the cached data that has been accessed for the least number of times is evicted first when the cache is full. FIFO is the policy where the cached data that has been stored for the longest time is evicted first when the cache is full.

A backend developer needs to use various caching tools and techniques to implement these aspects in their backend code and data. Some examples of caching tools and techniques are:

- Redis: Redis is an open source in-memory data structure store that can be used as a database, cache or message broker. It supports various data types such as strings, lists, sets, hashes, etc. It also provides features such as replication, transactions, pub/sub, etc.
- Memcached: Memcached is an open source distributed memory caching system that can be used to speed up dynamic web applications by caching data and objects in memory. It supports simple key-value pairs and provides features such as sharding, expiration, etc.
- Varnish: Varnish is an open source web application accelerator that can be used to cache HTTP requests and responses between the backend and the frontend or other components. It supports various protocols such as HTTP, HTTPS, WebSocket, etc. It also provides features such as load balancing, compression, caching policies, etc.