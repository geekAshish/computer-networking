# Computer Networking
A computer network is a system of connected devices that can exchange data and resources with each other.

Devices in a computer network use communications protocols, which are systems of rules, to transmit information over physical or wireless technologies. This allows devices to collaborate, transfer data, and access shared information, such as files, emails, and printers.

## Some examples of computer networks include:
* Internet
* Extranet 
* Darknet 
* Personal Area Network (PAN) 
* Local Area Network (LAN) 
* Metropolitan Area Network (MAN) 
* Wide Area Network (WAN) 
* Passive optical local area network (POLAN)

## Internet
The Internet is a vast network that connects computers all over the world. Through the Internet, people can share information and communicate from anywhere with an Internet connection.

# How did it start?
* ARPA : Advanced Research Projects Agency
* ARPANET: Advanced Research Projects Agency Network

world wide web

# Protocols
A protocol is a set of rules that govern how data is transmitted and received in a network. Protocols ensure that devices on a network can communicate with each other effectively and accurately

### Here are some examples of protocols:
* Transmission Control Protocol (TCP)
* Internet Protocol (IP)
* File Transfer Protocol (FTP)
* Hypertext Transfer Protocol (HTTP)
* User Datagram Protocol (UDP)
* DHCP

# PORTS
0 - 1023 (ports are reserved)
like for 
HTTP - 80

1024 - 49152
for application
mongodb - 27027
sql - 1433

remaingin you can use

# How comunication between two computer happen
1. Guided way

- Optical fiber cable
https://www.submarinecablemap.com/

2. Unguided way
bluetooth, wifi, 3G, 4G, 5G


# ############
LAN: house, office, via ethernet, wifi

MAN: accross the city

WAN: accross the country, via optical fiber cable
1. SoNET
2. frame relay

MODEM: convert digital signal to analog signal

# Togology
1. BUS
2. RING
3. STAR
4. TREE
5. MESH

# Structure of the Network

## OSI Model (Open System Interconnection Model)
There are 7 layers in the OSI model

### Application layer:
The application layer is concerned with the specific type of application itself and its standardized communication methods. For example, browsers can communicate using HyperText Transfer Protocol Secure (HTTPS), and HTTP and email clients can communicate using POP3 (Post Office Protocol version 3) and SMTP (Simple Mail Transfer Protocol).

### Presentation layer
The presentation layer is primarily concerned with the syntax of the data itself for applications to send and consume. For example, Hypertext Markup Language (HTML), JavaScipt Object Notation (JSON), and Comma Separated Values (CSV) are all modeling languages to describe the structure of data at the presentation layer. 

### Session layer
The session layer is responsible for network coordination between two separate applications in a session. A session manages the beginning and ending of a one-to-one application connection and synchronization conflicts. Network File System (NFS) and Server Message Block (SMB) are commonly used protocols at the session layer.

### Transport layer
The primary focus of the transport layer is to ensure that data packets arrive in the right order, without losses or errors, or can be seamlessly recovered if required. Flow control, along with error control, is often a focus at the transport layer. At this layer, commonly used protocols include the Transmission Control Protocol (TCP), a near-lossless connection-based protocol, and the User Datagram Protocol (UDP), a lossy connectionless protocol. TCP is commonly used where all data must be intact (e.g. file share), whereas UDP is used when retaining all packets is less critical (e.g. video streaming).

### Network layer
The network layer is concerned with concepts such as routing, forwarding, and addressing across a dispersed network or multiple connected networks of nodes or machines. The network layer may also manage flow control. Across the internet, the Internet Protocol v4 (IPv4) and IPv6 are used as the main network layer protocols.

### Data link layer
The data link layer refers to the technologies used to connect two machines across a network where the physical layer already exists. It manages data frames, which are digital signals encapsulated into data packets. Flow control and error control of data are often key focuses of the data link layer. Ethernet is an example of a standard at this level. The data link layer is often split into two sub-layers: the Media Access Control (MAC) layer and Logical Link Control (LLC) layer. 

### Physical layer
The physical layer refers to the physical communication medium and the technologies to transmit data across that medium. At its core, data communication is the transfer of digital and electronic signals through various physical channels like fiber-optic cables, copper cabling, and air. The physical layer includes standards for technologies and metrics closely related with the channels, such as Bluetooth, NFC, and data transmission speeds.


## TCP/IP Model (5 Layers)
1. Application layer
2. Transport layer
3. Network layer
4. Data link layer
5. Physical layer

# Client Server Architecture
1. Application layer
   1. User Interaction
   2. whatsapp, browser, etc
   3. where: devices
   4. Protocols
   5. cilent-server architecture

client  -->  request  --->  server
client  <--  response <---  server

# Peer to Peer Architecture
In this arch every computer treated as server and client.


# Networking devices
1. Repeater
2. Hub

Type of hub
* active hub
* passive hub

3. Bridge
Type of bridge
* Transparent bridges
* Source routing bridges

4. Switch
5. Routers
6. Gateway
7. Brouter

# Protocols
## web protocols
1.  TCP/IP
* HTTP
* DHCP
* FTP
* SMTP
* POP3 & IMAC
* SSH (IF YOU WANT TO LOGIN TO SOMEONE ELSE TERMINAL)
* vnc (for graphical controle)

2. Telnet
* port

3. UDP
stateless connection, data may be lost during the connection

# Sockets

# Ports
Ephemeral ports

# HTTP
http uses tcp
stateless protocol
http methods
cookies

# How email works?
sender SMPT server --> receiver SMPT server
POP
IMAC

# DNS (Domain Name System)
mail.google.com
sub-domain.second-level-domain.top-level-domain

* Root DNS Servers
.io      .org     (TLD)

web.io       wiki.org   (SLD)


* They are the one register TLD
https://www.icann.org/


* when you search something
first check in own computer
then ISP
then Root Server
then LTD (it'll give you the ip address)

command
dig google.com

# Transport Layer
Data transport between application layer to network layer
it's located in you device
transport layer has a multiplexer and demultiplexer

* message, file, vc --socket--> transport layer multiplexer --network--> transport layer multiplexer --socket--> message, file, vc
* and these socket have port no. and transport layer will attach these socket port no.
* data travels in packets
* This layer also take care of congestion control
* congestion control algorithms built in TCP

## checksum
when we send data to someone, checksum will also go with the data, and when the receiver got the data they create the checksum with the same algorithms and if the checksum is different then data is lost if not then receiver got the full data.

## Timers

            send data   (timer starts)    ------>      data send  
me                                                                        reveiver
                        (timer ends)      <------      yes, I got the data
and then we know our data is received


            send data   (timer starts)    ------> data not send       
me                                                                  reveiver
                        (timer expires)
and we know, our data got lost


            send data   (timer starts)       ------> data send
me                                                                        reveiver
                        (timer expires)      <------ message not send

to solve this problem we use sequence numbers

### UDP (user datagram protocol) is the tranport layer protocol
* Data may not be delivered
* Data may change
* Data may not be in order
* connection less
* UDP uses checksums

### UDP Packets
* every data pockets have your port number (source) (2 bytes)
* and receiver port number (destination) (2 bytes)
* lenth of the datagram will also added (2 bytes)
* checksum will also added (2 bytes)
total size = 2^16;

data = 2^16 - 8; [This is the size of the data in one packate that you can send]

### use cases
it's very fast
video conferenceing app
Gaming
DNS is also uses UDP

command tcpdump -c 5


# TCP (Transmission Control Protocol)
* Transport layer protocols
* Application layer sends lots of raw data TCP segment this data ---> divide in chunks, and headers, checksums
* It may also collet the data from network layer(network layer have more smaller chuncks)
* congestion contole
* Takes care of
   * when data does not arrive
   * maintains the order of the data (using sequence number)

## Feature
* connection oriented
* error controle
* congstion controle
* full duplex
* using tcp we only have two endpoints
* 1 TCP connection can only between two computers
* it will add sequence number, and acknowledgement number


## 3-Way handshake
Client                                                                           server
      ---- sync flag in header, seq no. ----->
      <---- sync flag in header, (do some maths on seq no. = no), ack number (prev seq no. + 1) ----- ack
      ack---- sync flag in header, (prev seq no. + 1), ack number ----->


# Network layer
In transport layer the data we've, is in segments.
In the network layer the data travells in the form of packets.
Data link layer have frames.


* Here we works with routers.
* forwording table is the part of routing table and theses exist inside router
* hop-by-hop routers
* Router has network address
* every packate has info about network address (source and destination) + data

192.63.2.63
network address(192.63.2)  device address(.63)
Subnet id                        hostId

who creates forwarding table (control plane)

# Control plane
1. Static Routing (not addaptive)
   * Adding manually

2. Dynamic routing
path finding algorithms
dijkstra

# Internet Protocol (IP)
It uniqually define a server, node, device.
IPv4 --> 32 bit, 4- words
IPv6 --> 128 bit

* class of IP addresses
class A    0.0.0.0      --   127.255.255.251
class B    128.0.0.0    --   191.225.225.225
class C    192.0.0.0    --   223.225.225.225
class D    224.0.0.0    --   239.225.225.225
class E    240.0.0.0    --   225.225.225.225

### subnet masking

Internet Engneering task force
https://www.ietf.org/
they assign the IP to ISP


### Reserved Addresses:
127.0.0.0/8

ex: localhost : 127.0.0.1
loopback addresses


# Packets:
header is of 20 bytes
IP version, total length, Identification number, flags, checksums, protocols, address, TTL(Time to live), etc.

After so many hopping if the package doesn't reach the destination, it'll drops.


# DHCP (Dynamic host configuration protocols)
whenever new device connect to the router, DHCP give new device a address


# IPv6
IPv6 = 2^128

cons:
* not backword compatible
* ISPs would have to sift, lot of hardware work.
* a:a:a:a:a:a:a:a
  |
  hexadecimal(16bit)


# Middle Boxes
extra devices which also intaract with the ip packets
1. Firewall ( Global internet, you trusted network)
   filter out IP packets based on various rules.
   * Address
   * Modify Packets
   * Port number
   * flags
   * protocols

Stateless firewall
Statefull firewall


# (NAT) Network Address Translation


# TCP (Data Link Layer)
Many devices connected in LAN: data link layer address (known as mac address)

device has data link layer address

cache (ARP cashes: Address resolution protocols)

frame (DLLA of sender and ip address of the destination)

* Framing
* Error Detection




