## Lecture 9
#### Application Layer (DNS)

- ### Domain Name System
	- Distributed Database implemented in the hierarchy of many many nameservers
	- Core internet Function
		- Resolve Names to IP addresses
	- Host Aliasing
		- Canonical Alias Names
	- Mail Server Aliasing
	- Load Distribution
		- Replicated web servers
			- Many IP Addresses correspond to one name
	- Why Not Centralize DNS?
		- Single point of Failure
		- Traffic Volume
		- Distant Centralized Database
		- Maintenance
		- Doesn't scale at all
			- COMCAST DNS 600B DNS queries/Day
			- AKAMAI DNS 2.2T queries/Day
	- Trivia
		- Billions of records, each of them simple
		- Handles Trillions of queries per day
			- A lot more reads than writes
		- Physical decentralized
			- millions of different organizations are responsible for their own records
		- Bulletproof Reliability and Security



## DNS Hierarchy

