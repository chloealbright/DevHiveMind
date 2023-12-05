![[OSI Layer.jpg]]

A suite of protocols for communication between computers, specifying standards for transmitting data over networks and used as the basis for standard Internet protocols that follow along the OSI model. 

<mark style="background: #BBFABBA6;">7 user levels with certain protocols are used  and data is created to be sent or is opened after received </mark>

The Hypertext Transfer Protocol (HTTP) is a stateless application-level request/response protocol that uses extensible semantics and self-descriptive message payloads for flexible interaction with network-based hypertext information systems. 

HTTP is a stateless request/response protocol that operates by exchanging messages across a reliable transport- or session-layer "connection". 

some mechanisms for state management in HTTP, such as cookies, allowing session management on server side (but it doesn't make HTTP stateful in any ways). 

The DNS server also operates on the application layer 

<mark style="background: #BBFABBA6;">6 data is formatted and encryption is handled here </mark>

<mark style="background: #BBFABBA6;">5 handles if a connection is on or off </mark>

<mark style="background: #ABF7F7A6;">4 transport layer adds source and destination for ports and we use either udp or tcp </mark>

<mark style="background: #ABF7F7A6;">3 this layer  handles routing the source and destination are added and routers are used </mark>

<mark style="background: #FFB86CA6;">2 physical address are assigned to the data for the source and destination mac address and switches are used here </mark>

<mark style="background: #FFB86CA6;">1 is like the Ethernet   </mark>




we go from  

        App(Client) -> presentation -> Session -> Transport -> Network -> Data -> Phys 

                                                                                                                                 /  \ 

                                                                         | send Request & receives Response  | 

                                                                                                                                  \ / 
       App(DNS) <- presentation <- Session <- Transport <- Network <- Data <- Phys 

appending different info that will be passed through the physical the next physical on the other side until it reaches their own application layer