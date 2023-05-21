Lecture 36: MAC & ARP

Layer: Link Layer/Back Layer

- 32 bit IP address
	- network-layer address for interface
	- used for layer 3 forwarding
- MAC Address
	- LAN. physical or ethernet address
	- Function
		- Used locally to get frame from one interface to another physically-connected interface
	- 48 bit MAC burned in NIC
	- Switches do not have MAC Addresses
		- Switch communication happens at the link level
		- MAC Addresses are used
		- ARP facilitates this communication by providing a MAC address based on IP addresses
			- Similar to DNS in working
			- While sending packets through, MAC address of the sender and directly linked router is used while the IP stays the same

- ARP Table
	- Each host has on the LAN has a table
		- IP/MAC datagram with the receivers unknown MAC is sent 
		- Receiver will respond in unicast with its MAC message as it already has the IP of the sender
		- All nodes however receive an ARP query

Lecture 37: Ethernet & Switches





---
SUMMER MISP CTI