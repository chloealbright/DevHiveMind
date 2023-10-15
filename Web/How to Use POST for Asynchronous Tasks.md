HTTP is a synchronous and stateless protocol. When a client submits a request to a server, the client expects an answer, whether the answer is a success or a failure. But this does not mean that the server must finish processing the request before returning a response. For example, in a banking application, when you initiate an account transfer, the transfer may not happen until the next business day, and the client may be required to check for the status later. This recipe discusses how to use this method to process requests asynchronously. 

On receiving a POST request, create a new resource, and return status code 202 (Accepted) with a representation of the new resource. The purpose of this resource is to let a client track the status of the asynchronous task. Design this resource such that its representation includes the current status of the request and related information such as a time estimate. 

When the client submits a GET request to the task resource, do one of the following depending on the current status of the request: 

Still processing 

Return response code 200 (OK) and a representation of the task resource with the current status. 

On successful completion 

Return response code 303 (See Other) and a Location header containing a URI of a resource that shows the outcome of the task. 

On task failure 

Return response code 200 (OK) with a representation of the task resource informing that the resource creation has failed. Clients will need to read the body of the representation to find the reason for failure. 

Consider an image-processing web service offering services such as file conversions, optical character recognition, image cleanup, etc. To use this service, clients upload raw images. Depending on the nature and size of images uploaded and the current server load, the server may take from a few seconds up to several hours to process each image. Upon completion, client applications can view/download processed images. 

Let’s start with the client submitting a POST request to initiate a new image-processing task: 

# Request 

POST /images/tasks HTTP/1.1 

Host: www.example.org 

Content-Type: multipart/related; boundary=xyz 

--xyz 

Content-Type: application/xml;charset=UTF-8 

... 

--xyz 

Content-Type: image/png 

... 

--xyz--  

In this example, the client uses a multipart message, with the first part containing an XML document describing the kind of image-processing operations the server needs to perform and the second part containing the image to be processed. 

Upon ensuring that the contents are valid and that the given image-processing request can be honored, let the server create a new task resource: 

# Response 

HTTP/1.1 202 Accepted   

Content-Type: application/xml;charset=UTF-8 

Content-Location: http://www.example.org/images/task/1 

Date: Sun, 13 Sep 2009 01:49:27 GMT 

<status xmlns:atom="http://www.w3.org/2005/Atom"> 

  <state>pending</state> 

  <atom:link href="http://www.example.org/images/task/1" rel="self"/> 

  <message xml:lang="en">Your request has been accepted for processing.</message> 

  <ping-after>2009-09-13T01:59:27Z</ping-after>  

</status>  

Response code indicating that the server accepted the request for processing 

A hint to check for the status at a later time 

The client can subsequently send a GET request to this task resource. If the server is still processing the task, it can return the following response: 

# Request 

GET /images/task/1 HTTP/1.1 

Host: www.example.org 

# Response 

HTTP/1.1 200 OK 

Content-Type: application/xml;charset=UTF-8 

<status xmlns:atom="http://www.w3.org/2005/Atom"> 

  <state>pending</state> 

  <atom:link href="http://www.example.org/images/task/1" rel="self"/> 

  <message xml:lang="en">Your request is currently being processed.</message> 

  <ping-after>2009-09-13T02:09:27Z</ping-after> 

</status>  

After the server successfully completes image processing, it can redirect the client to the result. In this example, the result is a new image resource: 

# Request 

GET /images/task/1 HTTP/1.1 

Host: www.example.org 

# Response 

HTTP/1.1 303 See Other   

Location: http://www.example.org/images/1 

Content-Location: http://www.example.org/images/task/1 

<status xmlns:atom="http://www.w3.org/2005/Atom"> 

  <state>done</state> 

  <atom:link href="http://www.example.org/images/task/1" rel="self"/> 

  <message xml:lang="en">Your request has been processed.</message> 

</status>  

This representation informs the client that it needs to refer to http://www.example.org/images/1 for the result. If, on the other hand, the server fails to complete the task, it can return the following: 

# Request 

GET /images/task/1 HTTP/1.1 

Host: www.example.org 

# Response 

HTTP/1.1 200 OK 

Content-Type: application/xml;charset=UTF-8 

<status xmlns:atom="http://www.w3.org/2005/Atom"> 

  <state>failed</state> 

  <atom:link href="http://www.example.org/images/task/1" rel="self"/> 

  <message xml:lang="en">Failed to complete the request.</message> 

  <detail xml:lang="en">Invalid image format.</detail> 

  <completed>2009-09-13T02:10:00Z</completed> 

</status>