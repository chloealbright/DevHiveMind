Load balancing is a critical concept in the field of distributed systems and computer networking. It refers to the distribution of workloads across multiple computing resources to ensure optimal resource utilization, minimal response time, and high availability. Load balancing becomes particularly important in scenarios where a single server or resource is not sufficient to handle all incoming requests, which is common in high-traffic web applications, online services, and large-scale systems.

Load balancing can be achieved through various methods, but two fundamental approaches are horizontal scaling and vertical scaling. Let's explore their relationship with load balancing:

1. Horizontal Scaling:
Horizontal scaling, also known as scaling out, involves adding more machines or nodes to a distributed system to handle increasing workloads. In this approach, multiple servers or resources are added to the system, and each server operates independently, serving a portion of the incoming requests. These servers collectively handle the overall load, making it possible to accommodate a larger number of concurrent users or transactions.

Relationship with Load Balancing:
When employing horizontal scaling, a load balancer sits in front of the multiple servers and acts as the entry point for incoming requests. Its primary role is to distribute the incoming traffic across the available servers in a way that ensures an even distribution of workloads. The load balancer uses various algorithms to determine which server should handle each incoming request, based on factors like server health, current load, response time, and more. By effectively distributing the workload, horizontal scaling helps prevent individual servers from becoming overloaded, thereby enhancing system performance and reliability.




2. Vertical Scaling:
Vertical scaling, also known as scaling up, involves upgrading the existing servers or resources with more powerful hardware components (e.g., increasing CPU, RAM, or storage capacity) to handle increased demands. In this approach, the computing resources of a single server are increased to improve its capability to handle higher workloads and manage more concurrent connections.

Relationship with Load Balancing:
Unlike horizontal scaling, where multiple servers handle the load, vertical scaling typically involves a single server. Therefore, load balancing in the context of vertical scaling may not seem as relevant at first glance. However, in some cases, vertical scaling can be complemented with a limited form of load balancing.

For example, even if you have a powerful server after vertical scaling, you can still use a load balancer to distribute traffic across different components of the server, such as multiple CPUs or network interfaces. This can help make better use of the server's internal resources and improve its overall performance.

In summary, load balancing is a crucial aspect of both horizontal and vertical scaling approaches. Horizontal scaling involves distributing workloads across multiple servers, while vertical scaling focuses on increasing the capacity of a single server. In both cases, a load balancer plays a vital role in ensuring that the workload is efficiently distributed to achieve improved performance, scalability, and high availability.



2. **Resilience**

One of the major problems with vertical scaling is of **Single Point of Failure**. If the system fails, you don’t have any backup. Horizontal scaling provides us with resilience, meaning it can handle failure as there are other nodes to function if one of the nodes fails!

3. **Interaction/ Calls between System**

To communicate between nodes in horizontal scaling, Network calls are made, whereas in vertical scaling is simple Interprocess communication which is faster.

4. **Data Consistency**

It is quite logical to see why there is Data Consistency in Vertical Scaling, as there is a single data point. In contrast, there is a chance of Data Inconsistency as there are multiple nodes and data points in Horizontal Scaling.

5. **Hardware Limitations**

Don’t you think that vertical scaling has a fundamental problem of reaching saturation? You keep increasing the computation power of a single machine, but there has to be a point where it will become almost impossible to go further. This is the hardware limitation of Vertical Scaling, which is not the case for Horizontal Scaling, that scales well.



## Dynamic Scaling

dynamic scaling refers to the capability of a system to automatically adjust its resources based on real-time demand. Let's explore the relationship between horizontal and vertical scaling concerning dynamic scaling:

1. Horizontal Scaling:
As mentioned earlier, horizontal scaling involves adding more machines or nodes to the system to handle increasing workloads. When the demand for resources grows, new servers are added to the system, and they work together to distribute and process the incoming requests. Conversely, when the demand decreases, servers can be removed from the system, allowing for better resource utilization and cost optimization.

Dynamic Scaling with Horizontal Scaling:
Dynamic scaling complements horizontal scaling very effectively. When the system is designed for dynamic scaling, it can automatically add or remove servers based on the current demand and resource utilization. This process is often managed by an autoscaling system, which monitors key performance metrics like CPU usage, network traffic, or the number of requests per second.

For instance, during a sudden spike in traffic, the autoscaling system detects the increased load and automatically provisions additional servers to handle the incoming requests. As the traffic subsides, it can then scale down the number of servers to avoid unnecessary costs. This way, horizontal scaling combined with dynamic scaling ensures that the system efficiently adapts to varying workloads while maintaining performance and cost-effectiveness.





2. Vertical Scaling:
Vertical scaling involves upgrading the hardware resources (e.g., CPU, RAM, storage) of individual servers to increase their capacity to handle more significant workloads. In this approach, the existing servers are improved in terms of their computing power, allowing them to process more requests and handle more concurrent users.

Dynamic Scaling with Vertical Scaling:
Dynamic scaling is less commonly associated with vertical scaling, mainly because vertical scaling deals with individual servers. Nevertheless, there are scenarios where dynamic scaling can still play a role, especially in cloud-based environments.

For example, in a cloud environment, dynamic scaling can be applied to vertically scaled instances. The cloud platform can automatically adjust the computing resources of individual servers based on real-time demand. So, during peak times, the platform can increase the CPU and RAM allocation to handle higher workloads, and during periods of lower demand, it can scale down the resources to optimize costs.

In summary, both horizontal and vertical scaling can benefit from dynamic scaling to efficiently adapt to changing workloads. Horizontal scaling typically sees more extensive use with dynamic scaling, as it involves adding or removing entire servers from the system. On the other hand, dynamic scaling with vertical scaling can be useful in cloud environments, where individual instances can be automatically adjusted based on demand. The combination of dynamic scaling with either horizontal or vertical scaling ensures that a system remains responsive, highly available, and cost-effective, regardless of varying workloads.



## Example

For the Cre8tive springboot code we run multiple account services instances in terminal to process as many network request around accounservice for all existing user distributing that traffic across the many instances  

  
Load balancer in form of some business logic or imported library with this logic or in context of java annotation would handle the actual implementation of the balancing which is used to manage all these instances.  
  
Also by default load balancers uses Ron Robin approach to decide on which service instances to manage/utilize for traffic.