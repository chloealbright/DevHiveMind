---
tags: 
author:
  - jacgit18
Comments: This documentation discusses URI Universal Resources Identifier
Status: Capture
Started: 
EditDate: 
Relates:
---
The query component in a URI plays a crucial role in uniquely identifying a resource. For instance:

- `http://api.college.restapi.org/students/morgan/send-sms`
- `http://api.college.restapi.org/students/morgan/send-sms?text=hello`

**Rule:** The query component can be used to filter collections or stores:

- `GET /users`
- `GET /users?role=admin`

**Rule:** Use the query component for paginating collection or store results:

A REST API client should employ the query component for pagination, specifying parameters like `pageSize` and `pageStartIndex`. For example:

- `GET /users?pageSize=25&pageStartIndex=50`

When client pagination requirements become complex, consider designing a special controller resource. For instance:

- `POST /users/search`

This design allows more intricate inputs via the request's entity body. However, ensure cacheable results are marked accordingly, as detailed in Chapter 4.

###  Query Parameters:
- `limit`: Includes only the first N items of a resource collection in the first page of a response.
- `offset`: Excludes the first N items of a resource collection from a response or you can rephrase this a say the number of resources skipped, adjustable with this parameter.
- `sort`: Sorts items in a resource collection returned in a response.
- `filter`: Filters items in a resource collection to return a subset based on parameter values.
- `total`: Total number of resources returned.
- `count`: Number of resources on the current page, modifiable using the `limit` parameter (default is 100).


Reference: [Ember.js Guide on Query Parameters](https://guides.emberjs.com/release/routing/query-params/)