---
tags: 
author:
  - jacgit18
Status: Refinement
Started: 
EditDate: 
Relates:
---
-   A load balancer is a device that acts as a reverse proxy and distributes the network traffic across several different servers. Load balancers are used to scale distributed systems by distributing traffic between other servers. Load balancers are typically grouped into two distinct categories: Layer 4 and Layer 7. The load balancers at layer 4 act upon data found in network and transport layer protocols (IP, TCP, FTP, UDP). Layer 7 load balancers distribute requests based on application data (HTTP). Some of the standard algorithms that load balancers use are: 
    

-   Round Robin 
    
-   Weighted Round Robin 
    
-   Least connections 
    
-   Least response time 
    

**DNS ->load balancer(also  makes all server appear as one IP) -> server pool -> cache ->DB 

adding more servers create a bug because some might be state and not stateless that is why you push that down to data cache or database  away from the app server also adding more servers horizontally can affect the data base so vertical scale and get a bigger Data base 

ways to scale 

use replication for backups  

you would use a load balancer between this 

and have a master db that writes and slaves that reads 

they can be replica lag where you need to turn off site to clear it 


then there is shading or partitioning but there are issues with joins 

other option is distributed database but should avoid  because u sacrifice  consistence for availability  

as the platform grows you may need microservies


A load balancer is a category of technology rather than a specific technology. It refers to a device or software application that distributes network or application traffic across multiple servers to ensure no single server bears too much load, thereby improving the reliability, availability, and scalability of a system.  
  
There are different types of load balancers, and they can be implemented in various ways:  
  
1. **Hardware Load Balancers:** Dedicated physical devices designed to distribute traffic across servers.  
  
2. **Software Load Balancers:** Load balancing functionality implemented in software, often running on commodity hardware.  
  
3. **Application-Based Load Balancers:** Load balancing functionality integrated into applications or services.  
  
Load balancers can operate at different layers of the OSI model, such as:  
  
- **Layer 4 (Transport Layer):** Distributes traffic based on information in the transport layer, like IP addresses and port numbers. This is known as a TCP/UDP load balancer.  
  
- **Layer 7 (Application Layer):** Makes decisions based on application layer data, such as HTTP header information. This is known as an application or content-aware load balancer.  
  
API gateways and proxy servers, on the other hand, serve different purposes but may include load balancing features as part of their functionality. An API gateway manages, routes, and secures API traffic, while a proxy server acts as an intermediary between clients and servers.  
  
In summary, "load balancer" is a broad term encompassing various technologies that share the common goal of distributing network or application traffic to optimize performance and reliability. Different implementations cater to different needs and architectural requirements.