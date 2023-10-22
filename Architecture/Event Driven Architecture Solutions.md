![[Pasted image 20231003141446.jpg]]


Event-Driven Architecture (EDA) is an architectural pattern that emphasizes the production, detection, consumption, and reaction to events. 

In an event-driven system, events represent significant occurrences or state changes, and components communicate by producing or consuming events. This approach promotes loose coupling and flexibility, allowing different parts of a system to react to events without direct dependencies.  

There are architectures with an architectures like in the instance of microservices It can have event driven architecture being built inside of it.
  
Key concepts in Event-Driven Architecture include:  
  
1. **Events:**  
- Events are messages or signals that represent a change in state or a significant occurrence within a system. Examples of events include user actions, system notifications, or changes in data.  
  
2. **Event Producers:**  
- Components or services that generate and emit events are known as event producers. These could be user interfaces, microservices, sensors, or any part of the system that can trigger events.  
  
3. **Event Consumers:**  
- Components or services that respond to and process events are known as event consumers. They subscribe to or listen for specific types of events and take appropriate actions when those events occur.  
  
4. **Event Bus or Broker:**  
- An event bus or event broker acts as an intermediary for events, facilitating communication between producers and consumers. It is responsible for routing events to the correct consumers based on subscriptions.  
  
Event-Driven Architecture is not necessarily a combination of specific technologies like microservices, serverless, or streaming. Instead, it is a design paradigm that can be implemented using various technologies and architectural styles.

However, it is common to see combinations of event-driven architecture with other architectural patterns and technologies to address specific requirements:  
  
**Microservices and Event-Driven Architecture:**  
- Microservices architectures often align well with event-driven patterns. Each microservice can emit events when its state changes, allowing other microservices to react to those events.  
  
**Serverless and Event-Driven Architecture:**  
- Serverless architectures often leverage an event-driven model, where functions (FaaS) are triggered by events. This enables scalable and cost-efficient handling of specific functionalities.  
  
**Streaming and Event-Driven Architecture:**  
- Streaming platforms, such as Apache Kafka(Includes Zookeeper), can be used to implement event-driven architectures. They provide a scalable and resilient infrastructure for event streaming, enabling real-time communication between components.  
  





  
  

  
FaaS function as a service which is on cloud computing  
[https://www.ibm.com/topics/faas#:~:text=FaaS%2C%20or%20Function%2Das%2D,building%20and%20launching%20microservices%20applications](https://www.ibm.com/topics/faas#:~:text=FaaS%2C%20or%20Function%2Das%2D,building%20and%20launching%20microservices%20applications).