# AWS Key Management System (AWS KMS)

- Enable and manage encryption keys after creation
	- Managing this feature is the responsibility of the customer
	- It is enabled by default
	- Can also upload your own keys
- Control the use of encryption across AWS services and in the applications you use/create
- Integrates CloudTrail to log all key usage
- Uses hardware security modules HSMs that are validated by the Federal Information Processing Standards (FIPS 140-2) to protect keys

# Encryption of Data
### Encryption of Data at Rest
- Encryption is done with a secret key
	- AWS KMS manages that secret key
- Data At Rest
	- Defined as Data stored physically
### ### Encryption of Data in Transit
- Data In Transit
	- Data moving across a Network
- Encryption is done using TLS (Transport Layer Security)
	- Creates a secure tunnel using HTTPS
	- AWS Certificate Manager
		- Provides a way to manage, deploy and renew TLS/SSL Certs
- AWS Services support data in transit encryption

# AWS Cognito
- Adds the following to your web and mobile application
	- User
		- Sign in 
		- Sign Up
		- Access Control
- Scales to millions of users
- Supports 3rd party identity providers such as
	- Facebook
	- Google
	- Microsoft Active Directory via Security Assertion Markup Language (SAML 2.0)
# AWS Shield
- DDOS Protection Service
- Available for all AWS applications and services
- Provides always-on detection and automatic inline mitigations
- Advanced Shield
	- Paid service
	- Protects against advanced attacks that implement a faint using DOS
	- Used to minimize application downtime and latency

# AWS compliance programs
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
### AWS Config 
- Simplify compliance auditing and security analysis
- Assess, Audit and Evaluate the configurations of AWS Resources
- Use for continuous monitoring of configs
- Automatically evaluate recorded configs vs desired configs
- Review config changes
- View detailed config histories
### AWS Artifact
- Resource for compliance-related information
- Provide access to security and compliance reports
	- Select online agreements
- Can access example downloads
	- AWS ISO certs
	- Payment card industry (PCI) and Service Organization Control (SOC) reports 
- Access AWS Artifacts directly from the AWS management console
# Securing S3 Buckets & Objects
- Newly created S3 buckets & Objects are Private and Protected by default
