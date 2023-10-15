For databases ask if the data is structured(SQL very organize) or unstructured(use NoSQl media, audio geo, weather) and how much amount of data will you be storing if the data is unstructured and you need to store massive amounts of data then you know you'll need a NOSql 

When it Comes to vertical and horizontal scaling  

  it is very simple but vertical scaling has a hard limit it is impossible to add unlimited CPU and memory to the server and it lacks fail over and redundancy if one server goes down the website app goes down with it completely 

As for horizontal scaling it is more desirable when it comes to scaling application due to the limitations of vertical scaling 

When server usage you should try to implement a load balancer which evenly distributes incoming traffic among web servers that have been defined in the load balancer 

User connect to the public IP of a load balancer and the web servers communicate through private IP addresses within the network which is invisible to the internet 

Multiple server as if one server goes down you can reroute the traffic to another and combination with the pool of servers that have load balances to distribute the traffic 

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

A cache is a temporary storage area that stores the result of expensive responses or frequently accessed data in memory so that subsequent requests are served more quickly.  

every time a new web page loads, one or more database calls are executed to fetch data. The application performance is greatly affected by calling the database repeatedly.The cache can mitigate this problem. 

cache tier is a temporary data store layer, much faster than the database. The benefits of having a separate cache tier include better system performance, ability to reduce database workloads, and the ability to scale the cache tier independently.  

After receiving a request, a web server first checks if the cache has the available response. If it has, it sends data back to the client. If not, it queries the database, stores the response in cache, and sends it back to the client. This caching strategy is called a read-through cache. Other caching strategies are available depending on the data type, size, and access patterns. 

Consider using cache when data is read frequently but modified infrequently. Since cached data is stored in volatile memory, a cache server is not ideal for persisting data. For instance, if a cache server restarts, all the data in memory is lost. Thus, important data should be saved in persistent data stores. 

Expiration policy. It is a good practice to implement an expiration policy. Once cached data is expired, it is removed from the cache. When there is no expiration policy, cached data will be stored in the memory permanently. It is advisable not to make the expiration date too short as this will cause the system to reload data from the database too frequently. Meanwhile, it is advisable not to make the expiration date too long as the data can become stale. 

Consistency: This involves keeping the data store and the cache in sync. Inconsistency can happen because data-modifying operations on the data store and cache are not in single transaction. When scaling across multiple regions, maintaining consistency between 

the data store and cache is challenging 

Mitigating failures: A single cache server represents a potential single point of failure(SPOF), defined in Wikipedia as follows: “A single point of failure (SPOF) is a part of a system that, if it fails, will stop the entire system from working” [8]. As a result, multiple cache servers across different data centers are recommended to avoid SPOF. Another recommended approach is to over provision the required memory by certain percentages.This provides a buffer as the memory usage increases. 

Eviction Policy:Once the cache is full, any requests to add items to the cache might cause existing items to be removed. This is called cache eviction. Least-recently-used(LRU) is the most popular cache eviction policy. Other eviction policies, such as the Least Frequently Used (LFU) or First in First Out (FIFO), can be adopted to satisfy different use cases. 

A Content delivery network (CDN) a network of geographically dispersed servers used to deliver static content. CDN servers cache static content like images, videos, CSS, JavaScript files, etc. 

CDN can also be used for Dynamic content caching which is a relatively new. It enables the caching of HTML pages that are based on request path, query strings, cookies,and request headers. 

https://www.cloudflare.com/learning/cdn/caching-static-and-dynamic-content/ 

when a user visits a website, a CDN server closest to the user will deliver static content. Intuitively, the further users are from CDN servers, the slower the website loads. For example, if CDN servers are in San Francisco, users in Los Angeles will get content faster than users in Europe.  

User A tries to get image.png by using an image URL. The URL’s domain is provided by the CDN provider. The following two image URLs are samples used to demonstrate what image URLs look like on Amazon and Akamai CDNs:•https://mysite.cloudfront.net/logo.jpg 

If the CDN server does not have image.png in the cache, the CDN server requests the file from the origin, which can be a web server or online storage like Amazon S3. 

The origin returns image.png to the CDN server, which includes optional HTTP header Time-to-Live (TTL) which describes how long the image is cached. 

The CDN caches the image and returns it to User A. The image remains cached in the CDN until the TTL expires. 

User B sends a request to get the same image. 

The image is returned from the cache as long as the TTL has not expired. 

Considerations of using a CDN: 

Cost: CDNs are run by third-party providers, and you are charged for data transfers in and out of the CDN. Caching infrequently used assets provides no significant benefits so you should consider moving them out of the CDN. 

Setting an appropriate cache expiry: For time-sensitive content, setting a cache expiry time is important.The cache expiry time should neither be too long nor too short. If it is too long, the content might no longer be fresh. If it is too short, it can cause repeat reloading of content from origin servers to the CDN. 

CDN fallback: You should consider how your website/application copes with CDN failure. If there is a temporary CDN outage, clients should be able to detect the problem and request resources from the origin. 

Invalidating files: You can remove a file from the CDN before it expires by performing one of the following operations: 

•Invalidate the CDN object using APIs provided by CDN vendors. 

•Use object versioning to serve a different version of the object. To version an object,you can add a parameter to the URL, such as a version number. For example, version number 2 is added to the query string: image.png?v=2. 

1. Static assets (JS, CSS, images, etc.,) are no longer served by web servers. They are fetched from the CDN for better performance. 

2. 2. The database load is lightened by caching data. 

summary of how we scale our system to support millions of users: 

•Keep web tier stateless 

•Build redundancy at every tier 

•Cache data as much as you can 

•Support multiple data centers 

•Host static assets in CDN 

•Scale your data tier by sharding 

•Split tiers into individual services 

•Monitor your system and use automation tools