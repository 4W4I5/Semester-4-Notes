Lecture 18: TCP Segment Structure

- TCP is a hybrid of GO-BACK-N & Selective Repeat
	- Takes the timer and cumulative acknowledgement
	- Takes the out of order buffer from selective repeat
- Overview
	- point-to-point
		- one to one connection as one to many is not possible
	- reliable in-order byte stream
		- reordered in the transport layer, network layer is known as mesh of routers in this state
	- pipelined
		- TCP congestion and flow control mechanism
	- full duplex, bidirectional
		- Data is being sent and acknowledgements are being received
	- connection oriented
		- three way handshake
	- flow controlled

### MSS & MTU
- MSS (Max Segment Size)
		- Max amount of data in a segment
			- TCP header is a fixed 20 bytes
			- MSS sets the data length
		- Only restricted to the application layer
		- Wfif has a smaller MSS, Ethernet allows for a bigger standardized MSS
- MTU (Max Transmission Unit)
		- used to set MSS
		- assume a MTU of 1000, subtract 40 bytes from TCP/IP header therefore MSS will be 960
			- 40 bytes as TCP header is encapsulated by IP header
		- dependent on the medium used to transmit
			- usually standardized
		- excludes the frame header, in other words, the max bytes to transmit a packet\

### TCP Send/Receive Buffers
- Unique to every process, aka it is unique to every socket 
- set after the 3 way handshake

### TCP Connection
- Consists of 
	- Buffers & Variables
	- Socket connection to a process in one host, and another set of buffers, variables & a socket connection to a process in another host
NOTE:: nothing is stored in the network elements i.e routers, switches, repeaters b/w the hosts

### TCP Segment Structure
- consists of
	- src/dest port
	- sequence number
	- ack number
	- len
	- recieve windows
		- num of bytes receiver is willing to accept
	- chksum
	- flags = SYN, ACK, RESET, PUSH, URGENT, FIN
	- app data, can be variable length
	- urgent data pointer