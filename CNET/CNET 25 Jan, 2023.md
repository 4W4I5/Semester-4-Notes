## Access networks in detail
Access networks require a medium of transfer be it wire or wireless
Access networks are the interface between the internal mesh of routers and the edge networks

NOTE:: Forget standard home routers when thinking about routers. A router is connecting the network core to the enduser. The switch is wired connections and the access point is the wireless connections. A home router is an all in one package

NOTE:: A Network without an ISP connection will be known as INTRANET

- DialUp
	- Fixed internet connection 
	- Voice-Band MoDem
	- Computer-ISP
	- max theoretical speed of 56kbit/s
	- could only use voice/phone or the internet at one time
- DSL (Digital Subscriber Line)
	- Still using original telephone lines and a modem
	- consistent speed guaranteed as bandwidth is not shared with anyone else
	- use of a DSLAM (DSL access multiplexer)
	- included a splitter that could split the incoming signal into voice and data lines to use separately 
		- Phone and voice data was sent at lower frequencies
		- Data was sent at higher frequencies
	- Encoded at diff frequencies
		- highSpeed = 50kHz - 1MHz
		- slowSpeed = 4kHz - 50kHz
		- voiceCall = 0kHz - 4kHz
- Cable Network
	- Use of cable tv lines
	- Cable modems specific to frequency division multiplexing, used mainly channels 7 and 8
	- Shared network though, need to rely on off hours to get max speed
- Enterprise Access Network (Ethernet)
	- Standard Copper cable used, RJ45
	- 10mb, 100mb, 1gb, 10gb
	- todays network
- Wireless Access Networks
	- Standard WiFi
		- If a switch is wireless capable as well, then assume the higher priority one. Both cannot be used at the same time
	- Wide area wireless networks
		- Known as cellular network
- Data Center Networks
	- 10s to 1000s GBs
	- Connect hundreds of thousands of servers to the internet


### Physical Media Links

- bit
	- transmitted b/w transmitter/receiver pairs
- physical link
	- Actual link to b/w the transmitter and receiver
- guided media
	- Coaxial Cable
		- Two concentric copper conductors
		- Bi-directional
		- Broadband
			- Multiple frequency channels on a cable
			- 100MB per channel
	- Fiber Optic
		- 10Gbps to 100Gbps
		- Low error rate
		- Immune to EMF interference
- unguided media
	- Half-Duplex
		- The illusion of a full duplex connection is given by using multiple channels at the same time
	- Affected by the environment
		- Reflection
		- Obstruction
		- Interference
	- Types
		- Wireless LAN WIFI
			- 10Mbps to 100Mbps over 10's of meters
		- Mobile Networks (Wide Area)
			- 10Mbps over roughly 10 KM
		- Bluetooth
			- Short distances limited rates
		- Microwaves
			- Point to Point
			- 45Mbps Channels
		- Satellites
			- 45Mbps Channels
			- 270ms end to end delay
- twisted pair
	- Two insulated copper wires twisted together to reduce crosstalk
	- CAT5: 100Mbps to 1Gbps
	- CAT6: 10Gbps

# Core Networks

##### Methods to move data
- Packet Switching
	- Wait until table is reserved
	- Router doesn't hold packets back, they get sent via the path of less time
	- No route is dedicated for any one user, which is why packet switching is preferred. 
	- Used in the internet
	- More efficient use of overall network as multiple packets are routed over shared links
	- No call setup, simpler resource sharing
	- Congestion Possible which can cause packet loss and delay
		- Requires Congestion control protocols
- Circuit Switching
	- Need to reserve phone lines to call, 
	- Kind of like reserving a table at a restaurant
		- Might not get a table
	- Used in private specialized networks, eg a nuclear plant or some type of critical infrastructure where a delay or loss cannot be tolerated
	- Constant Data stream
	- Highly reliable once secured
	- Wasted bandwidth when data is not being sent over the connection
	- Modes
		- Explained in the next note [[CNET 1 Feb, 2023]]