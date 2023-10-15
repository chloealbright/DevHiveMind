By repurposing the web application’s controller paradigm, many of today’s frameworks provide support for using URI templates to route inbound client requests to handler-style methods or functions. In recognition of the fact that developers don’t want to code web page templates to format their REST API’s data, most of the frameworks offer built-in XML and JSON-based serialization and deserialization of the server’s objects to and from an HTTP message’s body. 

API template 

A named REST API containing a list of resource templates, a list of schemas, and a list of “global” API-level state facts. 

Resource template 

A resource template is a path segment within a REST API’s hierarchical resource model. It has an associated URI template and set of possible schemas that client’s may bind to, at request time, by using media type negotiation. The schemas that are assigned to a resource template must extend one of the four base schemas associated with the resource archetypes: Document, Collection, Store, and Controller. 

Schema 

Schemas are like classes or tables: they are a web application’s structured types. They allow forms (instances consisting of fields and links) to be molded in their image and used to carry the state of a resource. 

Format 

Formats, like HTML, XML, and JSON, are often used on their own to declare the type associated with the content of a message’s body. WRML elevates formats to first-class structures that can provide links to downloadable code to help programs exchange their encoded data. 

Link relation 

A link relation is a concept borrowed from HTML that adds semantics to links. WRML expands on the idea by also documenting a link’s acceptable input media types and possible output media types.