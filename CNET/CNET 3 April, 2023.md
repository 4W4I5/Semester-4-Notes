TCP Flow vs Congestion control

- Network assited flow control
- End to end assisted flow control
- How would a connection determine flow or congestion issues
	- Timeouts or Packet loss, or Duplicate packets
		- Packet loss is more severe as no ack is sent back
- For congestion 
	- Number of packets is reduced
- For Flow control
	- Size of packets is reduced
- Out of congestion widnow size and reciever buffer size, the loewr one is chosen


### TCP handshake



---
Congestion control graphs is what i came back to 


### Congestion aviodance
- increase MSS bytes 
- Slow start with congestion avoidance
	- Occurs after a timeout
		- CWND is set back to 1. Cannot be 0 as that would be division error
		- SSTHRESH is set to half of CWND_PREV
- Drawbacks
	- Slow recovery from losses
### Congestion Control
- TCP Tahoe
- TCP Reno 