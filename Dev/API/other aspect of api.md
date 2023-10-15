### 5. Backend For Frontend (BFF)

This pattern is used to identify how the data is fetched between the server and clients. Ideally, the frontend team will be responsible for managing the BFF.

  

A single BFF is responsible for handling the single UI and it will help us to keep the frontend simple and see a unified view data through the backend.

  

#### Why BFF needs in our microservice application?

The goal of this architecture is to decouple the front-end apps from the backend architecture.  
As a scenario, think about you have an application that consists of the mobile app, web app and needs to communicate with the backend services in a microservices architecture. 

This can be done successfully but if you want to make a change to one of the frontend services, you need to deploy a new version instead of stick to updating the one service.

So here comes the [microservice architecture](https://javarevisited.blogspot.com/2019/03/5-courses-programmers-can-join-to-learn.html) and this is able to understand what our apps need and how to handle the services.

  

This is a big improvement in microservice architecture as this allows to isolate the backend of the application from the frontend. One other advantage that we can get from this BFF is that we can reuse the code as this allows all clients to use the code from the backend. 

  

Between the client and other external APIs, services, and so on, BFF functions similarly to a proxy server. If the request must pass through another component, the latency will undoubtedly increase.

  

[![Backend For Frontend (BFF) Pattern for Microservices](https://1.bp.blogspot.com/-dHoPBbMRC3o/YUQz56N4uzI/AAAAAAAAC6k/jcvc9Qg3LSo8jte9spDQM1Q6YvtRlVs1wCLcBGAsYHQ/w406-h221/1_2BaGJecjJNBk0gGCUQJO2wdfdf.jpg)](https://1.bp.blogspot.com/-dHoPBbMRC3o/YUQz56N4uzI/AAAAAAAAC6k/jcvc9Qg3LSo8jte9spDQM1Q6YvtRlVs1wCLcBGAsYHQ/s1160/1_2BaGJecjJNBk0gGCUQJO2wdfdf.jpg)

  

  

  

  

### 6. API Gateway

This microservice architecture pattern is really good for large applications with multiple client apps and it is responsible for giving a single entry point for a certain group of microservices. 

  

API gateway sits between the client apps and the microservices and it serves as a reverse proxy, forwarding client requests to services. [Authentication](https://javarevisited.blogspot.com/2018/01/how-http-basic-authentication-works-in.html#axzz6hhgr3Uqg), SSL termination, and caching are some of the other cross-cutting services it can provide.

  

Why do we consider the API Gateway architecture instead of using direct client-to-microservice communication? We will discuss this with the following examples,

**1. Security issues** - All microservices must be exposed to the "external world" without a gateway, increasing the attack surface compared to hiding internal microservices that aren't directly accessed by client apps.

**2. Cross-cutting concerns** - Authorization and SSL must be handled by each publicly published microservice. Those problems might be addressed in a single tier in many cases, reducing the number of internal microservices.

  

**3. Coupling** - Client apps are tied to internal microservices without the API Gateway pattern. Client apps must understand how microservices decompose the application's various sections.

  

Last but not least, the microservices API gateway must be capable of handling partial failures. The failure of a single unresponsive microservice should not result in the failure of the entire request.

  

A microservices API gateway can deal with partial failures in a variety of ways, including:

- Use data from a previous request that has been cached.
- For time-sensitive data that is the request's major focus, return an error code.
- Provide an empty value
- Rely on hardware top 10 value.

|                                                                                                                                                                                                                                                                                                                                    |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [![API Gateway Microservice Pattern explained](https://1.bp.blogspot.com/-_LUpP4X_A9s/YURZnUy7g5I/AAAAAAAAC68/pejt_yTXFIciqAtHcr24jRavMIY1svQ1QCLcBGAsYHQ/w406-h226/api_gateway_nginx.png)](https://1.bp.blogspot.com/-_LUpP4X_A9s/YURZnUy7g5I/AAAAAAAAC68/pejt_yTXFIciqAtHcr24jRavMIY1svQ1QCLcBGAsYHQ/s709/api_gateway_nginx.png) |
| [API Gateway](https://www.java67.com/2021/04/5-free-microservice-courses-for-java.html)                                                                                                                                                                                                                                            |
|                                                                                                                                                                                                                                                                                                                                    |
|                                                                                                                                                                                                                                                                                                                                    |
| 





### **9. Externalized Configuration**

Often services need to be run in different environments. Environment-specific configuration is required, such as secret keys, database credentials, and so on. Changing the service for each environment has a number of drawbacks. So how we can enable a service to run in multiple environments without modification?

  

Here comes the Externalized configuration pattern as this enables the externalization of all application configurations including the database credentials and network location. 

  

For example, the [Spring Boot framework](https://javarevisited.blogspot.com/2018/05/top-5-courses-to-learn-spring-boot-in.html) enables externalized configuration, which allows you to read configuration from many sources and potentially change previously specified configuration settings based on the reading order. FastAPI, thankfully, has built-in support for externalized configuration.

  

  

[![How to externalize Configuration in Microservice](https://1.bp.blogspot.com/-2Xc_qIAxi0Q/YUW9rNDFoVI/AAAAAAAAC7U/1M0nqe--DUA0b2n38zxdQCxUr2UbfpLsACLcBGAsYHQ/w496-h221/external-configuration-store-overview.png)](http://www.java67.com/2018/06/5-best-courses-to-learn-spring-boot-in.html)

  

  

  

Open up the ConfigServerApplication class and activate the discovery client and the configuration server by using the following annotation.

@SpringBootApplication  
@EnableConfigServer  
@EnableDiscoveryClient  
public class ConfigServerApplication {  
  
}  

  

Remove the application.properties file and create a new application.yml file with the following content.

server.port: 8001  
  
spring:  
  application.name: config-server  
  cloud.config.server.git.uri: 
   https://github.com/alejandro-du/vaadin-microservices-demo-config.git  
  

eureka:  
  client:  
    serviceUrl:  
      defaultZone: http://localhost:7001/eureka/  
    registryFetchIntervalSeconds: 1  
  instance:  
    leaseRenewalIntervalInSeconds: 1

  
  

This sets the port (8001) and name (config-server) of the application, as well as the URI 
[Spring Cloud Config](https://www.java67.com/2021/01/spring-cloud-interview-questions-with-answers-java.html) should use to read the configuration from. On GitHub, we have a Git 
repository. The configuration files for all of the example application's microservices can 
be found in this repository. The admin-applicationmicroservic uses the admin-application.yml 
file, for example.
  

  

  
  
  
  

  

### **10. Consumer-Driven Contract Tracing**

When a team is constructing multiple related services at the same time as part of a modernization effort, and your team knows the “domain language” of the bounded context but not the individual properties of each aggregate and event payload, the consumer driven contracts approach may be effective.

[![Consumer-Driven Contract Tracing Pattern in Microservice](https://1.bp.blogspot.com/-Q35kmhh-b_Q/YUXCdcdYCNI/AAAAAAAAC7c/_dD1lE-1wTMhLN_IWlu9wU8AhwVx-g61gCLcBGAsYHQ/w320-h244/1_s-ujrGQyZszBcSdY3PCybw.png)](https://1.bp.blogspot.com/-Q35kmhh-b_Q/YUXCdcdYCNI/AAAAAAAAC7c/_dD1lE-1wTMhLN_IWlu9wU8AhwVx-g61gCLcBGAsYHQ/s1320/1_s-ujrGQyZszBcSdY3PCybw.png)

  
  

This microservice pattern is useful in legacy application which contains a large data model and existing service surface area. This [design patterns](https://medium.com/javarevisited/7-best-online-courses-to-learn-object-oriented-design-pattern-in-java-749b6399af59) will address the following issues,

 1. How can you add to an API without breaking downstream clients. 

 2. How to find out who is using their service.

3. How to make short release cycles with the continuous delivery.

  

In an event driven architecture, many microservices expose two kinds of API's, 

 1. RESTful API over HTTP 

 2. HTTP and a message-based API The [RESTful API](https://javarevisited.blogspot.com/2018/02/top-5-restful-web-services-with-spring-courses-for-experienced-java-programmers.html) allows for synchronous integration with these services as well as extensive querying capabilities for services that have received events from a service. 

In summary, a consumer-driven approach is sometimes used when breaking down a monolithic legacy

application.
