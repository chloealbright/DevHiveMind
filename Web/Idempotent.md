---
tags: 
author:
  - jacgit18
Comments: This documentation discusses what idempotency is.
Status: 
Started: 
EditDate: 
Relates:
---
**Idempotence** refers to the characteristic of certain operations that can be applied multiple times without altering the outcome.

In handling request failures, ensure users have a secure means to retry requests.

### Example:
```javascript
POST /BankAccount/AddFunds
{'value': 1000, 'token': 'TX123'}
```

An HTTP method is idempotent when an identical request can be made successively with the same effect, maintaining the server's state. Idempotent methods, such as GET, HEAD, PUT, and DELETE, should not produce side effects except for statistical tracking. Although the status code may differ, the back-end state remains unchanged.

PUT and DELETE are idempotent but not safe, whereas POST and PATCH lack idempotency and safety. The POST method induces a server state change, preventing it from being idempotent. In contrast, PUT APIs typically update resource states and exhibit idempotence, while DELETE is idempotent, resulting in a resource deletion with subsequent requests returning a 404 (Not Found) status. ^43c387

OPTIONS, GET, and HEAD are both idempotent and safe.



