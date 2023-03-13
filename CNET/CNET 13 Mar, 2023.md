Lecture 14: UDP (User Datagram Protocol)

- Is meant to do as little as a transport protocol is supposed to do
- UDP itself will not provide an reliablity
	- If it is requied and use of TCP is not possible
		- Implement Reliablity in the Applicaiton Layer

TCP VS UDP
- No connection State
- Small Packet Header

TCP & UDP
- error checking
	- Seems unreal but use of chksum is used
		- Internet CHKSUM
			- Divide segment into 16 bit parts
			- add them up and if carry on MSB then wrap around
			- Take ones complement
			- Place result in CHKSUM field in the header of the segment
	- All layers have their own errorchecking methods
- mux/demux

Uses of UDP
- DNS & DHCP usually uses UDP
- Streaming apps
- UDP is used to carry network management SNMP
- UDP is used for RIP routing protocol