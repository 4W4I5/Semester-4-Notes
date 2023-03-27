Lecture 20: TCP Flow Control

- All about matching speed with receiver
- Use of Send/Receive Buffers
- As MSS is fixed, flow is done using number of segements sent
	- During SYN sent by client, it sends the size of its buffer in bytes
	- During SYN-ACK response by server, it sends the size of its buffer in bytes
		- Both values are stored in the receive window

### Calculate Window Size
- 