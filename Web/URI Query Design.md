---
tags: 
author:
  - jacgit18
Status: 
Started: 
EditDate: 
Relates:
---
As a component of a URI, the query contributes to the unique identification of a resource. Consider the following example: 

http://api.college.restapi.org/students/morgan/send-sms   

http://api.college.restapi.org/students/morgan/send-sms?text=hello  

Rule: The query component of a URI may be used to filter collections or stores 

GET /users   

GET /users?role=admin   

Rule: The query component of a URI should be used to paginate collection or store results 

A REST API client should use the query component to paginate collection and store results with the pageSize and pageStartIndex parameters. The pageSize parameter specifies the maximum number of contained elements to return in the response. The pageStartIndex parameter specifies the zero-based index of the first element to return in the response. For example: 

GET /users?pageSize=25&pageStartIndex=50 

When the complexity of a client’s pagination (or filtering) requirements exceeds the simple formatting capabilities of the query part, consider designing a special controller resource that partners with a collection or store. For example, the following controller may accept more complex inputs via a request’s entity body instead of the URI’s query part: 

POST /users/search 

This design allows for custom range types and special sort orders to be easily specified in the client request message body. However, as detailed in Chapter 4, care must be taken to ensure that the controller’s cacheable results are marked accordingly.






Query Parameters 

this calls ending res status 200 as expected  

res body empty 

The limit query parameter is used to include in a first page of a response only the first N items of a resource collection. 

The offset query parameter is used to exclude from a response the first N items of a resource collection. 

The sort query parameter is used to sort items in a resource collection returned in a response. 

The filter query parameter is used to filter items in a resource collection to return a subset of resources in a response. The subset includes only those resources that satisfy parameter value specified in the query. 

total — total number of resources returned. 

count — number of resources on the current page. The default value is 100. You can modify this number using the limit parameter. 

offset — number of resources skipped. You can skip resources using the offset parameter. 

The SQL INCLUDE specifies the SQL table information to be used to generate field definitions. It names the table and gives the location where the field definitions are to be generated. 

[https://guides.emberjs.com/release/routing/query-params/](https://guides.emberjs.com/release/routing/query-params/)