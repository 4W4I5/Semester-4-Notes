When do we go into congestion avoidance state
	- When the threshold is hit
		- Threshold is increased by one for every ack

Fast recovery avoidance
-  When 3 dupes are received, fast retransmission is used. Skip the timeout period
- Used in TCP Reno

Congestion Control
- Timeout causes multiplicative decrease where CWND is halved
- Upon threshold hit, additive increase by 1
	- until congestion detected in other words a duplicate ack is received