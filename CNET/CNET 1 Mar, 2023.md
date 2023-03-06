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


## DNS Records
Stored in Resource Records formatting: (Name, Value, Type, TTL)
- ##### Type A
	- Name is Hostname
	- Value is IP
- ##### Type NS
	- Name is Domain
	- Value is Hostname of AUTHORITATIVE server for this domain
- ##### Type CNAME
	- Aliased name for the real name
	- Value is the CNAME
- ##### Type MX
	- Mail Server
	- Value is name of SMTP Mail Server associated with Name 

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
		- .com, .edu, .net, .org
		- .pk, .uk, etc
- #### Authoritative
	- Organization's own DNS servers providing hostname to IP mappings for organizations
	- Maintained by the organization itself or the service provider
	- the URL behind the TLD dns 
- #### Local
	- Doesnt belong to the hierarchy 
	- Local to the Host itself
	- It is basically a DNS Cache of previous requested addresses
		- If not found in the cache then it is sent to the DNS query 


## DNS Name Resolution

- #### Iterated Query
- #### Recursive Query

## DNS Caching
- Once a server learns a mapping, it is cached and sent in response to the query the next it recieves it
	- Improves response time
	- Cached Entries Timeout after a set time (TTL)
	- TLD servers are cached in local nameservers
- Best to use name-to-address translation
	- Entries might go out of data when a website changes IPs

## Setting up a website and Updating the DNS

- Example you have a new startup by networkutopia
	- Reigster name at DNS registrar
		- Provides names, IP addresses of Authoritative Name



NOTE::Glue records missing
