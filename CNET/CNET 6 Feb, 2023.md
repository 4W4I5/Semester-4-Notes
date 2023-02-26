# Network Delays

- Types of delays (Total Nodal Delay)
	- Processing Delay
	- Queueing Delay
	- Transmission Delay
	- Propagation Delay
- Packet Pathing
	- Starts from the host 
	- Passes through a series of routers
	- End in destination (another host)
- How to measure delay in the real world
	- Use TraceRoute

### Processing Delay
- Time required to examine the packets' header 
	- Processing is to determine where to send the packet next to
	- aka time to make a routing decision
- Delay is also added up from bit-level error checking that might've occurred when going through through multiple network layers

### Queueing Delay
- Output interface of routers have a buffer on each output
- A certain route might have queued traffic and the newly forwarded data is stored in the buffer, waiting to be sent along the stream
- Packet drop is also a known risk as when the buffer is full, further packets will be dropped until the connection is freed up enough to accept more packets
- Length of queueing delay depends on the number of early-arriving packets that are queued and waiting for transmission
	- Note that if the queue is empty and no packet is being transmitted, delay is known as 0ms
	- However if queue is full then the arriving packet is dropped therefore lost and has to be sent again
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
	- if La/R tends to 0. little to no delay  
	- if La/R tends to 1. delay increases
	- if La/R > 1 then delay is infinite (Packet loss)
- Factors
	- Size of Queue directly proportional to Length of delay
	- Number of packet arriving is also proportional to Length of delay
	- Number of servers/links is inversely proportional to Length of delay

### Transmission Delay / Propagation Delay
- Types Explained
	- Transmission
		- The time it takes to get the **packet** from the host onto the transmission medium
			- Occurs at both the transmitting host and the receiving host
	- Propagation
		- The time it takes for a **single bit** to go through the medium
- Formula: L/R, where
	- L = Length of Packet in bits
	- R = Transmission Rate of Link in bps
- Propagation Delay is the function of distance b/w two routers
	- Packet length or the transmission rate/bandwidth doesn't matter
	- Focus only on one bit instead of the entire packet when thinking about this type of delay. 
	- Formula: Distance b/w two routers / Propagation Speed
- Factors
	- Multiple active sessions means more delay
	- Increasing Bandwidth will decrease delay
	- MAC protocol determines if the delay in the link is shared among devices


### Router Forwarding Method
- Store-And-Forward
	- Wait until the entire frame is in the router memory before forwarding
		- Frame = Packet
	- Delay by this method is
		- 3L/R


### Throughput
- Rate bits/sec at which bits are transferred b/w sender and receiver
	- Instantaneous: rate at any given point in time
	- Average: rate over longer period of time
- Pick always the smaller possible of the multiple choices
- Rc is Rate of Client
- Rs is Rate of Server
- If a backbone is shared then its bandwidth is the number of users divided by max speed of the link
	- the bottleneck might still be Rc or Rs but still it is good to modify R to your needs to see it clearly
