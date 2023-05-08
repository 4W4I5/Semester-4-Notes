Lecture 36: MAC & ARP

Layer: Link Layer/Back Layer

- 32 bit IP address
	- network-layer address for interface
	- used for layer 3 forwarding
- MAC Address
	- LAN. physical or ethernet address
	- Function
		- Used locally to get frame from one interface to another physicaly-connected interface
	- 48 bit MAC burned in NIC
	- Switches do not have MAC Addresses
		- Switch communication happens at the link level
		- MAC Addresses are used
		- ARP facilitates this communication by providing a MAC address based on IP addresses
			- Similar to DNS in working