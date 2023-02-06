# Network Delays

- Different Types of delays (Total Nodal Delay)
	- Nodal Processing Delay
	- Queueing Delay
	- Transmission Delay
	- Propagation Delay
- Packet Pathing
	- Starts from the host 
	- Passes through a series of routers
	- End in destination (another host)

### Processing Delay
- Time required to examine the packets' header 
	- Processing is to determine where to send the packet next to
	- aka a routing decision
- Delay is also added up from bit-level error checking that might've occurred when going through through multiple network layers

### Queueing Delay
- Output interface of routers have a buffer on each output
- A certain route might have queued traffic and the newly forwarded data is stored in the buffer, waiting to be sent along the stream
- Packet drop is also a known risk as when the buffer is full, further packets will be dropped until the connection is freed up enough to accept more packets
- Length of queueing delay depends on the number of early-arriving packets that are queued and waiting for transmission
	- Note that if the queue is empty and no packet is being transmitted, delay is known as 0ms
- Queuing Delay can vary from packet to packet
	- Rate at which traffic arrives
	- Transmission rate of the link
	- Nature of the arriving traffic
		- in bursts or
		- periodically (NOTE:: This is usually better, if asked)
- Formula for determining intensity of queueing delay
	- La/R, where
		- L = Packet Length (bits)
		- R = Link Bandwidth (bps)
		- a = average packet arrival rate
	- La/R ~ 0. no delay  `Fix these`
	-  > 1. packet loss
	- if < 1 then delay

### Transmission Delay / Propagation Delay
- Amount of time required for the router to push out the packet
- Formula: L/R, where
	- L = Length of Packet in bits
	- R = Transmission Rate of Link in bps
- Propagation Delay is the function of distance b/w two routers
	- Packet length or the transmission rate/bandwidth doesnt matter
	- Focus only on one bit instead of the entire packet when thinking about this type of delay. 
	- Formula: Distance b/w two routers / Propagation Speed


### Router Forwarding Method
- Store-And-Forward
	- Wait until the entire frame is in the router memory before forwarding
		- Frame = Packet


### Throughput
- Rate bits/sec at which bits are transferred b/w sender and receiver
	- Instantaneous: rate at any given point in time
	- Average: rate over longer period of time
- Pick always the smaller possible of the multiple choices

## Layers
- Application layer
- Transport layer
	- segments
	- also decides TCP or UDP
- TCP or UDP
	- jfakdnlksfmlvnslkfsn