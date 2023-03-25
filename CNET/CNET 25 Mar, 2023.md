Lecture 19: TCP reliable data transfer

- How to set TCP Timeout
	- longer than RTT, however RTT varies
		- If timeout is too short then unecessary retransmissions
		- if timeout is too long then slow reaction to segment loss
- EstimatedRTT = (1 - a).EstimatedRTT + a.SampleRTT
	- typical value for a is 0.125
- TimeoutInterval = EstimatedRTT + 4xSampleRTT

- TCP creates RDT service on top of IP's unreliable service
	- Pipelined segments
	- Cumulative Acks
	- Single retransmission timer
- Retransmission is triggered 
	- timeout events
	- if duplicate acks are received

### TCP sender events (fill from recording)
- Data received from app
- Timeout
- Ack received