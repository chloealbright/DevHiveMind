---
tags: 
author:
  - jacgit18
Status: 
Started: 
EditDate: 
Relates:
---
CONNECT -> method starts two-way communications with the requested resource. It can be used to open a tunnel. For example, the CONNECT method can be used to access websites that use SSL (HTTPS). The client asks an HTTP Proxy server to tunnel the TCP connection to the desired destination. The server then proceeds to make the connection on behalf of the client. Once the connection has been established by the server, the Proxy server continues to proxy the TCP stream to and from the client. 

OPTIONS -> method requests permitted communication options for a given URL or server. A client can specify a URL with this method, or an asterisk (*) to refer to the entire server. 

sending OPTIONS with api URL gives you info on all api allowed functionality which is useful if you don't have documentation  

TRACE -> method performs a message loop-back test along the path to the target resource, providing a useful debugging mechanism.