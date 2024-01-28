---
tags: 
author:
  - jacgit18
Status: 
Started: 
EditDate: 
Relates:
---
Delete –> DELETE - request method deletes the specified resource. 

Delete means delete-if-exists: If the resource doesn’t exist, fail this operation. If two valid delete operations arrive at once, delete the resource, and allow both to pass. 


## How to Use DELETE for Asynchronous Deletion

This recipe outlines an approach for using DELETE for asynchronous tasks. This recipe is appropriate when resource deletion takes a significant amount of time for cleanup and archival tasks in the backend. 

On receiving a DELETE request, create a new resource, and return 202 (Accepted) with the response containing a representation of this resource. Let the client use this resource to track the status. When the client submits a GET request to the task resource, return response code 200 (OK) with a representation showing the current status of the task. 

Supporting asynchronous resource deletion is even simpler than creating or updating resources. The following sequence of steps illustrates an implementation of this recipe: 

To begin, a client submits a request to delete a resource. 

DELETE /users/john HTTP/1.1 

Host: www.example.org  

The server creates a new resource and returns a representation indicating the status of the task. 

HTTP/1.1 202 Accepted 

Content-Type: application/xml;charset=UTF-8 

<status xmlns:atom="http://www.w3.org/2005/Atom"> 

  <state>pending</state> 

  <atom:link href="http://www.example.org/task/1" rel="self"/> 

  <message xml:lang="en">Your request has been accepted for processing.</message> 

  <created>2009-07-05T03:10:00Z</ping> 

  <ping-after>2009-07-05T03:15:00Z</ping-after> 

</status>  

The client can query the URI http://www.example.org/task/1 to learn the status of the request. 

You can use the same approach for asynchronously updating a resource via the PUT method.



Other METHOD