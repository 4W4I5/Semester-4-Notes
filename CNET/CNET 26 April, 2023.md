Lec 29: DHCP, NAT & ICMP

DHCP 
- How does a host get an IP address
	-  Used to be hardcoded by system admin
	- DHCP
- Goal
	- Allow host to dynamically obtain an ip address from network server when it joins a network
		- Allow resuse of addresses, on hold addresses when host is connected/on
		- Required use of DCHP to assign IP to new devices in the network
- Procedure
	- Host broadcasts ->  DHCP Discover
	- DHCP responds with -> DHCP Offer
	- Host 