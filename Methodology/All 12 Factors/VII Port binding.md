Port binding: Your app should be self-contained and bind to a specific port  for external access. Docker enables you to expose and map container ports to host ports, allowing external access to the app through a designated port. 

Your application's code should be designed to read configuration at runtime, including port numbers, from environment variables or configuration files weather you doing this development, staging, or production environment. 


`Expose` command in docker essentially exposes what port the container should listen on at runtime.

 >[!example] Docker port Mapping: 
```bash
docker run -p 5000:8080 --name containerName -d BaseImageName
```
The "-d" flag detaches, allowing background execution. Port 8080 or the Docker image exposed port is mapped to local port 5000 for browser access.

You can even map the same port number so image port 5000 can mapped to local port 5000

## Port binding In-Depth
Port binding is a fundamental networking concept used to associate a network application or service with a specific port number on a device's network interface. The process of port binding allows the application to listen for incoming network connections on that port. When a client device wants to communicate with the application, it sends data packets to the bound port, enabling the application to receive and process the data.

## Purpose of Port Binding
Port binding is necessary because multiple applications or services may be running on a device simultaneously, all of which may require network communication. To differentiate between these applications and ensure that the correct data is sent to the intended recipient, each application must be associated with a specific port.


## Official 12 Factor App Description
### Export services via port binding

Web apps are sometimes executed inside a webserver container. For example, PHP apps might run as a module inside [Apache HTTPD](http://httpd.apache.org/), or Java apps might run inside [Tomcat](http://tomcat.apache.org/).

**The twelve-factor app is completely self-contained** and does not rely on runtime injection of a webserver into the execution environment to create a web-facing service. The web app **exports HTTP as a service by binding to a port**, and listening to requests coming in on that port.

In a local development environment, the developer visits a service URL like `http://localhost:5000/` to access the service exported by their app. In deployment, a routing layer handles routing requests from a public-facing hostname to the port-bound web processes.

This is typically implemented by using [dependency declaration](https://12factor.net/dependencies) to add a webserver library to the app, such as [Tornado](http://www.tornadoweb.org/) for Python, [Thin](http://code.macournoyer.com/thin/) for Ruby, or [Jetty](http://www.eclipse.org/jetty/) for Java and other JVM-based languages. This happens entirely in _user space_, that is, within the app’s code. The contract with the execution environment is binding to a port to serve requests.

HTTP is not the only service that can be exported by port binding. Nearly any kind of server software can be run via a process binding to a port and awaiting incoming requests. Examples include [ejabberd](http://www.ejabberd.im/) (speaking [XMPP](http://xmpp.org/)), and [Redis](http://redis.io/) (speaking the [Redis protocol](http://redis.io/topics/protocol)).

Note also that the port-binding approach means that one app can become the [backing service](https://12factor.net/backing-services) for another app, by providing the URL to the backing app as a resource handle in the [config](https://12factor.net/config) for the consuming app.



## Server-side Port Binding: 

In server applications, the port binding process typically involves the following steps:

1. Creating a socket: A socket is a software abstraction that represents the communication endpoint. It allows the application to send and receive data over the network. The server application creates a socket and specifies the transport protocol it wants to use (e.g., TCP or UDP) and the IP address to which the socket should be bound.

2. Binding the socket to a port: After creating the socket, the server application binds it to a specific port number. The combination of the IP address and port number uniquely identifies the server application's network endpoint.

3. Listening for incoming connections: Once the socket is bound to a port, the server application starts listening for incoming connections on that port. It waits for client devices to initiate a connection to the bound port.
    
4. Accepting incoming connections: When a client device establishes a connection to the bound port, the server application accepts the incoming connection, and a new socket is created to handle the communication with that specific client.
  
## Client-side Port Binding: 

In client applications, port binding is typically handled by the operating system rather than the application itself. When a client wants to establish a connection to a server, it specifies the server's IP address and the server's port number in the connection request. The operating system then assigns an available local port as the source port for the client-side of the connection.

The client's operating system handles the actual binding of the local port to the client application. It also manages the dynamic assignment of local ports, ensuring that no port conflicts occur between multiple outgoing connections.


## Dynamic Port Allocation:
In client-server communication, the server is usually bound to a well-known or registered port (e.g., HTTP on port 80). On the client side, when an application initiates a connection to the server, the operating system assigns a dynamically available local port as the source port for the client application. This dynamic port allocation allows multiple clients on the same device to communicate with the server concurrently without conflicting port numbers.
