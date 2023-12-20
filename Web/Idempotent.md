---
tags: 
author:
  - jacgit18
Status: 
Started: 
EditDate: 
Relates:
---


## idempotency

- ### **Idempotence** is the property of certain operations that they can be applied multiple times without changing the result
- ### Request failures happen. Provide users a safe way to retry requests

- ### Example:
```javascript
POST /BankAccount/AddFunds
{'value': 1000, 'token': 'TX123'}
```




An HTTP method is idempotent if an identical request can be made once or several times in a row with the same effect while leaving the server in the same state. In other words, an idempotent method should not have any side effects (except for keeping statistics). Implemented correctly, the GET, HEAD, PUT, and DELETE methods are idempotent, but not the POST method. All safe methods are also idempotent. 

To be idempotent, only the actual back-end state of the server is considered, the status code returned by each request may differ: the first call of a DELETE will likely return a 200, while successive ones will likely return a 404. Another implication of DELETE being idempotent is that developers should not implement RESTful APIs with a delete last entry functionality using the DELETE method. 

idempotency and safety 

PUT & DELETE have idempotency but aren't safe. 

while POST & PATCH don't have idempotency and aren't safe 

Post method always results in a server state change. If the POST method was idempotent, everything sent and accepted to or from the web server would already have to exist on the server in some form to respond with the same codes and value response. For that reason, POST cannot be idempotent. 

Generally – not necessarily – PUT APIs are used to update the resource state. If you invoke a PUT API N times, the very first request will update the resource; the other N-1 requests will just overwrite the same resource state again and again – effectively not changing anything. Hence, PUT is idempotent. 

When you invoke N similar DELETE requests, the first request will delete the resource and the response will be 200 (OK) or 204 (No Content). 

Other N-1 requests will return 404 (Not Found). 

Clearly, the response is different from the first request, but there is no change of state for any resource on the server-side because the original resource is already deleted. 

So, DELETE is idempotent. 

OPTIONS, GET, & HEAD have idempotency and are safe