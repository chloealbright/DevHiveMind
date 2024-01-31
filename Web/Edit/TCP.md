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



![[OSI Layer.gif]]



Websites are stored and hosted on servers that clients like are personal computers connect to through ISP when sending and receiving data it is broken down into packets with headers which are guided by routers to avoid confusion also known as TCP(Transmission Control Protocol) which consist of layers like application which tend to consist of HTTP, HTTPS, SMTP, FTP and other things from internet browsers then next layer is transport which has TCP and UDP and things are transferred between ports between these two layers then TCP breaks things down into packets with headers then the packets are pushed to internet layer which attaches origin and destination IP address which would eventually reach a DNS server that checks the address and match it to a URL and domain name like ".com" then it is sent to the network layer that handles mac addressing.  
  
when it comes to IP address the DNS checks IP address with URL name and domains like `.com`  
  
your computer caches DNS storing website info on your machine if you visit a site that changed IP address you can get a 404 error
