Cont IP Datagram

- Upper Layer Protocol
- Datagram length
	- 2^16 Bytes
	- Fragmentation/Reassembly
		- 16-Bit ID
			- The same is assigned to all subdivided packets as well
		- Flags 3-Bit
			- haveMoreFragments: 0 if NO
				- Set to 0 by source host internet process. Also set to 0 for the last segment after fragmentation
		- Fragment offset 13-Bit
			- Based on Octals
			- 
		- \
### IP Fragmentation
- Occurs when IP packet is longer than MTU 
- Router fragments the packet into smaller fragments that are still IP packets.
	- Split to accommodate to smaller the MTU
	- Occurs at the routers
		- Defrag/Reassembly is handled by end system
- Target MTU is the sender's MTU
- Always frag the data, 20 bytes for the IP header is fixed