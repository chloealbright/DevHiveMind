---
tags:
  - scaling
  - revist
  - review
  - systemDesign
author:
  - jacgit18
Comments: This documentation discusses Scaling.
Status: Refinement
Started: 
EditDate: 2024-02-25
Relates: "[[Dynamic Scaling]]"
---
![[System Scaling.png]]
# Horizontal scaling  

Horizontal scaling (aka scaling out) refers to adding additional nodes or machines to your infrastructure more specifically adding more instances of the application to distribute the workload and cope with new demands. If you are hosting an application on a server and find that it no longer has the capacity or capabilities to handle traffic, adding a server may be your solution. 

It is quite similar to delegating workload among several employees instead of one. However, the downside of this may be the added complexity of your operation. You must decide which machine does what and how your new machines work with your old machines.  

**Example**: When a popular website experiences high traffic, it can horizontally scale by deploying multiple web server instances behind a load balancer, ensuring that each instance shares the incoming requests.  


## Advantages of horizontal scaling 

Scaling is easier from a hardware perspective - All horizontal scaling requires you to do is add additional machines to your current pool. It eliminates the need to analyze which system specifications you need to upgrade. 

Fewer periods of downtime - Because you’re adding a machine, you don’t have to switch the old machine off while scaling. If done effectively, there may never be a need for downtime and clients are less likely to be impacted. 

Increased resilience and [[Fault tolerance]] - Relying on a single node for all your data and operations puts you at a high risk of losing it all when it fails. Distributing it among several nodes saves you from losing it all.  

Increased performance - If you are using horizontal scaling to manage your network traffic, it allows for more endpoints for connections, considering that the load will be delegated among multiple machines.    

## Disadvantages of horizontal scaling 

Increased complexity of maintenance and operation - Multiple servers are harder to maintain than a single server is. Additionally, you will need to add software for load balancing and possibly virtualization. Backing up your machines may also become a little more complex. You will need to ensure that nodes synchronize and communicate effectively.  

Increased Initial costs - Adding new servers is far more expensive than upgrading old ones.    


## Horizontal Scaling Relationship with Concurrency

Concurrency and horizontal scaling are related but distinct concepts in the context of handling increased workloads in software applications. Here's the difference between the two:  

- **Definition**: Concurrency refers to an application's ability to execute multiple tasks or processes simultaneously. It's about efficiently managing and executing multiple tasks concurrently within a single instance of the application.  
  
- **Key Points**:  
- Concurrency is often achieved through techniques like multi-threading or asynchronous programming.  
- It's essential for maximizing the utilization of available system resources and improving responsiveness.  
- Concurrency primarily deals with optimizing the performance of a single instance of the application.  
  
- **Example**: In a web server, concurrency is the ability to handle multiple incoming HTTP requests simultaneously by efficiently managing and processing them concurrently within the same server instance.  

## Horizontal Scaling Relationship with Load Balancing

When employing horizontal scaling, a load balancer sits in front of the multiple servers and acts as the entry point for incoming requests. Its primary role is to distribute the incoming traffic across the available servers in a way that ensures an even distribution of workloads. The load balancer uses various algorithms to determine which server should handle each incoming request, based on factors like server health, current load, response time, and more. By effectively distributing the workload, horizontal scaling helps prevent individual servers from becoming overloaded, thereby enhancing system performance and reliability.


# Vertical scaling  

Vertical scaling (aka scaling up) describes adding additional resources to a system so that it meets demand. How is this different from horizontal scaling?  

While horizontal scaling refers to adding additional nodes, vertical scaling describes adding more power to your current machines. For instance, if your server requires more processing power, vertical scaling would mean upgrading the CPUs. You can also vertically scale the memory, storage, or network speed. 

Additionally, vertical scaling may also describe replacing a server entirely or moving a server’s workload to an upgraded one.  

## Advantages of vertical scaling 

Cost-effective - Upgrading a pre-existing server costs less than purchasing a new one. Additionally, you are less likely to add new backup and virtualization software when scaling vertically. Maintenance costs may potentially remain the same too. 

Less complex process communication - When a single node handles all the layers of your services, it will not have to synchronize and communicate with other machines to work. This may result in faster responses. 

Less complicated maintenance - Not only is maintenance cheaper but it is less complex because of the number of nodes you will need to manage.  

Less need for software changes - You are less likely to change how the software on a server works or how it is implemented.          

## Disadvantages of vertical scaling 

Cost-effective - Upgrading a pre-existing server costs less than purchasing a new one. Additionally, you are less likely to add new backup and virtualization software when scaling vertically. Maintenance costs may potentially remain the same too. 

Less complex process communication - When a single node handles all the layers of your services, it will not have to synchronize and communicate with other machines to work. This may result in faster responses. 

Less complicated maintenance - Not only is maintenance cheaper but it is less complex because of the number of nodes you will need to manage.  

Less need for software changes - You are less likely to change how the software on a server works or how it is implemented.


## Vertical Scaling Relationship with Concurrency 

- Vertical scaling can indirectly impact concurrency. By increasing the resources of a single machine, you can potentially handle a higher level of concurrency because the machine has more processing power and memory to manage multiple tasks simultaneously.  
  
- However, vertical scaling has its limitations, and there comes a point where further increases in resources on a single machine may not be cost-effective or practical. At that stage, horizontal scaling (adding more machines) may become a more viable option.  
  
**Considerations:**  
- **Concurrency Management:** Even with vertical scaling, effective concurrency management strategies are essential. This involves proper thread or process handling, synchronization, and resource allocation to ensure efficient utilization of the available resources.  
  
- **Scalability Strategies:** Systems often employ a combination of vertical and horizontal scaling strategies to achieve both increased resource capacity and enhanced concurrency handling. The choice depends on the specific requirements and constraints of the application.  

## Vertical Scaling Relationship with Load Balancing

Unlike horizontal scaling, where multiple servers handle the load, vertical scaling typically involves a single server. Therefore, load balancing in the context of vertical scaling may not seem as relevant at first glance. However, in some cases, vertical scaling can be complemented with a limited form of load balancing.

For example, even if you have a powerful server after vertical scaling, you can still use a load balancer to distribute traffic across different components of the server, such as multiple CPUs or network interfaces. This can help make better use of the server's internal resources and improve its overall performance.

## Load Balancing Scaling 

**Resilience**
One of the major problems with vertical scaling is of **Single Point of Failure**. If the system fails, you don’t have any backup. Horizontal scaling provides us with resilience, meaning it can handle failure as there are other nodes to function if one of the nodes fails!

**Interaction/ Calls between System**
To communicate between nodes in horizontal scaling, Network calls are made, whereas in vertical scaling is simple Interprocess communication which is faster.

**Data Consistency**
It is quite logical to see why there is Data Consistency in Vertical Scaling, as there is a single data point. In contrast, there is a chance of Data Inconsistency as there are multiple nodes and data points in Horizontal Scaling.

**Hardware Limitations**
Don’t you think that vertical scaling has a fundamental problem of reaching saturation? You keep increasing the computation power of a single machine, but there has to be a point where it will become almost impossible to go further. This is the hardware limitation of Vertical Scaling, which is not the case for Horizontal Scaling, that scales well.




# Microservice Scaling 
At a higher scope, in terms of microservices, you can apply both vertical and horizontal scaling as well. Vertical scaling might involve optimizing the performance of a single microservice, while horizontal scaling can involve deploying multiple instances of a microservice to handle increased loads. This is a common approach in microservices architectures to achieve scalability and fault tolerance.


## Horizontal Scaling (Microservices):
   - In microservices, horizontal scaling means adding more instances of the same service to distribute the load and improve redundancy.
   - Instead of making a single service more powerful, you add more identical instances of the service to handle more requests and increase fault tolerance.
   - Horizontal scaling is beneficial when the system needs to handle increased traffic and needs redundancy and high availability.


## Vertical Scaling (Microservices):
- In microservices architecture, vertical scaling involves increasing the resources (CPU, memory, etc.) of a single service or component to handle increased load or demand.
   - This means that you're making the existing service more powerful by adding more capacity to it.
   - Vertical scaling is suitable when a specific microservice is a performance bottleneck, and you want to optimize it by enhancing its capabilities.

