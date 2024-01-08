---
tags:
  - scaling
  - systemDesign
author:
  - jacgit18
Status: done
Started: 
EditDate: 
Relates:
---
## Concurrency  

Concurrency and horizontal scaling are related but distinct concepts in the context of handling increased workloads in software applications. Here's the difference between the two:  

- **Definition**: Concurrency refers to an application's ability to execute multiple tasks or processes simultaneously. It's about efficiently managing and executing multiple tasks concurrently within a single instance of the application.  
  
- **Key Points**:  
- Concurrency is often achieved through techniques like multi-threading or asynchronous programming.  
- It's essential for maximizing the utilization of available system resources and improving responsiveness.  
- Concurrency primarily deals with optimizing the performance of a single instance of the application.  
  
- **Example**: In a web server, concurrency is the ability to handle multiple incoming HTTP requests simultaneously by efficiently managing and processing them concurrently within the same server instance.  
  
## Horizontal Scaling  
  
- **Definition**: Horizontal scaling, also known as scaling out, involves adding more instances of the application to distribute the workload. It's a strategy for handling increased demand by creating multiple, separate instances of the application.  
  
- **Key Points**:  
- Horizontal scaling is typically used to improve an application's capacity to handle increased traffic, data processing, or computational loads.  
- It doesn't necessarily deal with how tasks are executed within a single instance but focuses on adding more instances to share the load.  
- Horizontal scaling often involves load balancing to evenly distribute requests across multiple instances.  
  
- **Example**: When a popular website experiences high traffic, it can horizontally scale by deploying multiple web server instances behind a load balancer, ensuring that each instance shares the incoming requests.  
  
In summary, concurrency is about how efficiently an application can manage multiple tasks within a single instance, while horizontal scaling is the strategy of adding more instances of the application to distribute the workload. Both are techniques used to handle increased workloads, but they address different aspects of scaling and optimization. In practice, applications may utilize both concurrency and horizontal scaling to provide responsive and scalable services.