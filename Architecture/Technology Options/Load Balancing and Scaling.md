---
tags:
  - scaling
  - systemDesign
author:
  - jacgit18
Status: 
Started: 
EditDate: 
Relates:
---

## Dynamic Scaling

dynamic scaling refers to the capability of a system to automatically adjust its resources based on real-time demand. Let's explore the relationship between horizontal and vertical scaling concerning dynamic scaling:



### Dynamic Scaling with Horizontal Scaling:
Dynamic scaling complements horizontal scaling very effectively. When the system is designed for dynamic scaling, it can automatically add or remove servers based on the current demand and resource utilization. This process is often managed by an autoscaling system, which monitors key performance metrics like CPU usage, network traffic, or the number of requests per second.

For instance, during a sudden spike in traffic, the autoscaling system detects the increased load and automatically provisions additional servers to handle the incoming requests. As the traffic subsides, it can then scale down the number of servers to avoid unnecessary costs. This way, horizontal scaling combined with dynamic scaling ensures that the system efficiently adapts to varying workloads while maintaining performance and cost-effectiveness.




### Dynamic Scaling with Vertical Scaling:
Dynamic scaling is less commonly associated with vertical scaling, mainly because vertical scaling deals with individual servers. Nevertheless, there are scenarios where dynamic scaling can still play a role, especially in cloud-based environments.

For example, in a cloud environment, dynamic scaling can be applied to vertically scaled instances. The cloud platform can automatically adjust the computing resources of individual servers based on real-time demand. So, during peak times, the platform can increase the CPU and RAM allocation to handle higher workloads, and during periods of lower demand, it can scale down the resources to optimize costs.

In summary, both horizontal and vertical scaling can benefit from dynamic scaling to efficiently adapt to changing workloads. Horizontal scaling typically sees more extensive use with dynamic scaling, as it involves adding or removing entire servers from the system. On the other hand, dynamic scaling with vertical scaling can be useful in cloud environments, where individual instances can be automatically adjusted based on demand. The combination of dynamic scaling with either horizontal or vertical scaling ensures that a system remains responsive, highly available, and cost-effective, regardless of varying workloads.



## Example

For the Cre8tive springboot code we run multiple account services instances in terminal to process as many network request around accounservice for all existing user distributing that traffic across the many instances  

  
Load balancer in form of some business logic or imported library with this logic or in context of java annotation would handle the actual implementation of the balancing which is used to manage all these instances.  
  
Also by default load balancers uses Ron Robin approach to decide on which service instances to manage/utilize for traffic.