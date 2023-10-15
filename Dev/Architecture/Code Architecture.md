![[Pasted image 20230418082710.jpg]]
![[Pasted image 20230418082736.png]]


Entities: encapsulate enterprise-wide critical business rules. An entity can be an object with methods or a set of data structures and functions 

Use cases: orchestrate the flow of data to and from the entities 

Controllers, Gateways, Presenters: a set of adapters that convert data from the use cases and entities format to a most convenient way, in order to pass the data to the upper level (typically the UI) 

UI, External Interfaces, DB, Web, Devices: the outermost layer of the architecture, generally composed of frameworks such as database and web frameworks. 

The dependencies between the layers must be inwards, a lower-level module should not depend on a higher level module (entities should not depend on use cases, use cases should not depend on controllers and so on, take a look at the direction of the arrows in the diagram).