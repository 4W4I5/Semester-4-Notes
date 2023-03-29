- CIDR
	- Overlapping means IP Class overlapping
		- CIDR also does not overlap but it looks like it does as the second or third octet is shared.
		- A variable amount of fixed bits means that standard classes lose their meaning and therefore 192.168.1.XX(20) and 192.168.2.XX(20) have a few IPs that have the 3rd octet shared but it still is only part of one subnet and not shared
- VPC Reserved IP Addresses
	- A CIDR block of 10.0.0.0/ 16 has 65535 total IP addresses
	- This gives the VPC 4 equally sized subnets
	- out of which each subnet only has 251 usable IP addresses

### Route Tables & Routes

- Route Table contains a set of rules that you can configure to direct traffic from your subnet
	- Each route specifies a destination and a target
		- If target == "Local" then at the VPC level any destination is within the VPC network of multiple subnets
	- Each subnet must be associated with at least one route table
	- By default, every table contains a local route for communication within the VPC
	- Defines outgoing connections
		- 0.0.0.0/0 to Gateway means all internal IPs in the VPC

### Internet Gateway

- Final piece of the puzzle that connects to the internet
- An ip with a fixed bit length of 32 is sent to the gateway in the routing table
- Each gateway has its own IP as well assigned to it in the route table
- Routing Table Entry
	- Outgoing Connection 0.0.0.0/0 | igw-id


### Security Groups

- Act at the instance level
- By default deny all inbound traffic and allow all outbound traffic
- Stateful groups
	- Return traffic is automatically allowed
- Users can only specify allow rules not deny rules
- Rules are evaluated before the decision to allow traffic

### Network ACLs (Access-Control Lists)

- Act at the subnet level
- Has separate inbound & outbound rules
	- Each rule can deny/allow traffic
- By default allow inbound and outbound traffic
	- Custom ACLs however deny all inbound/outbound traffic unless specified
	- Can specifiy both allow/deny rules
	- Evaluated in number order starting from lowest first
- Stateless
	- Return traffic must be explicitly allowed through rules
