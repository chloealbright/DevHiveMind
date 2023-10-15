-   Messaging queues make it possible for services to communicate with each other asynchronously. The typical use cases of messaging queues tend to send clients notifications. These notifications can be alerts, emails, messages, etc. The basic architecture of a messaging queue consists of the following: 
    

-   Producer: The service that produces messages and writes them on the messaging queue. 
    
-   Consumer: The service that consumes messages and reads them off the messaging queue. 
    

-   The essential characteristics of a messaging queue are as follows: 
    
    -   Scalable: A messaging queue should be able to scale to millions of messages per hour. It should scale horizontally and preserve the basic guarantees when more nodes are added to the system. 
        
    -   Distributed: A messaging queue should be distributed to scale up and support multiple consumers, producers, and messaging using a cluster of nodes. 
        
    -   Reliability: A messaging queue should be reliable and not drop messages. If the error rate is high, i.e., many messages get settled, then the burden falls on the client to perform checks on the data. This makes the message queue inefficient to use. 
        
    -   Performance: A message queue should support high throughput and low latency when delivering messages. 
        
    -   Easy to use interface: A messaging queue should provide a simple API interface to integrate with the client applications (i.e., producers and consumers) for broader adoption.