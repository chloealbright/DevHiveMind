A REST API commonly uses a response message’s entity body to help convey the state of a request message’s identified resource. REST APIs often employ a text-based format to represent a resource state as a set of meaningful fields. Today, the most commonly used text formats are XML and JSON. 

Rule: JSON should be supported for resource representation 

Rule: JSON must be well-formed 

Rule: XML and other formats may optionally be used for resource representation 

Rule: Additional envelopes must not be created 

A REST API must leverage the message “envelope” provided by HTTP. In other words, the body should contain a representation of the resource state, without any additional, transport-oriented wrappers. 

Rule: A consistent form should be used to represent errors