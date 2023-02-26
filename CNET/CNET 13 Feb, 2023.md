SLIDES: Lecture 7, Application Layer Principles

### Application Layer
- Supports networking between Applications
- Allows Applications to transfer data over the internet
- Use of common protocols
	- DNS
	- DHCP
	- SMTP
	- FTP
	- HTTP
---
###### Creating a network app
- Runs on multiple end systems
- Communicates over the internet

###### Application-Layer Protocol Defines
- Types of messages Exchanged
	- Request
	- Response
- Message Syntax
	- What fields in messages and how fields are delaminated (deserialized)
- Message Semantics
	- Meaning of information in fields
- Rules for when and how process send and respond to messages
- Open Protocols
	- Defined in RFCs, a specification sheet
	- Allows for interoperability
		- HTTP, SMTP
- Proprietary Protocols
	- A custom made protocol made for a particular system
		- Skype

#### Client-Server
- Whenever a system inits a request, its known as a client
	- Usually temporarily connected, only for the need of the service
	- Has a dynamic IP address
	- cannot communicate directly with other clients
	- Clients increase = Demand more resources
- The system responding to the request is known as a server
	- Usually assigned a static IP
	- Always-On (Always powered on)
	- Used in data centers, for scaling
#### Peer-Peer 
- Concept of torrenting
	- CS model used at first to get the torrent file
	- List of seeders, leechers found
	- Downloading from seeders
	- leechers are the people downloading
		- They usually download random parts of the file itself, if the file goes down then the leechers share the downloaded files
	- Architecture
		- No Always-On Server
			- Theres no concept of a server
		- End systems directly communicate
			- Downloading is essentially a CS model
		- Scaleable
			- No central entity involved
			- New peers bring new service capacity, as well as new service demands
		- Peers request service from other peers and provide service in return to other peers
		- Always Connected, Change IP Addresses
###### Process Communications
- Some kind of tab or whatever, a process in task manager
	- Program running within a host
	- Within the same host, two processes communicate using inter-process communication, defined by OS
	- Processes in different hosts, communicate by exchange of messages

### Sockets
- A port and IP stored in memory. 
- Used to identify the process with the help of IP and Port
	- Scope ki baat ha, including the machine with the application
### What does a network APP expect?
- Data integrity
	- Expected of transport layer
	- Require 100% reliable data transfer
	- Some can tolerate some amount of data loss
- Timing
	- Expected of transport layer
	- Low latency
- Throughput
	- Actual speed
	- Bandwidth
- Security
	- Encryption, but not much to be expected of it

#### Why TCP/UDP
- ### TCP
	- Reliable Transport
	- Flow Control
		- Sender wont overwhelm receiver
	- Congestion Control
		- Throttle sender when network is overloaded
	- Connection-Oriented
		- Setup required b/w client and server processes
	- Does not however provide
		- Timing
		- Minimum throughput guarantee
		- Security
- ### UDP
	- Unreliable
	- Does not provide
		- Reliability
		- Flow Control
		- Congestion Control
		- Timing
		- Throughput guarantee
		- security
		- connection setup
	- Used cause these things take time and overhead, if a packet has to be sent as fast as possible UDP is the way

##### Securing TCP/UDP
- As is the connection is not encrypted
	- Everything is sent in cleartext
- Use of SSL
	- Located in between application and transport layer
	- Used at the application layer via an SSL library

---