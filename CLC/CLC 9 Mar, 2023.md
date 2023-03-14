- CIDR 
	- Overlapping means IP Class overlapping
		- CIDR also does not overlap but it looks like it does as the second or third octet is shared.
		- A variable amount of fixed bits means that standard classes lose their meaning and therefore 192.168.1.XX(20) and 192.168.2.XX(20) have a few IPs that have the 3rd octet shared but it still is only part of one subnet and not shared
- VPC Reserved IP Addresses
	- A CIDR block of 10.0.0.0/ 16 has 65535 total IP addresses
	- This gives the VPC 4 equally sized subnets
	- out of which each subnet only has 251 usable IP addresses

### Public IP
- Manually assigned through an Elastic IP address
	- Elastic IP
		- Associated with AWS Account
		- Can be allocated and remapped at any time
		- Additional costs
- Auto-assigned using the PublicIP settings at the subnet level

### Elastic Network Interface
- Can be attached/detached and then reattached to an instance
- Attriubtes follow when reattached to a new instance
- Each instance has a default network interface that is assigned a private IPv4 address from the range of the IPv4 range in VPC

### Route Tables & Routes
- Route Table contains a set of rules that you can configure to direct traffic from your subnet
	- Each route specifies a destination and a target
		- If target == "Local" then at the VPC level any destination is within the VPC network of multiple subnets
	- Each subnet must be associated with at least one route table
	- By default, every table contains a local route for communication within the VPC
	- Defines outgoing connections
		- 0.0.0.0/0  to Gateway means all internal IPs in the VPC
### Internet Gateway
- Final piece of the puzzle that connects to the internet
- An ip with a fixed bit length of 32 is sent to the gateway in the routing table
- Each gateway has its own IP as well assigned to it


 For private subnets there has to be a way for them to connect to the internet without acutally being public to the internet
