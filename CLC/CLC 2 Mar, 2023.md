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