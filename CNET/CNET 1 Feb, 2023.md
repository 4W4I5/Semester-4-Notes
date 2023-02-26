## Circuit Switching (MAC protocols)
##### Switching Modes FDM vs TDM

# Frequency Division Multiplexing
- Use of one transmission medium i.e. a certain frequency channel. Assign a frequency to each user. 
	- WIFI has the concept of collision as well by being a shared medium but its is mitigated by FDM, Router works on channels 1-10
	- Limited bandwidth but consistency granted
# Time Division Multiplexing
- Assign a time slot to each user, only for that fixed time will the data be transferred at full speed
	- Full bandwidth granted but consistency is bad since going over the limit of allowed users will affect the entire connection for other users as well


## Key Network-Core Functions
- ### Forwarding 
	- Modify a packet's header for the next appropriate router
	- Act of sending the packet to the destination router based on routing information
- ### Routing
	- Determines the source to destination route of packets
	- It is the act of processing the next route for the packet done by the router

### Internet Structure: Network of Networks
- Given millions of ISPs how do we connect them together?
	- Bad scalability method: Connect every ISP to every other ISP
	- A better option: Have a central ISP that governs/routes traffic from local ISPs but the central ISP will run a monopoly
		- Also thinking from a business standpoint, other central ISPs might not connect with other central ISPs
		- Central ISPs also have Peering links (hardware connections) with a bridge router and IXP (Internet Exchange Point) 
			- IXPs take responsibilty and setup the hardware to route data b/w two central ISPs when peering isnt possible
			- It is also how internet infrastructure companies such as ISPs, CDNs (Content Delivery Network), web enterprises, CSPs(communication service providers), Cloud providers, SaaS providers connect to each other
- Content Delivery Network
	- A CDN is a geographically distributed group of servers that work together to provide fast delivery of internet content
	- Usually used for fast delivery including html pages, javascript files, css sheets, images and videos
	- Synced together to allow for faster local data delivery
	- Essentially created a temp data store that holds the most requested data
	- CDN deploys servers globally
		- Known as Point of Presence (PoP)
		- A server in the PoP is known as a edge server
		- Edge servers act as proxy with a huge content cache
		- CDNs will also communicate with the originating server to deliver any content that wasnt previosuly cached
		- Static content is usally cached
	- Content Request Method
		- DNS Based Routing
			- Each PoP has its own IP assigned.
			- User looks up IP for CDN(the entire network not the server nearby) 
			- The DNS returns the IP of the PoP instead
		- AnyCast
			- All Edge servers have the same IP
			- A request to the anycast network to the DNS
			- The DNS returns the IP of the PoP that is closest to the repeater
			- `Look up more information on this topic`
			- How do the servers talk to each other, if they have the same IP?
				- MAC addresses might be cached


#### Layers of the internet
- User Layer
- Regional Layer
- Provincial Layer
- Country Layer
- Continent Layer
- CDN Layer
- Another way to look at this
	- Access ISP
	- Regional ISP
	- IXP
	- Tier 1 ISP or CDN 