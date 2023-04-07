- [ ] Module 4 KMS, slide 65 onwards
- [ ] Module 5: Networking & Content Delivery
- [ ] Module 6: Compute slides 1 to 16
- [ ] Module 7: Storage EBS only
---

# Module 4: AWS IAM (KMS onwards from 65)

# Section 4: Securing Accounts

## Encryption of Data (AWS Cert Manager)

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

## AWS KMS (Key management system)

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

## AWS Cognito

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

## AWS Shield

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

# Section 5: Securing data on AWS

## Securing S3 Buckets & Objects

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

# Section 6: Working to Ensure Compliance
