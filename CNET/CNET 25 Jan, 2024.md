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
	- consistent speed guaranteed
	- use of a DSLAM (DSL access multiplexer)
	- included a splitter that could split the incoming signal into voice and data lines to use separately 
	- Encoded at diff frequencies
		- highSpeed = 50kHz - 1mHz
		- slowSpeed = 
		- voiceCall = 
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


### Physical Media

- bit
- physical link
- guided media
- unguided media

# Core Networks

##### Methods to move data
- Packet Switching
	- Wait until table is reserved
	- Router doesn't hold packets back, they get sent via the path of less time
	- No route is dedicated for any one user, which is why packet switching is preferred. 
	- Used in the internet
- Circuit Switching
	- Need to reserve phone lines to call, 
	- Kind of like reserving a table at a restaurant
		- Might not get a table
	- Used in private specialized networks, eg a nuclear plant or some type of critical infrastructure where a delay or loss cannot be tolerated