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
- VPC Subnets (CIDR Type)
	- Range of IP Addresses that divide a VPC
	- Belongs to a single availability zone
	- Can be private or public
	- Address range cannot be changed after creating a VPC
