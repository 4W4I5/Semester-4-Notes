# Chapter 3: Transport Layer

### Transport Layer Protocols
- UDP
	- Connectionless Transport
- TCP
	- Connection-Oriented Reliable Transport
	-  missed a point
---
### Transport Services & Protocols
-  Provide logical communication b/w app processes running on different hosts
	- Not on application layer but on transport layer
	- Port is assigned hence Transport layer is the layer that provides the comms link
	- Application layer only provides the data
		- %%Check up on what sockets actually do then%%
	- Network layer provides comms link b/w systems

### Mux/Demux
- Handle data from multiple sockets, add transport header
	- Demux-ed using port numbers
	- Multiplexing requires
		- Sockets have unique identifiers
		- each segment have special fields that indicate the socket to which the segment is to be delivered
		- special fields are the src port num and the dest port num
	- Demux requires
		- 