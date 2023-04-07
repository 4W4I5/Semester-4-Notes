- [ ] Module 4 KMS, slide 65 onwards
- [ ] Module 5: Networking & Content Delivery
- [ ] Module 6: Compute slides 1 to 16
- [ ] Module 7: Storage EBS only
---

# Module 4: AWS IAM (KMS onwards from 65)

## Section 4: Securing Accounts

### Encryption of Data (AWS Cert Manager)

- ##### Encryption of Data at Rest
	- Encryption is done with a secret key
		- AWS KMS manages that secret key
	- Data At Rest
		- Defined as Data stored physically
- ##### Encryption of Data in Transit
	- Data In Transit
		- Data moving across a Network
	- Encryption is done using TLS (Transport Layer Security)
		- Creates a secure tunnel using HTTPS
		- **AWS Certificate Manager**
			- Provides a way to manage, deploy and renew TLS/SSL Certs
	- AWS Services support data in transit encryption

### AWS KMS (Key management system)

- Enables you to
	- Create & Manage encryption keys
	- Control the use of encryption across AWS services and in your apps
- Integrated with CloudTrail to log all key usage to ensure regulatory & compliance needs
- HSMs (Hardware Security Modules) provided by FIPS (Federal Information Processing Standards) to protect the keys physically
- CMKs (Customer Master Keys)
	- Used to
		- Control access to data encryption keys
		- Create new keys
		- Manage access to keys
	- Management of keys
		- AWS-Managed
			- Rotated on a regular basis
			- Used by some AWS services
		- Customer-Managed
			- Full control passed to the user
				- Own responsibility to
					- Rotate
					- Audit
					- Define policies for the key

### AWS Cognito

- Adds the following to your web and mobile application
	- User
		- Sign in
		- Sign Up
		- Access Control
- Scales to millions of users
- Provides
	- Multi-Factor Authentication
	- Secure token exchange
	- Encryption of data in transit or at rest
- Supports 3rd party identity providers known as Federated Identity such as
	- Facebook
	- Google
	- Microsoft Active Directory via Security Assertion Markup Language (SAML 2.0)
		- Allows single sign-on (SSO)
- Compliant with healthcare & merchant companies

### AWS Shield

- DDOS Protection Service
- Available for all AWS applications and services
- Provides always-on detection and automatic inline mitigations
- Standard Shield
	- Integrated into
		- CloudFront
- Advanced Shield
	- Paid service
	- Protects against advanced attacks
		- Multivector
		- Specific App target
		- API Endpoints
	- Used to minimize application downtime and latency
	- Protects apps that run on
		- EC2
		- ELB (Elastic Load Balancing)
		- CloudFront
		- Global Accelerator
		- Route 53
	- To contact DDOS Response team an Enterprise or Business support from AWS Support will be required

## Section 5: Securing data on AWS

### Securing S3 Buckets & Objects

- New S3 Buckets are private & protected by default
- Permissions following the principle of least privilege are used alongside S3 Encryption to allow access to the data stored in the bucket
- Tools
	- S3 Block Public Access
		- Blocks all public access to S3 Bucket
		- Overrides other policies or permissions
	- IAM Policies
		- Specify which user or role can access which bucket/object
		- More granular and specify permissions for specific actions
	- Bucket Policies
		- Define access to specific buckets/objects.
		- Used when IAM cannot authenticate a user
		- Attached directly to a S3 Bucket, Applied to all requests made to that bucket
		- Grant access to
			- Public
			- Anonymous
			- AWS accounts
	- Access Control Lists
		- Older way of IAM
		- Written in XML
		- Differences b/w ACL & IAM
			- Scope
				- ACLs are attached to individual objects
				- IAMs are attached to IAM users, groups or roles
			- Granularity
				- ACLs grant/deny access to individual objects in a bucket
				- IAMs specify permissions for specific actions on a bucket or object
			- Level of Control
				- Less granular than IAM
				- IAMs can specify fine-grained permissions for users & groups, restrict access based on IP address or time of the day & manage permissions across multiple AWS services
			- Access Management
				- ACLs provide access to a small number of trusted accounts or make an object publicly accessible
				- IAMs manage access for a large number of users, groups or roles within you AWS account
	- AWS Trusted Advisor
		- Provides recommendations for optimizing AWS resources
		- Offers guidance for securing S3 Buckets & Objects
			- Analyze S3 config and provide recommendations based on industry practices and AWS security guidelines
			- Provides guidance on configuring S3 bucket policies and/or ACLs
			- Recommends enabling S3 server-side encryption and configure versioning, protecting against data loss & unauthorized access
		- Alerts to
			- any S3 buckets that are not in spec of the AWS security guidelines or out of date
			- buckets that are publicly accessible or have open permissions

## Section 6: Working to Ensure Compliance

### AWS compliance programs

- Customers are subject to many different security & compliance regulations and requirements
- Engages with certifying bodies and independent auditors to provide customer with detailed information about the policies, processes, and controls that are established and are operated by AWS
- These are broadly categorized
	- Certifications & Attestations
		- Assessed by a third party, independent auditor
		- Example
			- ISO 27001
			- ISO 27017
			- ISO 27018
			- ISO/IEC 9001
	- Laws, Regulations, & Privacy
		- AWS provides security features and legal agreements to support compliance
		- Example
			- EU general data protection regulation (GDPR)
			- HIPAA
	- Alignments & Frameworks
	- Industry or Function specific or compliance requirements
		- Examples
			- Center for internet security (CIS)
			- EU-US Privacy Shield certified

#### AWS Config

- Simplify compliance auditing and security analysis
- Assess, Audit and Evaluate the configurations of AWS Resources
- Use for continuous monitoring of configs
- Automatically evaluate recorded configs vs desired configs
- Review config changes
- View detailed config histories

#### AWS Artifact

- Resource for compliance-related information
- Provide access to security and compliance reports
	- Select online agreements
- Can access example downloads
	- AWS ISO certs
	- Payment card industry (PCI) and Service Organization Control (SOC) reports
- Access AWS Artifacts directly from the AWS management console

---

# Module 5: Networking & Content Delivery

## Section 2: AWS VPC

### Amazon VPC (Virtual Private Cloud)

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
			- Attaching to a new VPC also persists old attributes
- VPC dedicated to AWS Account
- Single AWS region / Spans multiple Availability Zones

#### Public IP Address

- Can be IPv4/6
- In cloud context
	- Elastic IP Address is assigned
		- Associated with an AWS Account
		- Can be reallocated
		- Additional Costs (What kind?)
	- Public IPv4
		- Manually assigned through an Elastic IP
		- Auto-Assigned at the subnet level

#### Reserved IP Addresses

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
CIDR
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

## Section 3: VPC Networking

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

### NAT Gateway

- Used to communicate with the private subnet
	- Via the private route table which routes packets from the NAT gateway to the public subnet
- Restricts data flow to one direction only therefore no other way of access is provided to the private subnet
- To connect a private subnet with another network's private subnet we need to use Virtual Private Network (VPN)
	- A tunnel is created therefore any traffic inside is unknown to the internet and therefore private
	- Tunnel Gateway is responsible for encrypting/decrypting traffic
	-
- Private subnet can not communicate with the outside world
	- To provision for outside comms, a private routing table is used
	- This means that the Private subnet is routed to the NAT gateway which is routed to the Public route table which is then routed to the Internet Gateway
- Routing Table Entry
	- 0.0.0.0/0 | nat-gw-id

### AWS Site-To-Site VPN

- NFV version of a VPN that allows private-private subnet interactions
	- Spawns its own Virtual Gateway to communicate with off-site private subnets
- On cloudside
	- Setup inside VPC with a virtual gateway device pointing to the customer gateway
- Route using Virtual Gateway (vgw-id)
- Allows to connect the private subnet to say a data center off site using a VPN connection over the internet
- generally used as a backup connection to AWS Direct Connect

### AWS Direct Connect (AWS-Specific)

- Only provided by AWS
	- AWS buys a connection with dedicated bandwidth bought from ISP to get a direct connection to the internet
	- Essentially a cable that AWS sells
- Amazon buys infrastructure to provide direct connections. Bypasses the internet entirely
- Same as site-to-site VPN however due to infrastructure costs, its costs more than the site to site VPN
- Requires more setup time
- Used for large-scale data transfer, high-volume workloads and applications that require low latency and bandwidth

## VPC Peering

- Restrictions
	- IP spaces cannot overlap
		- Prerequired to separate IP address spaces as that would result in IP conflicts
	- Transitive peering is not allowed
		- If A & B are peered and B & C are peered. A & C are not peered
		- Requires a direct peer link to establish a peer connection
	- You can only have one peering resource between the same two VPCs
- Used in AWS to allow communication b/w two VPCs in the cloud
	- Can be used within an AWS account, b/w AWS accounts, or b/w AWS Regions
- After establishing a connection
	- Modify the routing table to target traffic to the Peering connection's IP and the destination IP will be the host IP
- VPC can also be chained to each other to allow communication b/w
	- your own AWS account via VPC Sharing
		- they wont need to create their own VPC but can deploy their own AWS resources and will have access to your VPC
		- Isolated resources from your account
	- multiple AWS accounts
	- multiple AWS Regions
- Restrictions
	- CIDR IP spaces cannot overlap
	- Transitive peering is not allowed
	- Only one peering resource is established b/w two VPCs
- Routing Table Entry
	- IP of target VPC | pcx-id

### VPC Endpoints

- Two types
	- Interface endpoints
		- Used to connect services via Private IP
		- Powered by AWS PrivateLink
			- Use of ENIs to route traffic to and from endpoint
	- Gateway endpoints
		- Used to connect services via Public IP
		- Amazon S3 & Amazon DynamoDB
		- Powered by VPC Gateway
			- Allow to route over a private connection
- Points
	- Allow to privately connect VPC to supported AWS Services without requiring a gateway, NAT, VPN connection or Internet gateway
	- Keeps traffic within the AWS Network
	-
- Routing Table Entry
	- ID of AWS Resource | vpcep-id

### AWS Transit Gateway

- Bypass Sharing and Peering
- A middleman that directly Peers all connected VPCs, provides a central point of management
	- Kind of acts like a router but in software
- Do not start with a Transit Gateway at the start, Try to use AWS VPC Sharing and AWS VPC Peering
- Supports
	- VPC Attachments
	- VPN Connections
	- Direct Connect Gateway
	- Peeing Connections
	- VPC Sharing
- Allows
	- Connect VPCs across different regions & accounts, sharing resources with them
	- Routing control using a Routing Table for VPCs and on-premises networks
	- Network Segmentation, create multiple route tables and associating with different VPCs
	- Centralized Network traffic and management

### AWS Route 53

- DNS Service
- 53 is the port number for DNS servers
- Features
	- Enables domain name registration
	- Features Traffic flow
	- Check health of resources
	- Connects to user to infrastructure inside AWS and also outside AWS
- Supported Routing Types
	- Simple
		- Used in single-server environments
		- Use for a single resource that performs a given function for your domain (such as a web server that serves content for the example.com website).
	- Weighted Round Robin
		- Assign weights to resource records sets to specify the frequency
			- Its a turn by turn system that gives weights to each resource
			- Itll wait till first resource is full of requests before proceeding to send requests to the next one
		- Not a form of load balancing, however it is a routing mechanism where traffic flow is dictated in a route table
		- Each server is assigned a weight value. 
		- Ensures that each server receives a fair share of traffic based on its weight, and it is useful for load balancing when some servers have a higher capacity or processing power than others.
	- Latency
		- Improve global applications 
		- Works by routing packets thru the path of lowest latency
		- Route AWS endpoints depending on the lowest time in flight
	- Geolocation
		- Localized Content
		- Route based on location of users
		- Within location
	- Geoproximity
		- Use when you want to route traffic based on the location of your resources and, optionally, shift traffic from resources in one location to resources in another. 
		- Closest IP is returned based on location of server/resources
	- Failover
		- Fail over to backup site if primary site is unreachable
		- Active-Passive Failover
		- Redirects to alternate locations based on availibility
	- Multivalue Answer
		- Respond to DNS queries with upto 8 healthy records selected at random


### AWS CloudFront


---

# Module 6: Compute

Categories of Compute Services
- Virtual Machines | Instance based
	- AWS EC2
- Serverless computing
	- AWS Lambda
		- Called serverless as it just runs code as it is given
			- Called a lambda function
			- Pay only for the time the code was run
		- AWS manages the infrastructure
		- Scheduled run of code or by run of event
- Container-Based computing
	- Diff types
		- AWS ECS (Amazon Elastic Container Service)
			- Manages running multiple docker containers on a single OS host
		- AWS EKS (Amazon Elastic Kubernetes Service)
			- Manages running multiple Kubernetes containers on multiple docker hosts
		- AWS ECR (Amazon Elastic Container Registry)
			- Store, manage and deploy docker containers
		- AWS Fargate
			- Requires administrative overhead but provides more control
	- Used to spin up and run jobs more quickly
- Platform-As-A-Service
	- AWS Beanstalk
		- Used for WebApps
		- AWS automatically handles the deployment. All you need is to upload the code

### Amazon EC2

- Provides VMs
	- Allows user spec of hardware to use for a specific instance
- Can run into any availability zone
- Use of AMI, Amazon Machine Images
	- Custom images can also be used either from the community or your own
	- Amazon Marketplace can also provide 3rd party AMIs
	- Besides these two, Amazon provides quick start AMIs
- Can manage traffic to active instances
- Instance Types determine RAM, CPU, Storage & Network performance
	- General purpose
	- Compute Optimized
	- Memory Optimized
	- Storage Optimized
	- Accelerated Computing
- Instance Type Naming
	- t3.large
		- Here 't' is the family of the instance
		- 3 is the generation number 
		- large is the size of the instance
- Use case based instances
	- General Purpose
		- A1, M4, M5, T2, T3
		- Broad use case
	- Compute Optimized
		- C4, C5
		- High performance use case
		- High CPU workloads expected
	- Memory Optimized
		- R4, R5, X1, Z1
		- In-Memory Databases
		- Large amounts of RAM required
		- Faster memory processing expected
	- Storage Optimized
		- D2, H1, I3
		- Distributed file systems or Databases
		- Large storage volumes provisioned and bandwidth improved
	- Accelerated Computing
		- F1, G3, G4, P2, P3
		- GPU-Acceleration expected
		- AI or machine learning workload expected

---
# Module 7: Storage
## Amazon EBS (Elastic Block Storage)

- Uses
	- Root/Boot volumes & storage for EC2
	- Data storage within a file system
	- Database hosts
	- Enterprise Application
- Comes in two Types
	- SSD & HDD
		- Which are also in two types divided on IOPS and Bandwidth
		- Note that HDD cannot be used as boot volumes
	- Ascending order of quality (Complete from slides)
		- Cold (HDD) 250 IOPS
			- Used for data that is infrequently accessed, throughput oriented for large volumes
			- Good when looking for low storage costs
			- Cannot be boot volume
		- Throughput-Optimized (HDD) 500 IOPS
			- Streaming workloads that require consistent, fast throughput at a low price
			- Used
				- Big data
				- Data warehouses
				- Log processing
			- Cannot be a boot volume
		- General Purpose (SSD) 16k IOPS
			- Recommended for most workloads
			- Used
				- Virtual Desktops
				- Low latency interactive applications
				- Dev and test environments
		- Provisioned IOPS (SSD) 64k IOPS
			- Critical businesses that require sustained IOPS or more than 16k IOPS
			- Large Database workloads
- Features
	- MAX volume size capped at 16TiB or roughly 17TB
	- Enables you to create individual storage volumes & attach them to an EC2 instance
	- Block-Level Storage
	- All volumes persist independent from the instance
	- Volumes are auto-replicated within its availability zone
	- Backed up automatically to S3 using snapshots'
	- Recreate a new volume at any time
	- Encrypted EBS volumes at no additional cost
	- Change to diff types or scale capacity
	- Snapshots allows to revert back in time
		- Can be stored locally, on a EBS or on a S3 Bucket but generally stored in S3
- Pricing
	- Volume
		- Direct cost of storage provision in GB/Month until released
	- Snapshots
		- Added Cost of Amazon EBS snapshots to S3 is per GB-Month of data stored
	- Data Transfer
		- Inbound data transfer is free
		- Outbound data transfer across regions incurs charges
		- Copying EBS snapshots incurs charges across regions after which standard EBS snapshot charges apply for storage in the destination region
	- According to IOPS
		- Cold (HDD)
			- Charged by number of requests to volume
		- Throughput-Optimized (HDD)
			- Charged by number of requests to volume
		- General Purpose (SSD)
			- Charged by amount of GB per month until storage is released
		- Provisioned IOPS (SSD)
			- Charged by amount of IOPS provisioned x percentage of days that you provision for the month
