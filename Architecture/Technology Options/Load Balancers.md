---
tags: 
author:
  - jacgit18
Status: refinement
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