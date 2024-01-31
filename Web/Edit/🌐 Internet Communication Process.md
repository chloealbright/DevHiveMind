---
tags: 
author:
  - jacgit18
Comments: 
Status: Refinement
Started: 
EditDate: 
Relates:
---
![[Protocol.gif]]

#### Website Hosting and Servers
   - Websites are hosted on servers.
   - Clients (like personal computers) connect to these servers through ISPs (Internet Service Providers).

#### Data Transmission in Packets
   - Data is broken down into packets with headers for efficient transmission.
   - These packets are guided by routers to avoid confusion.

#### Transmission Control Protocol (TCP) Layers
   - **Application Layer:**
     - Includes protocols like HTTP, HTTPS, SMTP, FTP used by internet browsers.
   - **Transport Layer:**
     - Houses TCP and UDP, facilitating communication between ports.

#### TCP Breaks Down Data
   - TCP breaks down data into packets with headers for reliable and ordered delivery.

#### Internet Layer
   - Attaches origin and destination IP addresses to packets.

#### DNS Resolution
   - When data reaches the internet layer, it may go through DNS (Domain Name System) resolution.
   - DNS checks the URL and domain names (like ".com") and matches them to IP addresses.

#### Network Layer and MAC Addressing
   - The network layer handles MAC (Media Access Control) addressing.

#### IP Address and DNS Caching
   - DNS checks the IP address associated with a URL.
   - Computers cache DNS information locally for quick retrieval.
   - If a site changes its IP address, accessing it may result in a 404 error due to outdated DNS information.

 The internet communication process involves the efficient transmission of data in packets, guided by various protocols and layers, with DNS playing a crucial role in matching URLs to IP addresses. Local caching helps improve the speed of accessing frequently visited websites, but outdated information can lead to errors. 



![[Network Protocols.gif]]



![[OSI Layer.jpg]]
<mark style="background: #BBFABBA6;">7 user levels with certain protocols are used  and data is created to be sent or is opened after received </mark>

<mark style="background: #BBFABBA6;">6 data is formatted and encryption is handled here </mark>

<mark style="background: #BBFABBA6;">5 handles if a connection is on or off </mark>

<mark style="background: #ABF7F7A6;">4 transport layer adds source and destination for ports and we use either udp or tcp </mark>

<mark style="background: #ABF7F7A6;">3 this layer  handles routing the source and destination are added and routers are used </mark>

<mark style="background: #FFB86CA6;">2 physical address are assigned to the data for the source and destination mac address and switches are used here </mark>

<mark style="background: #FFB86CA6;">1 is like the Ethernet   </mark>


![[OSI Layer.gif]]



HTTP, a stateless application-level request/response protocol, utilizes extensible semantics and self-descriptive message payloads for flexible interaction with network-based hypertext information systems. It operates through message exchange over a reliable transport or session-layer "connection." While state management mechanisms like cookies exist in HTTP, they facilitate session management on the server side without fundamentally rendering HTTP stateful.


Hypertext Transfer Protocol Secure is an extension of the Hypertext Transfer Protocol. It is used for secure communication over a computer network, and is widely used on the Internet. In HTTPS, the communication protocol is encrypted using Transport Layer Security or, formerly, Secure Sockets Layer.

The Simple Mail Transfer Protocol is an internet standard communication protocol for electronic mail transmission. Mail servers and other message transfer agents use SMTP to send and receive mail messages


The File Transfer Protocol is a standard communication protocol used for the transfer of computer files from a server to a client on a computer network. FTP is built on a client–server model architecture using separate control and data connections between the client and the server.




The headers and body are completely different 

You can create a request and response directly using the Request() and Response() constructors, but it's uncommon to do this directly. Instead, these are more likely to be created as results of other API actions using the Fetch Interfaces like fetch() 

Within CRUD  

we typically POST request on the front-end > and Get request on the back-end 

if data is already created you do a GET on front-end at the endpoint and on the back-end the query action is down at whatever endpoint you defined