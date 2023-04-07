- [ ] Module 4 KMS, slide 65 onwards
- [ ] Module 5: Networking & Content Delivery
- [ ] Module 6: Compute slides 1 to 16
- [ ] Module 7: Storage EBS only
---

# Module 4: AWS IAM (KMS onwards from 65)

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
## Securing S3 Buckets & Objects
- New S3 Buckets are private & protected by default
- Permissions following the principle of least privilege are used alongside S3 Encryption to allow access to the data stored in the bucket
- Tools
	- S3 Block Public Access
	- IAM Policies
	- Bucket Policies
	- Access Control Lists
	- AWS Trusted Advisor