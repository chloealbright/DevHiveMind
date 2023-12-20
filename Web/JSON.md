---
tags: 
author:
  - jacgit18
Status: 
Started: 
EditDate: 
Relates:
---

we use JSON to send data since a server may use a different language 

the syntax stores and exchanges data and is just text created with JavaScript object notation which can be read in any language 

we can wrap an object in the JSON parse method or JSON stringify  

JSON stringify object -> make a request to server or db using  

Get, Post, Put or Delete 

                                                                      |      that gets JSON parse       

                                                                     \/ 

   when it get browser  JSON parse  <-  on response  JSON stringify again  

Dealing with JSON 

JSON maybe parsed by default and the scenario where you want to re parse is to reorder the keys Json.stringify(Json.parse(jsonVar)) or Json.parse(Json.stringify(jsonVar)) 

The order of JSON is preserved because JSON is a protected primitive type of string in order to alter it you need to convert it to an object that is mutable by parsing it to make it unprotected and you can manipulate it and  you can stringify to make it a string again 

JSON.parse converts it back to the object where you can mutate it 

Then you use the JSON.stringify and pass that object as Param to make it string again



## JSONP
JSONP stands for JSON with Padding. Requesting a file from another domain can cause problems, due to cross-domain policy. Requesting an external script from another domain does not have this problem. JSONP uses this advantage, and request files using the script tag instead of the XMLHttpRequest object.