---
tags: 
author:
  - jacgit18
Status: 
Started: 
EditDate: 
Relates:
---
### When to Use JWT (JSON Web Tokens)

#### Authentication
After a successful login, an ID token (JWT) is returned, adhering to OpenID Connect specifications.

#### Authorization
JWTs are commonly used for secure authorization. Subsequent requests include the JWT, granting access to permitted routes, services, and resources. JWTs are especially popular in Single Sign-On due to their efficiency and cross-domain compatibility.

#### Information Exchange
Securely transmit information between parties using signed JWTs. The use of public/private key pairs ensures the authenticity of senders, and the signature verifies content integrity.

### When to Use Custom HTTP Methods

Avoid nonstandard custom HTTP methods to ensure compatibility with off-the-shelf software. Instead, design a controller resource for abstract operations and use the standard HTTP method POST.

- **WebDAV Methods**: WebDAV defines methods like PROPFIND, PROPPATCH, MOVE, LOCK, UNLOCK for distributed authoring and versioning.

- **Other Examples**: PATCH for partial updates, MERGE for resource merging.

- **Considerations**: Nonstandard methods are treated similarly to POST by proxies, caches, and HTTP libraries. Idempotency and safety guarantees must be explicitly provided by the server. Use custom methods only when interoperability is not a concern.