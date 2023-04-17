Cont IP Datagram

- Upper Layer Protocol
- Datagram length
	- 2^16 Bytes
	- Fragmentation/Reassembly
		- 16-Bit ID
			- The same is assigned to all subdivided packets as well
		- Flags 3-Bit
		- Fragment offset 13-Bit
		- \
### IP Fragmentation
- Occurs when IP packet is longer than MTU 
- Router fragments the packet into smaller fragments that are still IP packets.
	- Split to accommodate to smaller the MTU
	- Occurs at the routers
		- Defrag/Reassembly is handled by end system
- Target MTU is the sender's MTU