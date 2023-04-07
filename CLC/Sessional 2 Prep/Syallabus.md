- [ ] Module 4 KMS, slide 65 onwards
- [ ] Module 5: Networking & Content Delivery
- [ ] Module 6: Compute slides 1 to 16
- [ ] Module 7: Storage EBS only
---
# Module 4: AWS IAM (KMS onwards from 65)

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