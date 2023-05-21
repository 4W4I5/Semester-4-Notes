# Link Layer

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
			- hosts are unware of switches in the network
		- plug n play, self learning
			- builds a switch table to forward to the correct host
				- done by broadcasting the same packet to everyone, store senders mac address and then get the receivers mac address when they reply back. 
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
- 
# Network Layer
# Transport Layer
# Session Layer
# Application Layer
