RDT 2.0 cont.
duplication error, state stuck in forever wait if ack is corrupted

RDT2.1
fixed duplication error by adding XOR of prev packet number
twice as many states as rdt2.0

RDT2.2
- Get rid of NACK
	- ACK the packet # being received
	- think of it as XNOR(packetRecived, packetSent) == 0)
- Go back to 2 states

RDT3.0
Introduce Packet loss now into the equation
- introduce countdown timer, waits for ACK after sending packet
	- If ACK is not sent, resent packet for ACK
	- If ACK is lost then sender resends duplicate and it is dropped by reciever
	- If ACK is delayed, same scene, itll just drop the ack/set it as seen
	
- Very resource intensive, consumes bandwidth
`Add in formulas from notes to calculate consumption`

---
Lecture 17: Pipelined Protocols
- Two protocols besides stop n wait
	- Go-Back-N
		- Send a batch of packets
		- If any is corrupted or missed, resend all from missed packet
			- Reciever will keep responding with SegNum(PcktNum n-1)
		- Sender
			- Maintains two pointers, sendbase and nextseqnum
	- Selective Repeat
		- Complete from slides