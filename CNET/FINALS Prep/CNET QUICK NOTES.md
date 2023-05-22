# Link Layer

## MAC & ARP (Lec 36)
- Trivia
	- MAC (Media Access Control)
		- Used locally, its the name of the interface
		- First half is vendor info, Second half is unique identifier
	- ARP (Address Resolution Protocol)
		- Used to resolve MAC addresses of hosts/Map an IP address to a MAC address
		- Usually if the IP/MAC entry isnt present then a broadcast is sent
			- Lookup using IP
		- usually used for IPv4
- ARP Table NOTE::Does not contain the Interface, thats on switch table
	- Consists 
		- IP Address of the device
		- MAC Address of the device
		- TTL for the entry in the table

---

## Ethernet & Switches (Lec 37)
- Trivia 
	- Ethernet
		- is cheap
		- widely used LAN tech
		- simple and fast
		- no handshakes
		- has a unslotted CSMA/CD binary backoff MAC protocol
			- IG this means its got collision detection
		- no ACKs/NACKs
		- multiple physical media of transmission
	- Switch
		- Link layer device (obvs)
		- store & forward frames
			- selectively forward frame to one or more outgoing links
		- transparent
			- hosts are unwary of switches in the network
		- plug n play, self learning
			- builds a switch table to forward to the correct host
				- done by broadcasting the same packet to everyone, store senders mac address and then get the receivers mac address when they reply back. 
		- buffer packets
		- full duplex connections
		- witching, each connection can send to another host without collisions
		- Forwards & Filters
			- Uses a switch table
			- Filtering is where the switch determines to drop the packet or forward it to the host its meant for
			- Forwarding is where the switch determines the host to send the frame to and sends it
		- Router VS Switch
			- Both are Store&Forward
				- They examine their respective layers i.e a switch will examine the link layer and the router will examine the network layer
			- Both use forwarding tables
				- Routers compute theirs using routing algos, IP addresses while switches use self-learning, broadcasts
	- Quiz @ end of slides
		- What is binary (exponential) backoff and what problem does it solve?
			- Collision detection and congestion, introduces random waiting periods for both senders when they detect a collision.
			- If another collision is detected after waiting i.e, both senders picked the same integer for wait time then the randomized waiting interval is doubled
		- How would a host know the IP of the first hop router?
			- This would be done....(Answer later yaad se)
			- ARP broadcast on FF-FF-FF-FF-FF-FF w/ B's IP address which would give the IP and then the mac as well 
- Ethernet Topologies
	- Bus
	- Star
- Ethernet Frame Structure
	- PREAMBLE
		- 7 Bytes with 10101010
	- SFD 
		- A single Byte (10101011) sent after PREAMBLE
		- Indicates start of frame
	- DEST. ADDR (6 Bytes)
	- SRC. ADDR (6 Bytes)
	- TYPE (2 Bytes)
		- IPv4/IPv6/AT&T
	- PAYLOAD(DATA)
	- FCS (4 Bytes)
		- CRC checksum
- Switch Table
	- Contains entries for some but not always all hosts and routers on a LAN
		- Entry of sender MAC address
		- Time of sending 
		- Interface the frame was received on 
	- Maps MAC to an interface/port
	- Filled using self-learning
		- That is, every unknown sender frame is broadcast/flooded on all interfaces
			- MAC address and interface added to the table
			- the response back to the sender is also then recorded and saved as well
			- the next time the same frame is detected it is automatically sent on its corresponding interface
		- Routers also have their own IP and hence will also have the same
			- However, note that only the interface facing the switch is known, all other interfaces away from the network are the responsibility of the router

---

# Network Layer

## Network Layer Principles (Lec 25)
## IP Datagram (Lec 26)
- Trivia
	- IP HEADER
		- 4 bits for version
		- 4 for header len
		- 8 for service
		- 16 for packet length
		- 16 for identifier
		- 3 for flags and 13 for frag offset
		- 8 for TTL
		- 8 for upper layer protocol
		- 16 for checksum
		- 32 for src and dest IP
		- payload
		- 20 Bytes of overhead for TCP header and then another 20 for IP overhead
	- Max Transmission Unit
		- Length of largest frame sent over a link
		- if larger than MTU
			- Packet is fragmented
	- IPv6 doesnt have fragmentation
		- Causes complexity at the router
		- can also be used to DOS
- IP Fragmentation
	- Components
		- ID, random for each og full size packet. kept the same for fragmented packets from original
		- Flags, first bit is reserved. other two are Dont Frag and More Frag flags 
			- DF = 1, packet will be dropped if over MTU
			- MF = 1, more fragments, 0 if not 
				- Last frag MF is set to 0 others are 1
		- Frag Offset
			- work in octets (base 8)
## IP Addressing (Lec 27)
- Trivia
	- Talks about IPv4
	- dotted decimal notation i.e 192.168.1.1
	- conversion to binary
	- networkID + hostID bits
	- CIDR
		- fixed bits denoted by /x
		- 192.168.1.1/24 means there are 24 fixed bits
			- it also means this is a class C network
	- Address class
		- OLD WAY had either 0, 10, or 110 at the start of an IP address to determine its class respectively from A to C
		- also these classes have ranges
			- CLASS A = 1 - 126
			- CLASS B = 128 - 191
			- CLASS C = 192 - 223
## IP Subnetting (Lec 28)
- already know this lol
- Just remember that u are supposed to iterate thru subnet bits 
- subnet bits are derived from host bits
- subnet mask is made up of network and host bits
- subnet bits are used to extend the number of networks available within a IP range
## NAT & ICMP (Lec 29)
- Trivia 
	- NAT Network address translation
		- made to cater with growing pains of adapting IPv6 
		- one single public IP address is used to map an internal network
		- Controversial
			- Misuse of port numbers (meant for addressing processes not hosts)
			- Routers are meant to process upto the network layer
			- end to end policy violated
			- problematic for P2P
	- ICMP Internet Control Message Protocol
		- Made to address limitation of data loss within the transport layer
		- Error-reporting protocol
		- ICMP messages are carried in IP datagrams
			- Type, Code + 8 bytes of IP w the error
			- Imagine tracert reporting that a particular router is down
			- Header size of 8 bytes
- NAT
	- works by modifying the datagrams leaving the router to have a single source IP (the public IP) but varied source port numbers
	- internally a NAT table is used to map a random port number to a host interface and this is used to send packets to and fro from a NAT network
## Link State & Distance Vector Routing(Lec 30 & 31)
- Trivia
	- Comparison b/w the two
		- Complexity
			- LinkState: updates are sent to all
			- DistanceVector: exchange b/w neighbors only
		- Convergence
			- LinkState: pata nai bhai its some O(n) stuff
			- DistanceVector: might count to infinity, routing loops
		- Malfunction?
			- LinkState: Node might advertise incorrect link cost, only computes its own table
			- DistanceVector: Node might advertise incorrect path cost, own nodes table is used by others, error will propagate thru the network
	- Link State
		- Find directly connected neighbors only using a Link-State Packet
		- Floods to all neighbors who store the LSP in database
		- Each router determines its own cost to each destination
		- Distributed algorithm
		- Use of djikstra
	- Distance Vector 
		- Distributed = Only communicates with directly attached neighbors
		- Iterative = Self-terminating, continues until no nodes exchange info
		- Asynchronous = wtf is this "nodes need not exchange info/iterate in lock step"
- Link State Algorithm
	- Dijkstra gives end to end routes, routing tables are used to store next hop addresses
	- Each router uses the database to construct a complete map of the network topology
		- Computes least cost paths using Dijkstra and Constructs routing tables that show the destination address and next hop address
	- Working
		- Notation
			- c(x, y) => Cost of x to y. infinite if only not direct neighbor
			- D(v) => current value of cost of path from source to destination
			- p(v) => last visited node (predecessor)
			- N' => set of nodes whos are last visited (least cost walay)
		- Code: (agar smjh gaye toh guru ho) {**IGNORE THIS**}
			- Start the loop by using direct costs of neighbors otherwise theyre all infinity
			- find nodeNew that isnt in last visited set and is also the lowest D(nodeNew)
			- update D(nodeNew) w the following formula
				- min of (D(prevNode), D(nodeNew) + cost(prevNode, newNode))
			- FUCK IT, doing by hand
- Distance Vector Algorithm
		- aka bellman-ford
## Hierarchical Routing | RIP & OSPF(Lec 32 & 33)
- Trivia
	- aka Autonomous Systems (AS)
	- runs intra-AS routing protocols (RIP, OSPF, IGRP) as well
	- RIP
		- uses DV algo
		- limited to max hops of 15
		- DV sent every 30 sec w neighbors
		- Costs are from src to dest
		- Hop means number of subnets traversed
		- if no ad heard after 180, link is dead and new ad is to be sent
		- managed by application level by route-d
			- uses UDP
		- only one path
	- OSPF
		- uses LS algo
		- link costs are setup by admin to 1
		- link weights are inversely proportional to link capacity to discourage traffic from using low bandwidth links
		- AD carries one entry per neighbor
			- Flooded to entire AS
			- uses either TCP/UDP
			- LS is broadcast periodically or upon every LS change
		- Must implement its own RDT and LS broadcast features
			- protocol num is 89
		- multiple same cost paths are allowed
		- can be structured hierarchically
	- Hierarchical OSPF (needs refinement)
		- two-level hierarchy
			- local area, backbone
			- LS AD only in area
		- area border routers
			- summarize distances to nets in own area, ad to other area border routers
		- backbone routers
			- run ospf routing to limited to backbone
		- boundary routers
			- connect to other AS's
		- hot potato routing 
			- choose the gateway that has the smallest lead cost
---

# Transport Layer

## Transport Layer Services (Lec 11 but not)
## UDP (Lec 14)
## RDT - Reliable Data Transfer (Lec 15)
## RDT - Reliable Data Transfer (Lec 16)
## GoBackN & Selective Repeat (Lec 17)
## TCP Segment Structure (Lec 18)
## TCP Reliable Data Transfer (RDT) (Lec 19)
## TCP Flow control (Lec 20)
## TCP Congestion control (Lec 22 & 23)

---

# Application Layer
## Application Layer Principles (Lec 07)
## Web & HTTP (Lec 08)
## WebCache & FTP (Lec 09)
## DNS (Lec 11)
## DHCP (Lec 29)
- Trivia
	- Auto assignment of IP to hosts
	- PORT=67 for server | 68 for client over UDP 
	- Shares gateway, DNS, next hop router and IP address of host
- Working (all are broadcasts)
	- DHCP discover
		- source IP = 0.0.0.0
		- destination IP = 255.255.255.255
	- DHCP offer
		- source IP = 1.1.1.254/24
		- destination IP = 255.255.255.255 (offer is also broadcast to all)
		- Server sends available IP addresses and options
	- DHCP request 
		- Requests IP from server after selecting from options
		- Basically check if the network has that IP already assigned by using the offered IP and ARP broadcasting
	- DHCP ACK
		- DHCP agrees final comms and ack the IP request
