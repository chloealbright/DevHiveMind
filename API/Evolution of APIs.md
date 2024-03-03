---
tags:
  - API
  - REST
author:
  - jacgit18
  - chatgpt
Comments: This documentation discusses different types of APIs.
Status: Done
Started: 
EditDate: 2024-03-02
Relates:
---
APIs are a set of protocols that define how system components interact with each other. As architectural styles evolve, APIs have gained prominence in recent years. The diagram below shows how the rise of microservices and cloud-native applications brings further granularity to services. In-process calls in monolithic applications transition to inter-process calls in microservice and serverless applications. Additionally, each process might reside on a different physical server, and service calls can fail due to various network issues.

Increased service complexity emphasizes the need for more disciplined API designs.
![[mono to Servless .png]]

1. **Data APIs (RESTful APIs):**  
	- These APIs primarily deal with data retrieval or manipulation. They are designed to expose data, often in a structured format such as JSON or XML.  
	- Examples include APIs that retrieve information from a database, weather data, user profiles, or any other form of data that can be queried or manipulated.  
  
2. **Service APIs (Functional APIs):**  
	- These APIs provide specific functions or services that can be utilized by applications or systems.  
	- Examples include APIs that facilitate sending emails (e.g., SendGrid for email services), processing payments, translating text, image recognition, or any other service-oriented functionality.  
  
3. **RESTful APIs:**  
	- RESTful APIs (Representational State Transfer) are a common type of data API that follows principles such as statelessness, client-server architecture, and resource-based endpoints.  
	- RESTful APIs are often used for data-related operations, providing a standard approach for accessing and manipulating resources.  
  
4. **RPC APIs (Remote Procedure Call):**  
	- RPC APIs are a form of service API where the focus is on invoking procedures or functions remotely.  
	- Examples include APIs that expose specific functionalities or services for remote invocation, allowing developers to call functions on a remote server.  
  
In the case of SendGrid, it falls into the category of a service API. SendGrid provides a set of functions or services related to email, allowing developers to integrate email sending functionality into their applications.  
  
It's worth noting that these distinctions can sometimes blur, as APIs may offer both data-related operations and specific functions or services. The choice of terminology often depends on the primary purpose or focus of the API.