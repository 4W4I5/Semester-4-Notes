Lec 29: DHCP, NAT & ICMP

DHCP 
- Ports
	- Client uses UDP port 68
	- Server uses UDP port 67
- How does a host get an IP address
	-  Used to be hardcoded by system admin
	- DHCP
- Goal
	- Allow host to dynamically obtain an ip address from network server when it joins a network
		- Allow reuse of addresses, on hold addresses when host is connected/on
		- Required use of DCHP to assign IP to new devices in the network
- Procedure
	- Host broadcasts ->  DHCP Discover
	- DHCP responds with -> DHCP Offer
	- Host -> DHCP Request
	-  -> DHCP Ack
- Example
	- Client Broadcast IP is 0.0.0.0::68
	- Server Broadcast IP is 255.255.255.255::67
	- A unique transaction ID is also assigned which is used in the DHCP discover and offer phases
	- After DHCP offer the client has both its own IP and the Client IP that can be used to communicate in the network
	- DHCP Request also uses broadcast to make sure only one DHCP IP is used by the client
	- DHCP ACK used to assure that IP is in use
		- Note this example only assigned the IP to the new device. Network information still has not been passed through