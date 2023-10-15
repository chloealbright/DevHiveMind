![[1_AXw-H6_4gYbKlkA8d2u_cA.png]]
As per Decentralized Data Management principle, each Microservice should manage its own data, without relying on other Microservice, to ensure scalability and reliability. For example, each Microservice could have its own database that it uses to store data.

Sharing Database with other Microservices violate this principle and should be avoided as it will make it difficult to troubleshoot and can result in data inconsistency.

This design principle will help you better manage your database its also a basis of Database per Microservice design pattern, an essential Microservice Design Principle.

If you are thinking about how could then another Microservice get access to the same data as its very much possible that another service do need it? Well, you should always create APIs for that as we going to see in next Microservice design principle.

You can see this in following Microservice architecture we have different database for UserService, MessageService and FriendService.