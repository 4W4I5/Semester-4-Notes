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
## IP Addressing (Lec 27)
## IP Subnetting (Lec 28)
## NAT & ICMP (Lec 29)
## Link State & Distance Vector Routing(Lec 30 & 31)
- Trivia
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
		- Code: (agar smjh gaye toh guru ho)
			- Start the loop by using direct costs of neighbors otherwise theyre all infinity
			- find nodeNew that isnt in last visited set and is also the lowest D(nodeNew)
			- update D(nodeNew) w the following formula
				- min of (D(prevNode), D(nodeNew) + cost(prevNode, newNode))
			- FUCK IT, doing by hand
	- Bellman-Ford Algorithm
## Hierarchical Routing (Lec 32)
## RIP & OSPF (Lec 33)

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

