- [x] [[#Module 1 Introduction to CC]]
- [x] [[# Module 2: Cloud Economics & Billing]]
- [x] [[#Module 3 Global Infrastructure]]
- [x] [[#Module 4 AWS IAM]]
- [x] [[#Module 5 Networking & Content Delivery]]
- [ ] [[#Module 6 Compute]]
- [ ] [[#Module 7 Storage]]
- [ ] [[#Module 8 Databases]]
- [x] [[#Module 9 Cloud Architecture]]
- [x] [[#Module 10 AutoScaling & Monitoring]]

# Module 1: Introduction to CC

- ### Section 1: Introduction To Cloud Computing
	- NIST DEF
		- Enables Ubiquitous, Convenient, On-Demand Network Access to a Shared Pool of Configurable Computing Resources that can be Rapidly Provisioned and Released with Minimal Management effort or service provider interaction
	- Multi-Tenancy
		- Use of same resources by multiple consumers that may belong to the same or different organization\
		- Private Cloud tenancy includes sharing an onsite datacenter w multiple business units i.e the organization manages the hardware and grants more individual level control to its tenants
		- Public Cloud tenancy includes sharing resources b/w multiple organizations
	- Cloud Computing Models
		- Not required for services to fit these models, as this is a reference model
		- IaaS
			- Cloud Based Services over Internet
			- Access to networking, computational and storage resources
			-
		- PaaS
			- Tools over Internet
			- Development/Application Platforms
			- Examples
				- Databases
				- VMs
				- File Servers
		- SaaS
			- Product over Internet
	- Cloud Deployment Models
		- Public
			- Accessible by all, Off-Site, Managed by 3rd party provider and intended for the public or a large industry group
		- Private
			- Trusted access only, On-Site, Managed by organization and intended for a single organization too
			- Sought for ability to dedicate resources with more control
		- Hybrid
			- Accessible by access only and all, On/Off-site, Managed by both organization/3rd party provider.
			- Consists of two or more Private/Public Clouds bound together by tech that enables data/application portability i.e. cloud bursting (load balancing b/w clouds)
- ### Section 2: Advantages of Cloud Computing
	- Pay only for the resources you consume (variable cost vs upfront capital expenditure)
	- Economies of scale achieved by aggregate of all users
	- Scaling on demand
	- Speed and flexibility - changes are software level, not hardware like traditional computing
	- Lower overhead due to not maintaining hardware and data centers
	- Data centers are global, like a company's customer base
- ### Section 3: Intro to AWS
	- What is AWS
		- Secure Cloud Platform, with broad set of global products
		- Offers flexibility
		- Pay as u go
	- Ways to interact with AWS
		- AWS Management Console
		- AWS CLI
		- AWS SDK
- ### Section 4: AWS CAF
	- **Business Capabilities**
		- Business (IT aligned with business needs)
			- IT Finance & Strategy
			- Benefits Realization
			- Business Risk Management
		- People (Training, Staffing & Organizational Changes)
			- Resource, Incentive, Career, Training and Organizational Change Management
		- Governance (Align IT Strat & Goals with Business Strat & Goals)
			- Portfolio, Program, Project, Business Performance and License Management
	- **Technical Capabilities**
		- Platform (Describe Architecture of target state environment in detail)
			- Provisioning of Compute, Network, Storage and Database resources
			- Systems and Solution Architecture
			- Application Dev
		- Security (Meet org security objectives)
			- Identity & Access Management
			- Detective Control
			- Infrastructure Security
			- Data Protection
			- Incident Response
		- Operations (Define day2day, quarter2quarter & year2year business)
			- Service
			- App performance monitor
			- Resource inventory
			- Release management
			- Reporting & Business continuity
			- IT Service

# Module 2: Cloud Economics & Billing

- ### Section 1: Fundamentals of Pricing
	- **AWS Pricing Model**
		- Compute, charged by use time, varies by instance
		- Storage, charged per GB
		- Data Transfer, outbound transfers are aggregated and charged per GB, inbound transfers and data transfers between services in the same AWS Region typically have no charge
	- **Paying for AWS**
		- Pay for what you use
		- Reserve and save up to 75% versus On-Demand
		    - All Upfront Reserved Instance (AURI) -> Large Discount
		    - Partial Upfront Reserved Instance (PURI) -> Lower Discount
		    - No Upfront Payments Reserved Instance (NURI) -> Smallest Discount
		- Scale and save as usage increases
		    - Tiered pricing for services like S3, EBS, EFS
		- Save as AWS grows
		- Custom Pricing
		    - Meet varying needs through custom pricing.
		    - Available for high-volume projects with unique requirements.
		- Free services (might be charged when used alongside other services)
			- Amazon VPC
			- Elastic Beanstalk
			- Auto Scaling
			- AWS CloudFormation
			- AWS Identity and Access Management
- ### Section 2: Total Cost of Ownership
	- **Considerations**
		1. Server Costs
		    - Hardware: Server, rack chassis power distribution units (PDUs), top-of-rack (TOR) switches, and maintenance
		    - Software: Operating system (OS), virtualization licenses, and maintenance
		    - Facilities: Space, power, and cooling
		2. Storage Costs
		    - Hardware: Storage disks, storage area network (SAN) or Fibre Channel (FC) switches
		    - Storage administration costs
		    - Facilities: Space, power, and cooling
		3. Network Costs
		    - Network Hardware: Local area network (LAN) switches, load balancer bandwidth costs
		    - Network administration costs
		    - Facilities: Space, power, and cooling
		4. IT Labor Costs
		    - Server administration costs
- ### Section 3: AWS Organizations | AWS Billing & Cost management
	- Definition
		- Consolidate multiple AWS Accounts into a centrally manageable organization
		- Includes Account Management and consolidated billing capabilities that enable you to better meet the budgetary, security, and compliance needs of a business.
	- Key Features & benefits
		- Policy based account management
		- Group based account management
		- Application programming interfaces (APIs) that automate account management
		- Consolidated billing
	- Security
		- Control access with AWS Identity and Access Management (IAM)
		- IAM policies enable you to allow or deny access to AWS services for users, groups, and roles.
		- Service control policies (SCPs) enable you to allow or deny access to AWS services for individuals or group accounts in an organizational unit (OU).
- ### Section 4: AWS Billing & Cost Management
	- Definition
		- Used to pay AWS Bill, monitor usage & analyze and control your costs
	- Tools
		- AWS Budgets
			- It gives you the ability to set custom budgets that alert you when your costs or usage exceed (or are forecasted to exceed) your budgeted amount. You can also use it to set reservation utilization or coverage targets and receive alerts when your utilization drops below the threshold you define.
		- AWS Cost and Usage Report
			- Tracks your AWS usage and provides estimated charges associated with your account.
		- AWS Cost Explorer
			- Visualize, understand, and manage AWS costs and usage over time.
- ### Section 5: Technical Support
	- Definition
		- Provides support plans
		- All plans offer 24/7 access to customer service, documentation, whitepapers and support forums
	- AWS Services
		- Proactive Guidance
			- Technical Account Manager (TAM)
		- Best Practices
			- AWS Trusted Advisor
		- Account Assistance
			- AWS Support Concierge
	- Support Plans
		- Basic Support
			- Resource Center access, Service Health Dashboard, product FAQs, discussion forums, and support for health checks
		- Developer Support
			- Support for early development on AWS
		- Business Support
			- Customers that run production workloads
		- Enterprise Support
			- Customers that run business and mission-critical workloads
---

# Module 3: Global Infrastructure

- ## Section 1: Global Infrastructure breakdown
	- AWS Regions
		- Definition
			- Each region is a geographical area
			- Data replication across Regions is controlled by you.
			- Communication between Regions uses AWS backbone network infrastructure.
			- Each Region provides full redundancy and connectivity to the network.
			- A Region typically consists of two or more Availability Zones
		- Considerations when selection a region
			- Laws - Data governance and legal requirements
			- Proximity - Select regions close to your customers for reduced latency
			- Availability - Some services are region locked
			- Cost - Cost varies by region
		- Trivia
			- Availability Zones consist of discrete data centers
			- They are interconnected with other Availability Zones by using high-speed private networking
			- They are designed for fault isolation
			- You choose your Availability Zones but AWS recommends replicating data and resources across Availability Zones for resiliency.
	- AWS Datacenters
		- Trivia
			- AWS data centers are designed for security. Each data center has redundant power, networking, and connectivity, and is housed in a separate facility.
			- Data centers are where the data resides and data processing occurs. A data center typically has 50,000 to 80,000 physical servers
			- AWS provides a global network of 187 Points of Presence locations
			- Consists of 176 edge locations - where end users access services located at AWS
			- 11 Regional edge caches - cache copies of your infrequent content close to your users
			- Used with **Amazon CloudFront** - a fast content delivery network (CDN) service that securely delivers data, videos, applications, and APIs to customers globally with low latency, high transfer speeds, all within a developer-friendly environment.
		- AWS InfraStructure Features
			- Elasticity and scalability - dynamically adapts to capacity and growth needs
			- Fault-tolerance - Continues operating properly in the presence of a failure due to built-in redundancy of components
			- High availability - High operational performance with minimized downtime and no human intervention
- ## Section 2: AWS Services & Service Categories
	- Foundation Services
	- Service Categories
		- AWS Storage Services
			- [Amazon Simple Storage Services (S3)](https://aws.amazon.com/s3/) - Object storage service that offers industry-leading scalability, data availability, security, and performance.
			- [Amazon Elastic Block Storage (EBS)](https://aws.amazon.com/ebs) - An easy to use, high performance block storage service designed for use with Amazon Elastic Compute Cloud (EC2) for both throughput and transaction intensive workloads at any scale.
			- [Amazon Elastic File System (EFS)](https://aws.amazon.com/efs/) - A simple, scalable, fully managed elastic NFS file system for use with AWS Cloud services and on-premises resources.
			- [Amazon Simple Storage Service Glacier](https://aws.amazon.com/glacier/) - A secure, durable, and extremely low-cost Amazon S3 cloud storage classes for data archiving and long-term backup.
		- AWS Compute Services
			- [Amazon EC2](https://aws.amazon.com/ec2/) - A web service that provides secure, resizable compute capacity in the cloud.
			- [Amazon EC2 Auto Scaling](https://aws.amazon.com/ec2/autoscaling/) - Helps to maintain application availability and allows you to automatically add or remove EC2 instances according to conditions you define.
			- [Amazon Elastic Container Services (ECS)](https://aws.amazon.com/ecs/) - A fully managed container orchestration service.
			- [Amazon EC2 Container Registry (ECR)](https://aws.amazon.com/ecr/) - A fully-managed Docker container registry that makes it easy for developers to store, manage, and deploy Docker container images.
			- [AWS Elastic Beanstalk](https://aws.amazon.com/elasticbeanstalk/) - An easy-to-use service for deploying and scaling web applications and services developed with Java, .NET, PHP, Node.js, Python, Ruby, Go, and Docker on familiar servers such as Apache, Nginx, Passenger, and IIS.
			- [AWS Lambda](https://aws.amazon.com/lambda/) - Lets you run code without provisioning or managing servers.
			- [Amazon Elastic Kubernetes Services (EKS)](https://aws.amazon.com/eks/) - A fully managed [Kubernetes](https://en.wikipedia.org/wiki/Kubernetes) service.
			- [AWS Fargate](https://aws.amazon.com/fargate/) - A serverless compute engine for containers that works with both Amazon Elastic Container Service (ECS) and Amazon Elastic Kubernetes Service (EKS).
		- AWS Database Services
			- [Amazon Relational Database Service (RDS)](https://aws.amazon.com/rds/) - Makes it easy to set up, operate, and scale a relational database in the cloud.
			- [Amazon Aurora](https://aws.amazon.com/rds/aurora/) - A MySQL and PostgreSQL compatible relational database built for the cloud, that combines the performance and availability of traditional enterprise databases with the simplicity and cost-effectiveness of open source databases.
			- [Amazon Redshift](https://aws.amazon.com/redshift/) - A fully managed, petabyte-scale data warehouse service in the cloud.
			- [Amazon DynamoDB](https://aws.amazon.com/dynamodb/) - A key value and document database that delivers single-digit millisecond performance at any scale.
		- Networking and Content Delivery Services
			- [Amazon VPC](https://aws.amazon.com/vpc/) - Lets you provision a logically isolated section of the AWS Cloud where you can launch AWS resources in a virtual network that you define.
			- [Elastic Load Balancing](https://aws.amazon.com/elasticloadbalancing/) - Automatically distributes incoming application traffic across multiple targets, such as Amazon EC2 instances, containers, IP addresses, and Lambda functions.
			- [Amazon CloudFront](https://aws.amazon.com/cloudfront/) - A fast content delivery network (CDN) service that securely delivers data, videos, applications, and APIs to customers globally with low latency, high transfer speeds, all within a developer-friendly environment.
			- [AWS Transit Gateway](https://aws.amazon.com/transit-gateway/) - A service that enables customers to connect their Amazon Virtual Private Clouds (VPCs) and their on-premises networks to a single gateway.
			- [Amazon Route 53](https://aws.amazon.com/route53/) - A highly available and scalable cloud Domain Name System (DNS) web service.
			- [AWS Direct Connect](https://aws.amazon.com/directconnect/) - A cloud service solution that makes it easy to establish a dedicated network connection from your premises to AWS.
			- [AWS VPN](https://aws.amazon.com/vpn/) - Lets you establish a secure and private encrypted tunnel from your network or device to the AWS global network.
		- Security, Identity, and Compliance Services
			- [AWS Identity and Access Management (IAM)](https://aws.amazon.com/iam/) - Enables you to manage access to AWS services and resources securely. You can create and manage AWS users and groups, and use permissions to allow and deny their access to AWS resources. IAM is a feature of your AWS account offered at no additional charge.
			- [AWS Organizations](https://aws.amazon.com/organizations/) - helps you centrally govern your environment as you grow and scale your workloads on AWS.
			- [Amazon Cognito](https://aws.amazon.com/cognito/) - Lets you add user sign-up, sign-in, and access control to your web and mobile apps quickly and easily.
			- [AWS Artifact](https://aws.amazon.com/artifact/) - A central resource for compliance related information that matters to you.
			- [AWS Key Management Service (KMS)](https://aws.amazon.com/kms/) - Makes it easy for you to create and manage cryptographic keys and control their use across a wide range of AWS services and in your applications.
			- [AWS Shield](https://aws.amazon.com/shield/) - A managed Distributed Denial of Service (DDoS) protection service that safeguards applications running on AWS.
		- Cost Management Services
			- [AWS Cost and Usage Report](https://aws.amazon.com/aws-cost-management/aws-cost-and-usage-reporting/) - contains the most comprehensive set of AWS cost and usage data available, including additional metadata about AWS services, pricing, and reservations (e.g., Amazon EC2 Reserved Instances (RIs)).
			- [AWS Budgets](https://aws.amazon.com/aws-cost-management/aws-budgets/) - gives you the ability to set custom budgets that alert you when your costs or usage exceed (or are forecasted to exceed) your budgeted amount.
			- [AWS Cost Explorer](https://aws.amazon.com/aws-cost-management/aws-cost-explorer/) - an easy-to-use interface that lets you visualize, understand, and manage your AWS costs and usage over time.
		- AWS Management and Governance Services
			- [AWS Management Console](https://aws.amazon.com/console/) - A secure, easy-to-access, web-based portal for AWS.
			- [AWS Config](https://aws.amazon.com/config/) - A service that enables you to assess, audit, and evaluate the configurations of your AWS resources.
			- [Amazon CloudWatch](https://aws.amazon.com/cloudwatch/) - A monitoring and observability service that provides you with data and actionable insights to monitor your applications, respond to system-wide performance changes, optimize resource utilization, and get a unified view of operational health. You can use it to detect anomalous behavior in your environments, set alarms, visualize logs and metrics side by side, take automated actions, troubleshoot issues, and discover insights.
			- [AWS Auto Scaling](https://aws.amazon.com/autoscaling/) - monitors your applications and automatically adjusts capacity to maintain steady, predictable performance at the lowest possible cost.
			- [AWS Command Line Interface (CLI)](https://aws.amazon.com/cli/) - a unified tool to manage your AWS services. With just one tool to download and configure, you can control multiple AWS services from the command line and automate them through scripts.
			- [AWS Trusted Advisor](https://aws.amazon.com/premiumsupport/technology/trusted-advisor/) - An online tool that provides you real time guidance to help you provision your resources following AWS best practices.
			- [AWS Well-Architected Tool](https://aws.amazon.com/well-architected-tool/) - Helps you review the state of your workloads and compares them to the latest AWS architectural best practices.
			- [AWS CloudTrail](https://aws.amazon.com/cloudtrail/) - A service that enables governance, compliance, operational auditing, and risk auditing of your AWS account.



---

# Module 4: AWS IAM

## Section 1: AWS Shared Responsibility Model

- Customer Security
	- Amazon Elastic Compute Cloud (Amazon EC2) instance operating system - Including patching, maintenance
	- Applications - Passwords, role-based access, etc.
	- Security group configuration
	- OS or host-based firewalls - Including intrusion detection or prevention systems
	- Network configurations
	- Account management - Login and permission settings for each user
- AWS Security
	- Physical security of data centers - Controlled, need-based access
	- Hardware and software infrastructure - Storage decommissioning, host operating system (OS) access logging, and auditing
	- Network infrastructure - Intrusion detection
	- Virtualization infrastructure - Instance isolation
- Service Characteristics and Security
	- Infrastructure as a service (IaaS)
		- Customer has more flexibility over configuring networking and storage settings
		- Customer is responsible for managing more aspects of the security
		- Customer configures the access controls
	- Platform as a service (PaaS)
		- Customer does not need to manage the underlying infrastructure
		- AWS handles the operating system, database patching, firewall configuration, and disaster recovery
		- Customer can focus on managing code or data
	- Software as a service (SaaS)
		- Software is centrally hosted
		- Licensed on a subscription model or pay-as-you-go basis.
		- Services are typically accessed via web browser, mobile app, or application programming interface (API)
		- Customers do not need to manage the infrastructure that supports the service

## Section 2: Identity & Access Management (IAM)

- IAM Uses
	- **Manage IAM Users and their access:** You can create Users and assign them individual security credentials (access keys, passwords, and multi-factor authentication devices). You can manage permissions to control which operations a User can perform.
	- **Manage IAM Roles and their permissions:** An IAM Role is similar to a User, in that it is an AWS identity with permission policies that determine what the identity can and cannot do in AWS. However, instead of being uniquely associated with one person, a Role is intended to be assumable by anyone who needs it.
	- **Manage federated users and their permissions:** You can enable identity federation to allow existing users in your enterprise to access the AWS Management Console, to call AWS APIs and to access resources, without the need to create an IAM User for each identity.
- Components of IAM
	- **IAM User:** A person or application that can authenticate with an AWS account. When you define an IAM user, you select what types of access the user is permitted to use.
		- Programmatic Access
		    - Authenticate using Access Key ID and Secret Access Key
		    - Provides AWS CLI and AWS SDK access
		- AWS Management Console Access
		    - Authenticate using Account ID or Alias, or Username and Password
		    - Can enable Multi-Factor Authentication (MFA)
	- **IAM Group:** A collection of IAM users that are granted identical authorization.
		- A user can belong to multiple groups
		- There is no default group
		- Groups cannot be nested
	- **IAM Policy:** The document that defines which resources can be accessed and the level of access to each resource.
		- Permissions determine which resources and operations are allowed.
		    - All permissions are implicitly denied by default.
		    - If something is explicitly denied, it is never allowed.
		- Two Types of Policies:
		    1. Identity Based
		        - Attach a policy to any IAM entity - user, group, or role
		        - Policies specify actions that may or may not be performed by the entity
		        - Policies and entities have a many-to-many relationship
		        - When the policy is updated, the changes to the policy are immediately apply against all Users and Groups that are attached to the policy.
		    2. Resource Based
		        - Attached to a resource (such as an S3 bucket)
		        - Specifies who has access to the resource and what actions they can perform on it
		        - The policies are inline only, not managed. An inline policy is assigned to just one User or Group. Inline Policies are typically used to apply permissions for one-off situations.
		        - Resource-based policies are supported only by some AWS services
	- **IAM Role:** Useful mechanism to grant a set of permissions for making AWS service requests.
		- Similar to an IAM user: Attach permissions policies to it
		- Different from an IAM user: Not uniquely associated with one person, intended to be assumable by a person, application, or service
		- Role provides temporary security credentials
	- **Principle of Least Privilege:** The practice of limiting access rights for users to the bare minimum permissions they need to perform their work. Under POLP, users are granted permission to read, write or execute only the files or resources they need to do their jobs

## Section 3: Securing a New AWS Account

Best practice: Do not use the AWS account root user except when necessary. Access to the account root user requires logging in with the email address and password that you used to create the account.

1. Stop using the account root user as soon as possible
    1. While you are logged in as the account root user, create an IAM user for yourself. Save the access keys if needed.
    2. Create an IAM group, give it full administrator permissions, and add the IAM user to the group.
    3. Disable and remove your account root user access keys, if they exist.
    4. Enable a password policy for users.
    5. Sign in with your new IAM user credentials.
2. Enable multi-factor authentication (MFA)
3. Use AWS CloudTrail
    - CloudTrail tracks user activity on your account. It logs all API requests to resources in all supported services your account.
    - Basic AWS CloudTrail event history is enabled by default and is free. It contains all management event data for the last 90 days of account activity (this can be extended beyond 90 days)
4. Enable a billing report, such as the _AWS Cost and Usage Report_

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

### AWS Organizations

- Security Features of AWS Organizations
	- Group AWS accounts into organizational units (OUs) and attach different access policies to each OU.
	- Integration and support for IAM. Permissions to a user are the intersection of what is allowed by AWS Organizations and what is granted by IAM in that account.
	- Use service control policies to establish control over the AWS services and API actions that each AWS account can access

#### Service Control Policies

- Service control policies (SCPs) offer centralized control over accounts. Limit permissions that are available in an account that is part of an organization.
- Ensures that accounts comply with access control guidelines.
- SCPs are similar to IAM permissions policies – They use similar syntax, but an SCP never grants permissions. Instead, SCPs specify the maximum permissions for an organization.

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

## Section 1: CIDR Stuff (SKIPPED)

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
		- Redirects to alternate locations based on availability
		- Used
			- when secondary IP of a maintenance HTML page is returned if load balancer is down
	- Multivalue Answer
		- Respond to DNS queries with upto 8 healthy records selected at random

### AWS CloudFront

- CDN Service
- AWS's Global network of edge locations and regional edge caches
	- Edge Locations: Network of data centers used to serve popular content
	- Regional Edge Caches: A middleman server to cache content based on location, used for less popular content
- Pay as you go pricing
	- Data Transfer Out
		- Charged for volume of data in GB transferred out from Amazon CloudFront edge location to the internet or to your origin
	- HTTP(s) Requests
		- Charged from number of HTTP requests
	- Dedicated IP custom SSL
		- 600$ per month for a custom SSL cert that is associated with one or more cloudfront distributions that use the dedicated IP version of custom SSL certs
	- Invalidation Requests
		- Request to invalidate data, basically remove old data from the internet
		- 1000 invalidation requests are allowed after which 0.005$ is charged per path

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

---

# Module 8: Databases

---

# Module 9: Cloud Architecture

- ## Section 1: AWS Well-Architected Framework
- ## Section 2: Reliability & Availability
	- ### **Reliability**
		- A measure of your system’s ability to provide functionality when desired by the user
		- System includes all system components: hardware, firmware, and software
		- Probability that your entire system will function as intended for a specified period
		- Mean time between failures (MTBF) = total time in service/number of failures
	- ### Metrics
		- Mean Time to Failure (MTTF)
		- Mean Time to Repair (MTTR)
		- Mean Time Between Failures (MTBF) = MTTF + MTTR
	- ### Availability
		- Normal operation time / total time
		- A percentage of uptime (for example, 99.9 percent) over time (for example, 1 year)
		- Number of 9s – Five 9s means 99.999 percent availability
	- ### High Availability
		- System can withstand some measure of degradation while still remaining available
		- Downtime is minimized
		- Minimal human intervention is required
	- ### Availability Factors
		- Fault tolerance: The built-in redundancy of an application's components and its ability to remain operational.
		- Scalability: The ability of an application to accommodate increases in capacity needs without changing design.
		- Recoverability: The process, policies, and procedures that are related to restoring service after a catastrophic event.
- ## Section 3: AWS Trusted Advisor
	- AWS Trusted Advisor is an online tool that provides real-time guidance to help you provision your resources following AWS best practices. It looks at your entire AWS environment and gives you real-time recommendations in five categories: Cost Optimization, Performance, Security, Fault Tolerance, Service Limits. You can use AWS Trusted Advisor to help you optimize your AWS environment as soon as you start implementing your architecture designs.

---

# Module 10: AutoScaling & Monitoring

- ## Section 1: Elastic Load Balancing
	- Elastic Load Balancing distributes incoming application or network traffic across multiple targets in a single Availability Zone or across multiple Availability Zones. It also scales your load balancer as traffic to your application changes over time. Monitoring is done via Amazon CloudWatch, access logs, and AWS CloudTrail logs
	- **Types of Load Balancers**

|Application Load Balancer|Network Load Balancer|Classic Load Balancer (Previous Generation)|
|---|---|---|
|Load balancing of HTTP and HTTPS traffic|Load balancing of TCP, UDP, and TLS traffic where extreme performance is required|Load balancing of HTTP, HTTPS, TCP, and SSL traffic|
|- Routes traffic to targets based on content of request  <br>- Provides advanced request routing to targeted at the delivery of modern application architectures, including microservices and containers|- Routes traffic to targets based on IP protocol data  <br>- Can handle millions of requests per second while maintaining ultra-low latencies  <br>- Optimized to handle sudden and volatile traffic patterns|Load balancing across multiple EC2 instances|
|Operates at the application layer ([OSI model](https://en.wikipedia.org/wiki/OSI_model) layer 7)|Operate at the transport layer (OSI model layer 4)|Operates at both the application and transport layers|

- With Application Load Balancers and Network Load Balancers, you register targets in target groups, and route traffic to the target groups.
- With Classic Load Balancers, you register instances with the load balancer.



- ## Section 2: Amazon CloudWatch
	- **Monitors:** AWS resources and applications that run on AWS
	- **Collects and tracks:** Standard and custom metrics
	- **Alarms:** Send notifications to an Amazon SNS topic and perform Amazon EC2 Auto Scaling or Amazon EC2 actions
	- Create alarms based on:
	    - Static threshold
	    - Anomaly detection
	    - Metric math expression
	- Specify:
	    - Name space
	    - Metric
	    - Statistic
	    - Period
	    - Conditions
	    - Additional configuration
	    - Actions
	- **Events:** Define rules to match changes in AWS environment and route these events to one or more target functions or streams for processing


- ## Section 3: Amazon EC2 Auto Scaling
	- Monitors your applications and automatically adjusts capacity to maintain steady, predictable performance at the lowest possible cost
	- Provides a simple, powerful user interface that enables you to build scaling plans for resources
	- Helps you maintain application availability
	- Enables you to automatically add or remove EC2 instances according to conditions that you define
	- Detects impaired EC2 instances and unhealthy applications, and replaces the instances without your intervention
	- Provides several scaling options: Manual, scheduled, dynamic or on-demand, and predictive
	- An Auto Scaling group is a collection of EC2 instances that are treated as a logical grouping for the purposes of automatic scaling and management.
	- Scale out (launch instances), Scale in (terminate instances)
