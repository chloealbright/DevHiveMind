-   A cache is temporary storage that is relatively smaller in size with faster access time. Caches are used to reduce latency and reduce the load on your servers and databases. There are several levels at which caches are implemented. These are as follows: 
    
    -   Client Caching: Caches are located on the client-side like browser, file system, and servers acting as reverse-proxy. 
        
    -   CDN Caching: CDN (Content Delivery Network) is also used as a cache for serving static content (e.g. HTML, CSS, JavaScript, Images, Videos, etc.). 
        
    -   Web Server Caching: Webservers also implement local caches and can retrieve, and return information without contacting downstream servers. 
        
    -   Database Caching: Databases by default include some level of caching so that they do not have to run queries repeatedly. This can boost the performance of databases when they are under a lot of load. 
        
    -   Application Caching: In application caching, the cache is placed between the application and data stores. These caches usually store database query results and/or objects that the application uses. Typical application caches include Memcached, Redis, DynamoDB, etc. 
        
    -   One of the challenges with caching is ensuring consistency of the data between the cache and the underlying data layer (i.e. server or database).