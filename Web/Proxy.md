
In computer networking, a proxy server is a server application that acts as an intermediary between a client requesting a resource and the server providing that resource.  

## 1\. Proxies

Proxies are intermediary servers that stand between clients and other servers. They play a critical role in enhancing performance, security, and reliability in various network scenarios.


```typescript
import * as http from 'http';
import * as httpProxy from 'http-proxy';

const proxy = httpProxy.createProxyServer({});

const server = http.createServer((req, res) => {
  console.log(`Proxying request to: ${req.url}`);

  // Proxy the request to the target server
  proxy.web(req, res, { target: 'http://example.com' });
});

const PORT = 3000;

server.listen(PORT, () => {
  console.log(`Proxy Server listening on port ${PORT}`);
});
```

This example uses the `http-proxy` library to create a simple HTTP proxy server. Requests to the proxy server are forwarded to `http://example.com`. You can modify the target URL or add more advanced features based on your specific use case.


## 1.1 Forward Proxy

A forward proxy is a server that acts on behalf of clients to make requests to other servers. Forward proxies can be used for various purposes, such as providing anonymity, enforcing security policies, and caching content.


```typescript
import * as http from 'http';
import * as httpProxy from 'http-proxy';

const proxy = httpProxy.createProxyServer({});

const server = http.createServer((req, res) => {
  console.log(`Forwarding request to: ${req.url}`);

  // Proxy the request to the target server
  proxy.web(req, res, { target: req.url, changeOrigin: true });
});

const PORT = 3000;

server.listen(PORT, () => {
  console.log(`Forward Proxy Server listening on port ${PORT}`);
});
```




Yes, the line `proxy.web(req, res, { target: req.url, changeOrigin: true });` is a key part of creating a forward proxy in the example. Let me explain the significance:

- `proxy.web(req, res, { target: req.url, changeOrigin: true });`: This line utilizes the `http-proxy` library to forward the incoming HTTP request to the target specified in `req.url`. Here, `req.url` contains the target URL that the client is trying to access. The `changeOrigin: true` option modifies the `Host` header in the request to match the target, which can be crucial when forwarding requests to servers that rely on the `Host` header for proper functioning.

In the context of a forward proxy:

- **Forward Proxy:** Forwards client requests to a variety of servers on behalf of the client. The client is unaware of the target server, and the proxy handles the communication with the target server. In this example, `proxy.web` is used to forward the client's request to the specified target server based on the `req.url`.

A forward proxy is typically used to provide anonymity, content filtering, or caching for clients, as the clients make requests through the proxy, and the target servers do not see the original client IP addresses.


## 1.2 Reverse Proxy

A reverse proxy is a server that handles client requests on behalf of other servers. Reverse proxies can provide load balancing, SSL termination, and content caching, among other benefits.

![](https://miro.medium.com/v2/resize:fit:700/1*oeUPfO992X54Q15f39Nsig.png)

Forward Proxy vs Reverse Proxy








## Proxy server vs VPN 

Proxy and VPN defined. A VPN secures all your network traffic, while a proxy works on an application level. They both hide your IP address, but only a VPN redirects your internet data through an encrypted tunnel. A proxy is suitable for browsing the internet, but it's not as safe and secure as a VPN.