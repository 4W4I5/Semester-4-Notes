# Link Layer

## MAC & ARP (Lec 36)
- Trivia
	- MAC (Media Access Control)
		- Used locally, its the name of the 
	- ARP (Address Resolution Protocol)
		- Used to resolve MAC addresses of hosts
- ARP Table
	- Consists 
		- IP Address
		- MAC Address (usually the )
		- TTL

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
	- Filled using self-learning
		- That is, every unknown sender frame is broadcast/flooded on all interfaces
			- MAC address and interface added to the table
			- the response back to the sender is also then recorded and saved as well
			- the next time the same frame is detected it is automatically sent on its corresponding interface
		- Routers also have their own IP and hence will also have the same
			- However, note that only the interface facing the switch is known, all other interfaces away from the network are the responsibility of the router
# Network Layer
# Transport Layer
# Session Layer
# Application Layer
