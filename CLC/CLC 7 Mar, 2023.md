Module 5: Networking & content Delivery


## Amazon VPC (Virtual Private Cloud)

- Dedicate a section of a cloud to host cloud services
	- Control over your own networking resources
		- Selection of IP range
		- Creation of subnets
		- Configuration of route tables & network gateways
	- Custom network configs
	- Multiple layers of security
- Logically isolated from other VPCs
	- Hosted on a ENI (Elastic Network Interface) which can host multiple VPCs
		- ENI's can be attached/detached to an instance to redirect network traffic
			- Attaching to a new instance also persists old attributes
- VPC dedicated to AWS Account
- Single AWS region / Spans multiple Availability Zones

### Public IP Address 
- Can be IPv4/6
- In cloud context
	- Elastic IP Address is assigned
		- Associated with an AWS Account
		- Can be reallocated
		- Additional Costs (What kind?)
	- Public IPv4
		- Manually assigned through an Elastic IP
		- Auto-Assigned at the subnet level


### Reserved IP Addresses
- Assume a VPC with a IPv4 CIDR Block of 10.0.0.0/16
- 16 Fixed bits therefore 65536 total IP addresses. 2^16
- Some IP are reserved however
	- 10.0.0.0 - Network Address
	- 10.0.0.1 - Internal Communication
	- 10.0.0.2 - DNS resolution
	- 10.0.0.3 - Future Use
	- 10.0.0.255 - Broadcast Address
- CIDR blocks will be 4
	- With 10.0.X.0, where X is 0 to 3
