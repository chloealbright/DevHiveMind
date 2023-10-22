Port binding: Your app should be self-contained and bind to a specific port  for external access. Docker enables you to expose and map container ports to host ports, allowing external access to the app through a designated port. 

Your application's code should be designed to read configuration, including port numbers, from environment variables or configuration files weather you doing this locally or in a staging 


`Expose` command in docker essentially exposes what port the container should listen on at runtime.

 >[!example] Docker port Mapping: 
```bash
docker run -p 5000:8080 --name containerName -d BaseImageName
```
The "-d" flag detaches, allowing background execution. Port 8080 or the Docker image exposed port is mapped to local port 5000 for browser access.

You can even map the same port number so image port 5000 can mapped to local port 5000

## Official Description
### Export services via port binding

Web apps are sometimes executed inside a webserver container. For example, PHP apps might run as a module inside [Apache HTTPD](http://httpd.apache.org/), or Java apps might run inside [Tomcat](http://tomcat.apache.org/).

**The twelve-factor app is completely self-contained** and does not rely on runtime injection of a webserver into the execution environment to create a web-facing service. The web app **exports HTTP as a service by binding to a port**, and listening to requests coming in on that port.

In a local development environment, the developer visits a service URL like `http://localhost:5000/` to access the service exported by their app. In deployment, a routing layer handles routing requests from a public-facing hostname to the port-bound web processes.

This is typically implemented by using [dependency declaration](https://12factor.net/dependencies) to add a webserver library to the app, such as [Tornado](http://www.tornadoweb.org/) for Python, [Thin](http://code.macournoyer.com/thin/) for Ruby, or [Jetty](http://www.eclipse.org/jetty/) for Java and other JVM-based languages. This happens entirely in _user space_, that is, within the app’s code. The contract with the execution environment is binding to a port to serve requests.

HTTP is not the only service that can be exported by port binding. Nearly any kind of server software can be run via a process binding to a port and awaiting incoming requests. Examples include [ejabberd](http://www.ejabberd.im/) (speaking [XMPP](http://xmpp.org/)), and [Redis](http://redis.io/) (speaking the [Redis protocol](http://redis.io/topics/protocol)).

Note also that the port-binding approach means that one app can become the [backing service](https://12factor.net/backing-services) for another app, by providing the URL to the backing app as a resource handle in the [config](https://12factor.net/config) for the consuming app.