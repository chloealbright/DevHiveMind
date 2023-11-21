![[GetImage (14).png]]

![[55555.jpg]]
Moving from Monolithic to microservice architecture stages.


The microservice architecture is a design paradigm where an application is structured to collect several independent services. The characteristics of these services are as follows: 

For each microservice has its own database

-   Organized around a specific business capability 
    
-   Own by a small team 
    
-   Independently deployable 
    
-   Highly scalable 
    
-   Loosely coupled 
    
-   Highly maintainable and testable

Benefits of microservices is you can choose to expose certain services publicly like an API and keep others privately

## When to use microservice
It makes sense to turn something into a microservice when you want to achieve scalability, maintainability, and independent deployment. However, administrative processes might not be suitable for microservices if they don't require frequent updates or scalability, and if their complexity doesn't warrant the overhead of a separate microservice. It's important to consider the trade-offs and benefits before deciding.



You can define microservices in yaml file



In the realm of microservices and software development, it's imperative that systems exhibit responsiveness, resilience, elasticity, and embrace a message-driven architecture. This ensures not only efficient handling of tasks but also enhances adaptability to varying workloads. Responsive systems promptly react to user inputs, while resilient ones gracefully recover from failures. Elasticity facilitates scalability, enabling systems to handle fluctuating demands seamlessly. Incorporating a message-driven approach promotes effective communication between components, fostering a robust and interconnected software ecosystem.


##  Strangler Design

The strangler design pattern is a popular design pattern to incrementally transform your monolithic application to microservices by replacing old functionality with a new service. Once the new component is ready, the old component is strangled and a new one is put to use.  
  
The facade interface, which serves as the primary interface between the legacy system and the other apps and systems that call it, is one of the most important components of the strangler pattern.  
  
External apps and systems will be able to identify the code associated with a certain function, while the underlying historical system code will be obscured by the facade interface. The strangler design addresses this by requiring developers to provide a façade interface that allows them to expose individual services and functions when they break them free from the monolith.  
  
You need to understand the quality and reliability of your system, whether you're working with legacy code, starting the process of "strangling" your old system, or running a newly containerized application. When anything goes wrong, you need to know how the system got there and why it went down that road.



### Strangler Facade 

The Strangler Facade is a software architectural pattern used in the context of legacy system modernization or migration. It's a gradual approach to replace or refactor an existing system without completely discarding it. Here's how it works:  
  
1. **Strangler Application**: Initially, a new system or application is built alongside the existing one, often using modern technologies and practices.  
  
2. **Routing and Decomposition**: Requests or traffic are gradually routed to the new system for specific functionalities or components. This can be done using a facade or proxy layer that determines whether to forward requests to the old or new system.  
  
3. **Incremental Replacement**: Over time, more and more functionality is moved from the old system to the new one. The old system is gradually "strangled" as its parts are replaced.  
  
4. **Decommissioning**: Eventually, when all critical functionality has been transitioned to the new system and the old system is no longer needed, it can be safely decommissioned.  
  
The Strangler Facade approach allows for a controlled, low-risk migration from legacy systems to more modern ones, reducing the chances of major disruptions and minimizing downtime.  
  
This pattern is often used in scenarios where rewriting the entire system from scratch is impractical due to cost, time, or risk constraints.
