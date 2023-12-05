![[URI.png]]

Each URI path segment, separated by forward slashes (/), represents a design opportunity.  

Assigning meaningful values to each path segment helps to clearly communicate the hierarchical structure of a REST API’s resource model design. 

When should URI path segments be named with plural nouns? 

add ‑s to the end of  regular nouns to make plural  

singular noun ends in ‑s, -ss, -sh, -ch, -x, or -z, add ‑es to the end to make it plural. 

In some cases, singular nouns ending in -s or -z, require that you double the -s or -z prior to adding the -es for pluralization. 

a URI or Universal Resource Identifier, is described as a "compact sequence of characters "that identifies an abstract or physical resource" that "provides a simple and extensible means "for identifying a resource." The URI is the most generic method for naming and locating a web resource. The official examples of URIs show you that any sequence of characters that identifies a resource is considered a URI. The URL, or Universal Resource Locator, is a subset of the URI. The URL not only identifies a resource, but also explains how to access that resource by providing an explicit method like HTTP or FTP. In other words, all URLs are URIs, but not all URIs are URLs. There's also another subset of URIs we rarely talk about, the URN, or Universal Resource Name. The URN refers to both URIs under the URN scheme and to any other URI with the properties of a name. The classic explanation of the difference between a URN and a URL is to say the URN is a unique name identifier, like the name of a person. There are many people named Morten, but only one person name Morten Rand-Hendriksen. Refer to me by my full name and anyone who knows me knows who you're talking about, even if I'm not there and they don't know where I am at the moment. The URL provides my actual physical location. So right now my URL is Earth, USA, California, Carpinteria, etc. On the web, a URN can be either an explicit URN, like oasis:names:spcification:docbook, etc. or it can be a resource name like linkedin.com/learning/instructors/morten-rand-hendrikson. Finally, a URN can also be a URL, but doesn't have to be. So in conclusion, a URL might also be a URN and both are URIs. When we talk about REST APIs, we typically use the generic term URI to refer to how we access resources because within our code, we can use either URLs or URNs or a combination and URIs cover all options. 



collection contains stores which stores document 

collection-c/stores-s/document-d 

**Rule: A singular noun should be used for document names 

http://api.soccer.restapi.org/leagues/seattle/teams/trebuchet/players/claudio 

**Rule: A plural noun should be used for collection names 

http://api.soccer.restapi.org/leagues/seattle/teams/trebuchet/players 

**Rule: A plural noun should be used for store names 

http://api.music.restapi.org/artists/mikemassedotcom/playlists 

**Rule: A verb or verb phrase should be used for controller names 

http://api.college.restapi.org/students/morgan/register 

http://api.build.restapi.org/qa/nightly/runTestSuite 

**Rule: Variable path segments may be substituted with identity-based values 

Some URI path segments are static; meaning they have fixed names that may be chosen by the REST API’s designer. Other URI path segments are variable, which means that they are automatically filled in with some identifier that may help provide the URI with its uniqueness. The URI Template syntax[21] allows designers to clearly name both the static and variable segments. A URI template includes variables that must be substituted before resolution. The URI template example below has three variables (leagueId, teamId, and playerId): 

http://api.soccer.restapi.org/leagues/{leagueId}/teams/{teamId}/players /{playerId} 

The substitution of a URI template’s variables may be done by a REST API or its clients. Each substitution may use a numeric or alphanumeric identifier, as shown in the examples below: 

http://api.soccer.restapi.org/leagues/seattle/teams/trebuchet/players/21   

**Rule: CRUD function names should not be used in URIs 

For example, this API interaction design is preferred: 

	DELETE /users/1234 


The following anti-patterns exemplify what not to do: 

	GET /deleteUser?id=1234 

	GET /deleteUser/1234 

	DELETE /deleteUser/1234 

	POST /users/1234/delete 

Api URL Rule 

	Rule: Hyphens (-) should be used to improve the readability of URIs 

	Rule: Underscores (_) should not be used in URIs 

	Rule: Lowercase letters should be preferred in URI paths 

	Rule: File extensions should not be included in URIs 

	Rule: Consistent subdomain names should be used for your APIs 

	http://api.soccer.restapi.org as oppose to http://api.soccer.restapi.org 

	Rule: Consistent subdomain names should be used for your client developer portal 

http://developer.soccer.restapi.org 

## Resource Modeling 

The URI path conveys a REST API’s resource model, with each forward slash separated path segment corresponding to a unique resource within the model’s hierarchy. For example, this URI design: 

http://api.soccer.restapi.org/leagues/seattle/teams/trebuchet 

indicates that each of these URIs should also identify an addressable resource: 

http://api.soccer.restapi.org/leagues/seattle/teams 

http://api.soccer.restapi.org/leagues/seattle 

http://api.soccer.restapi.org/leagues 

http://api.soccer.restapi.org 

Resource modeling is an exercise that establishes your API’s key concepts. This process is similar to the data modeling for a relational database schema or the classical modeling of an object-oriented system. 

Before diving directly into the design of URI paths, it may be helpful to first think about the REST API’s resource model. 

## Resource Archetypes 

Document | Collection | Store | Controller  

A document resource is a singular concept that is akin to an object instance or database record. A document’s state representation typically includes both fields with values and links to other related resources. With its fundamental field and link-based structure, the document type is the conceptual base archetype of the other resource archetypes. 

http://api.soccer.restapi.org/leagues/seattle/teams/trebuchet/players/mike 

A collection resource is a server-managed directory of resources. Clients may propose new resources to be added to a collection. However, it is up to the collection to choose to create a new resource, or not. A collection resource chooses what it wants to contain and also decides the URIs of each contained resource. 

http://api.soccer.restapi.org/leagues/seattle/teams/trebuchet/players 

A store is a client-managed resource repository. A store resource lets an API client put resources in, get them back out, and decide when to delete them. On their own, stores do not create new resources; therefore a store never generates new URIs. Instead, each stored resource has a URI that was chosen by a client when it was initially put into the store. 

The example interaction below shows a user (with ID 1234) of a client program using a fictional Soccer REST API to insert a document resource named alonso in his or her store of favorites: 

	PUT /users/1234/favorites/alonso 

A controller resource models a procedural concept. Controller resources are like executable functions, with parameters and return values; inputs and outputs. 

Like a traditional web application’s use of HTML forms, a REST API relies on controller resources to perform application-specific actions that cannot be logically mapped to one of the standard methods HTTP 

Controller names typically appear as the last segment in a URI path, with no child resources to follow them in the hierarchy. The example below shows a controller resource that allows a client to resend an alert to a user: 

	POST /alerts/245743/resend 

https://www.grammarly.com/blog/plural-nouns/



## Difference between route and endpoint?

3 different concepts here: 

Resource: {id: 42, type: employee, company: 5} 

Route: localhost:8080/employees/42 

Endpoint: GET localhost:8080/employees/42 

You can have different endpoints for the same route, such as DELETE localhost:8080/employees/42. So endpoints are basically actions. 

Also you can access the same resource by different routes such as localhost:8080/companies/5/employees/42. So a route is a way to locate a resource. 

Any application back end or front end needs routes in order to be able to call a URL and get something back in a web application. You can call a route and go to a specific page or you can also use routes to define your end points in an application. 

https://developer.wordpress.org/rest-api/extending-the-rest-api/routes-and-endpoints/ 

https://www.freecodecamp.org/news/here-is-the-most-popular-ways-to-make-an-http-request-in-javascript-954ce8c95aaa/


## Smart Endpoints and Dumb Pipes

As per this principle, the data-processing logic should be located in the Microservices themselves, rather than in a centralized hub, to ensure scalability and reliability. If you are wondering what is endpoints and Pipes means here, endpoints are APIs or URLs while pipes are queues an database.

The pattern suggests that endpoints, such as user interfaces or APIs, should be designed to be smart, handling all presentation and business logic, _while pipes, such as queues or databases,_ should be designed to be dumb, performing only simple data transfer and storage functions.

For example, a microservice could be responsible for processing customer orders, rather than having a centralized hub handle all order processing.

The key benefit of using this pattern is that it enables development teams to create applications with loosely coupled components that can be developed and deployed independently, allowing for better scalability and easier maintenance.

This pattern also helps to simplify the development process, as developers can focus on implementing specific features in their smart endpoints rather than worrying about the underlying communication and data storage systems.

However, one drawback of this pattern is that it can make debugging more difficult, as errors may occur in multiple components. Additionally, smart endpoints may require more resources and processing power, which can increase the cost of running the application.

Here is a nice diagram which illustrate this principle:

![](https://miro.medium.com/v2/resize:fit:700/0*wB3H5DE2QXv8at0i.png)



