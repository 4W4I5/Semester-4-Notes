# DNS (Domain Name System)

- ### Distributed Database implemented in the hierarchy of many many nameservers
	- #### Core internet Function
		- Resolve Names to IP addresses
	- #### Host Aliasing
		- Canonical Alias Names
		- Convert a complicated name into a simpler name
			- Example: enterprise.com can be a CNAME for 'www.enterprize.com'
	- #### Mail Server Aliasing
	- #### Load Distribution
		- Replicated web servers
			- Many IP Addresses correspond to one name
	- #### Why Not Centralize DNS?
		- Single point of Failure
		- Traffic Volume
		- Distant Centralized Database
		- Maintenance
		- Doesn't scale at all
			- COMCAST DNS 600B DNS queries/Day
			- AKAMAI DNS 2.2T queries/Day
	- #### Trivia
		- Billions of records, each of them simple
		- Handles Trillions of queries per day
			- A lot more reads than writes
		- Physical decentralized
			- millions of different organizations are responsible for their own records
		- Bulletproof Reliability and Security

## DNS Records

Stored in Resource Records formatting: (Name, Value, Type, TTL)
- ##### Type A
	- Name is Hostname
	- Value is IP
	- Technically also a glue record when address of DNS server is given
	- Example:
		- google.com (google.com, 192.21.42.1, A, 255)
- ##### Type NS
	- Name is Domain
	- Value is Hostname of AUTHORITATIVE server for this domain
	- CANNOT have an IP in the record
	- Example: DNS name googledns
		- (google.com, s1.googledns.com, NS, 255)
		- (google.com, s2.googledns.com, NS, 255)
- ##### Type CNAME
	- Aliased name for the real name
	- Can NEVER point to an IP address
		- can however point to another CNAME
	- Value is the CNAME
	- Example can be the same as NS as well but usually used for link shortening
		- (bit.ly/24Sd, google.com, CNAME, 255)
- ##### Type MX
	- Mail Server
	- priority value returned
	- Value is name of SMTP Mail Server associated with Name
- #### Glue Records
	- 'Glues' together the domain and its nameservers that answer the query for that domain
	- IF a nameserver is located in a different domain than the one being queried from the nameserver above the current one, a glue record is used to change domains.
		- Without one, additional dns queries are required or possibly even a loop can be encountered
	- Usually needed when two domains use the same nameservers, creating a cyclic redundancy
		- A records can usually include both nameservers for a single domain
	- Also usually needed when hosting your own authoritative name servers

## DNS Hierarchy

- #### ROOT
	- 13 Logical servers, replicated over the globe
		- Over 600 different DNS root servers distributed
	- Uses AnyCast Routing
	- Operated by ICANN
		- Internet Corporation for Assigned Names and Numbers
	- Built into DNS resolvers
		- Recursive resolvers cannot direct to the root zone
		- Every resolver has the list of 13 Root servers built in
	- Contact-of-Last-Resort name servers
	- DNSSEC - Provides security. Mostly Authentication and message integrity
- #### Top-Level Domain
	- Responsible for all top level country and normal domains such as
		- Generic TLDs
			- .com, .edu, .net, .org
		- ccTLDs (Country Code TLD)
			- .pk, .uk, etc
- #### Authoritative
	- Organization's own DNS servers providing hostname to IP mappings for organizations
	- Maintained by the organization itself or the service provider
	- the URL behind the TLD dns
- #### Local
	- Also known as 'Default Name Server'
	- Doesn't belong to the hierarchy
	- Local to the Host itself
	- It is basically a DNS Cache of previous requested addresses
		- If not found in the cache then it is sent to the DNS query

## Query & Reply

- Both of them have the same format, differentiated by flags
- Structure:
	- 2 bytes for
		- Identification
			- Same ID is used for the reply
		- Flags
			- isReply
			- isReplyAuthoritative
			- isRecursionDesired
				- If false, only if the DNS server is authoritative will it send a response for the query or if it has the domain cached. If not authoritative it will set the isRecursionAvailable flag off
				- if true, the DNS server will attempt to query for the record on its own when it can not find the record in its own domain
			- isRecursionAvailable
				- Affected by the isRecursionDesired flag
		- Number of Questions
		- Number of Answer Records
		- Number of Authority Records
		- Number of Additional RR
	- 4 bytes for
		- Questions
		- Answers
		- Authority
		- Additional Info

## DNS Name Resolution

- #### Iterated Query
	- Query starts at the Root level then is forwarded to the TLD level and then the authoritative level
	- Every server is pinged for the requested domain this way.
	- No resolvers are involved
- #### Recursive Query
	- A DNS resolver sends a query to the DNS server, if the server is not authoritative for the domain then it will attempt to query other DNS Servers at the behalf of the resolver until a domain is returned

## DNS Caching

- Once a server learns a mapping, it is cached and sent in response to the query the next it receives it
	- Improves response time
	- Cached Entries Timeout after a set time (TTL)
	- TLD servers are cached in local nameservers
- Best to use name-to-address translation
	- Entries might go out of data when a website changes IPs

## Setting up a website and Updating the DNS

- Assuming a domain is purchased, the registrar will associate an Authoritative server to point to their own DNS servers (NS records created)
	- Modifications to your domain modifies the NS records in the Authoritative server
- People queried the website will query the Root
	- Root will redirect to TLD + provide glue records
- TLD will query Authoritative servers
	- When the correct one is found till return the IP of the domain or redirect until the correct one is found




---

# Transport Layer Protocols

- UDP
	- Connectionless Transport
- TCP
	- Connection-Oriented Reliable Transport
	- Congestion & Flow control

### Transport Services & Protocols

- **Provide logical communication b/w app processes running on different hosts**
	- Not on application layer but on transport layer
	- Port is assigned hence Transport layer is the layer that provides the comms link
	- Application layer only provides the data
		- Endpoint for process/application on a host
		- Comes in two types UDP & TCP
		- Consists of IP address & port number
			- 192.168.1.1:8080 -> this is a socket with Ip and port
	- Network layer provides comms link b/w systems
- **At base layer, Internet Protocol is what works on the transport layer**
	- It tries its best effort to deliver segments but does not guarantee
		- Segment delivery aka packet loss
		- Integrity of data in segments aka out of order packets

### Socket

- A listening process is always running on the server
	- One can tell if a process is a listening type by examining the destination fields
		- They'll be empty and source fields will be the server's IP and listening port number
- Once an ACK is sent by the client
	- The server spawns a new socket using the client IP/Port + Server IP/Port
	- This is closed after connection close

---

# UDP

- Is meant to do as little as a transport protocol is supposed to do
- UDP itself will not provide any reliability
	- If it is required and use of TCP is not possible
		- Implement Reliability in the Application Layer
- Uses of UDP
	- DNS & DHCP usually uses UDP
	- Streaming apps
	- UDP is used to carry network management SNMP
	- UDP is used for RIP routing protocol

#### TCP VS UDP

- No connection State
	- No ack numbers
	- No seq numbers
	- No send/receive buffers
	- No congestion-control parameters (MSS & MTU)
- Small Packet Header
	- 8 Bytes for UDP
		- 2 bytes for the source port number
		- 2 bytes for the destination port number
		- 2 bytes for the length field (which specifies the length of the entire UDP datagram, including the header and the data)
		- 2 bytes for the checksum field (used for error detection)
	- 20 Bytes for TCP

#### Both TCP & UDP have:

- error checking
	- Seems unreal but chksum is used
		- Internet CHKSUM
			- Divide segment into 16 bit parts
			- add them up and if carry on MSB then wrap around and sum it again
			- Take ones complement of the result
			- Place result in CHKSUM field in the header of the segment
			- To verify
				- Do not recalc checksum at the recieving end
				- Instead
					- Slice data up into 16 bits
					- Add the chksum
					- If result has
						- All bits set to 1 = CHKSUM Valid
	- All layers have their own error checking methods
- mux/demux
	- Handle data from multiple sockets, add transport header
	- Demux-ed using port numbers
		- **Connectionless-Multiplexing requires**
			- Sockets have unique identifiers
			- each segment have special fields that indicate the socket to which the segment is to be delivered
			- special fields are the src port num and the dest port num
		- **Connectionless-Demux requires**
			- Each datagram to have src IP and dest IP
				- Each segement within has a src Port and dest Port
		- **Connection-Oriented Mux requires**
			- Used by TCP
				- Establishes a connection first before transmission
			- 4-tuple Data {srcIP, destIP, srcPort, destPort}
		- **Connection-Oriented DeMux requires**
			- 4tuple data to determine appropriate socket
				- Used 4tuple as multiple connections can share the same socket
				- Different IP's using the same port can be differentiated
				- Different Ports used by the same IP can be differentiated

---

## Reliability in general

#### Principles of Reliable Data Transfer

- Try as much as possible, bits can be flipped leading to corruption during transmission
- TCP is made complex by addressing the problems of IP

#### RDT 1.0 (Assume a perfect underlying channel)

- That means
	- No loss of packets
	- No bit errors
- Finite-State Machines
	- Sender
		- creates a packet from segments
		- sends packet over to unreliable data channel
	- Receiver
		- receives packet
		- extracts into segment
		- passes segments up into application layer

#### RDT 2.0 (Assume bit corruption is possible, but no packet loss still)

- That means a small error can occur during transmission
- CHKSUM can detect the error but how to fix it?
	- Use of ACK & NACK (Acknowledgements & Negative-Acknowledgements)
- New mechanisms
	- Error Detection
	- Feedback
	- Stop & wait Protocol
		- Sends a packet and then halt next packet transmission until a response is received
- Finite-State Machine
	- Sender
		- Wait for packet response from receiver
		- IF NACK
			- Resend previous packet and wait for response
		- IF ACK
			- Send new Packet and wait for response
	- Receiver
		- Wait for packet from sender
		- Extract data from packet received
		- Run CHKSUM
			- IF CHKSUM VALID
				- Send ACK
				- Deliver data to application layer
			- IF CHKSUM INVALID
				- Send NACK
				- Wait for new packet
	- Flaw
		- If ACK/NACK is corrupted sender will assume data was successfully delivered and send the next packet
			- No way of knowing if everything is alright if the feedback is corrupted
		- Sender system has two states, waiting for response and then sending a packet
			- Corrupted feedback means that it will forever be stuck in a waiting state as new data cannot be processed until the current response is heard
		- If CHKSUM has two bits toggle then the error is cancelled out and a ACK will be sent back

#### RDT2.1

- Improvement to RDT 2.0
	- Handles lost ACK/NACK
- Sender/Receiver must remember last state of packet to determine if it is a duplicate
	- Receiver does not know if ACK/NACK was ok at sender
- 4 States, N can be 0 or 1
	- Wait for Packet with N sequence number or ACK/NACK of previous packet
		- Assume on invalid chksum or dropped ACK/NACK the packet is resent
		- On stuck waiting state,
	- IF ACK, then next Packet is sent with N+1 Sequence Number
	- IF NACK, then Nth Packet is sent again
- Flaw
	- If sender does not wait for ACK/NACK, this will fail

#### RDT2.2

- Get rid of NACK
	- ACK the packet # being received
	- think of it as XNOR(packetRecived, packetSent) == 0)
		- Retransmit packet if ACK of prevPacket is the same as the ACK of the currentPacket
- Go back to 2 states
	- Send packet with N sequence
	- Expect ACK of N
	- If ACK N + 1, then invalid. Retransmit.
		- Duplicate packets get dropped

#### RDT3.0

Introduce Packet loss now into the equation
- introduce countdown timer, waits for ACK after sending packet
	- If ACK is not sent, resent packet for ACK
	- If ACK is lost then sender resends duplicate and it is dropped by reciever
	- If ACK is delayed, same scene, itll just drop the ack/set it as seen
- Very resource intensive, consumes bandwidth due to stop and wait. Only one packet is sent at a time
	- Utilization
		- U = D/(RTT + D)
		- D = L/R
			- L = Length of packet in bits
			- R = Link speed in bits per second


---

# PipeLined Protocols (Go Back N & Selective Repeat)

- ## Two protocols besides stop n wait
	- #### Go-Back-N
		- Send a batch of N Packets
		- If any is corrupted or missed, resend all from missed packet
			- Reciever will keep responding with SegNum(PcktNum n-1)
		- Sender
			- Maintains two pointers, sendbase and nextseqnum
		- Simplified Logic
			- IF Packet is dropped
				- Sender buffer does not advance
				- Receiver sends last known ACK
				- Timeout results in the sender buffer being sent all at once
			- IF ack is dropped
				- Skip over onto the next ack received if in window
				- if not in window then wait for timeout and resend ACK
		- Complex Logic (Bigger picture)
			- Send packets within window
			- Sender
				- If next ack not received, start a timer
					- If timeout, retransmit all from last ack'ed packet
				- if next ack received, move window forward and send new packets within
			- Receiver
				- If packet with correct sequence number received, send ack with current seq num
					- If packet lost, send ack for last good packet received for any packet with seq num greater than the last good packet
			- KEY FACTS (IGNORE DUPLICATES, NOT ENOUGH TIME TO REFINE)
				- **Sender resends all unacknowledged packets:** When a timeout or NAK occurs in Go-Back-N, the sender resends all unacknowledged packets from the first unacknowledged packet.
				- **Receiver buffers packets in order:** In Go-Back-N, the receiver buffers packets in order and only delivers them to the upper layer when all previous packets have been received.
				- **Does not allow out-of-order packets:** Go-Back-N does not allow out-of-order packets, so the receiver must discard any packets that arrive out of sequence.
				- **Requires smaller buffer space:** Go-Back-N requires a smaller buffer space at the receiver, since packets are delivered in order and can be discarded once they have been delivered.
	- ### Selective Repeat
		- **Receiver buffers individual packets:** In Selective Repeat, the receiver buffers and acknowledges each packet individually.
		- **Sender only resends lost packets:** When the sender receives a NAK or timeout, it only resends the lost packet(s), rather than retransmitting all packets that were sent after the lost one.
		- **Allows out-of-order packets:** The receiver can accept and buffer out-of-order packets, and then deliver them to the upper layer in order.
		- **Requires larger buffer space:** Selective Repeat requires a larger buffer space at the receiver to store out-of-order packets.

##### NOTE:: A packet cannot live in the network for more than approx 3 min

---

# TCP (Transmission Control Protocol)

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
NOTE:: nothing is stored in the network elements i.e. routers, switches, repeaters b/w the hosts

### TCP Segment Structure

- consists of
	- src/dest port (32 BITS)
	- sequence number (64 BITS)
	- ack number (64 BITS)
	- len (8 BITS)
	- UNUSED SECTION (8 BITS)
	- recieve windows (32 BITS)
		- num of bytes receiver is willing to accept
	- chksum (32 BITS)
	- flags = SYN, ACK, RESET, PUSH, URGENT, FIN (16 BITS)
		- PUSH: App informs that data should be pushed up the stack in the receiving app
		- URGENT: Transmit everything right now, used for remote interrupts
		- ACK: acknowledge
		- RESET: Abort connection
		- FIN: Close connection
		- SYN: Sync
	- app data, can be variable length
	- urgent data pointer (32 BITS)
	- TOTAL SIZE = 20 BYTES

### TCP Sequence Numbers

- Bytestream
- packet is divided into segments based on MSS, div total size by MSS
- initial number is randomly chosen at handshake

### TCP Acknowledgement Numbers

- indicates which byte in the stream is expected next and thus which bytes have been received
- initial number is randomly chosen at handshake
- wait for the lowest seq num packet to receive



NOTE:: These are swapped b/w sender and receiver. They will still increment.

#### Cumulative ACK vs Accumulative ACK (UNKNOWN)
- Cumulative
	- Used in Go Back N
	- Waits for last highest ACK
- Accucmulative ACK
	- Used in Selective repeat
---

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


---

Lecture 20: TCP Flow Control

- All about matching speed with receiver
- Use of Send/Receive Buffers
- As MSS is fixed, flow is done using number of segements sent
	- During SYN sent by client, it sends the size of its buffer in bytes
	- During SYN-ACK response by server, it sends the size of its buffer in bytes
		- Both values are stored in the receive window

### Calculate Window Size

- Variables
	- RWND
	- RCVBUFFER
- Happens on both sender/receiver side

What happens if rcvBUFFER is full

### TCP FLOW CONTROL (CHATGPT)
1.  Sender and receiver agree on the initial value of the receiver's advertised window size (rwnd) before data transmission begins.
2.  The sender transmits data in segments of a fixed size (MSS), and the receiver acknowledges each segment as it arrives.
3.  The receiver's advertised window size (rwnd) is calculated as the difference between the maximum receive buffer size and the number of bytes already in the buffer.
4.  If the receiver's buffer becomes full, the receiver sets the rwnd to 0 to indicate that it cannot receive any more data.
5.  The sender receives the updated rwnd value from the receiver in the ACK packets and adjusts its sending rate accordingly.
6.  If the rwnd value becomes zero, the sender must stop transmitting data until it receives an ACK with a non-zero rwnd value.
7.  When the receiver has more space in its buffer, it updates the rwnd value and sends an ACK with the new value to the sender.
8.  The sender resumes sending data, based on the updated rwnd value.


Lecture 21: TCP Connection Management


---

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

---

When do we go into congestion avoidance state
	- When the threshold is hit
		- Threshold is increased by one for every ack

Fast recovery avoidance
- When 3 dupes are received, fast retransmission is used. Skip the timeout period
- Used in TCP Reno

Congestion Control
- Timeout causes multiplicative decrease where CWND is halved
- Upon threshold hit, additive increase by 1
	- until congestion detected in other words a duplicate ack is received


---
GOT FROM CHATGPT (TCP CONGESTION
1. Slow Start:

- The initial window size is set to a small value, e.g. 1 MSS (maximum segment size).
- For every ACK received, the window size is increased by 1 MSS.
- The window size grows exponentially until it reaches a threshold called the congestion window (cwnd).
- The cwnd is typically set to a fraction of the maximum receive window advertised by the receiver.
- Mathematically, the window size is given by: `Window size = min(cwnd, receiver's advertised window)`

2. Congestion Avoidance:

- Once the cwnd is reached, TCP switches to congestion avoidance mode.
- In this mode, the window size is increased linearly for every round-trip time (RTT).
- The increase is typically by 1 MSS for every RTT.
- Mathematically, the window size is given by: `Window size = min(cwnd, receiver's advertised window) + (MSS * (number of ACKs received in RTT))`

3. Fast Retransmit/Fast Recovery:

- If TCP detects a packet loss, it assumes that the network is congested and reduces the window size to half of its current value.
- It then enters fast recovery mode and sends new packets while waiting for ACKs.
- If it receives three duplicate ACKs for a particular packet, it assumes that the lost packet has been retransmitted and immediately sends another copy of it.
- Mathematically, the window size is given by: `Window size = ssthresh + 3 * MSS`

where ssthresh is the threshold value of cwnd at which TCP switches to slow start mode.


4. Timeout:

- If a packet is not acknowledged within a certain time frame, TCP assumes that it has been lost and retransmits the packet.
- It also reduces the window size to the initial value and restarts the slow start algorithm.
- Mathematically, the window size is given by: `Window size = 1 MSS`
- This ensures that TCP can recover from severe network congestion caused by multiple packet losses.

5. AIMD (Additive Increase Multiplicative Decrease):

- AIMD is a congestion control algorithm used by TCP in congestion avoidance mode.
- In AIMD, TCP increases the window size linearly for every RTT until it reaches the cwnd.
- Once the cwnd is reached, TCP reduces the window size multiplicatively by half in response to packet loss or congestion signals.
- This allows TCP to respond quickly to network congestion, while ensuring that it does not flood the network with too much traffic.
- Mathematically, the window size is given by: `Window size = min(cwnd, receiver's advertised window) + (MSS * (number of ACKs received in RTT)) - (number of packets lost / cwnd) * MSS * cwnd`
