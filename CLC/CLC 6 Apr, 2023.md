### Module 6: Compute

Categories of Compute Services
- Virtual Machines | Instance based
	- AWS EC2
- Serverless computing
	- AWS Lambda
		- Called serverless as it just runs code as it is given
			- Called a lambda function
		- AWS manages the infrastructure
		- Scheduled run of code or by run of event
- Container-Based computing
	- Diff types
		- AWS ECS (Amazon Elastic Container Service)
		- AWS EKS (Amazon Elastic Kubernetes Service)
		- AWS ECR (Amazon Elastic Container Registry)
		- AWS Fargate
			- Requires administrative overhead but provides more control
	- Used to spin up and run jobs more quickly
- Platform-As-A-Service
	- AWS Beanstalk
		- Used for WebApps
---
### Amazon EC2
- Provides VMs
- Can run into any availability zone
- Use of AMI, Amazon Machine Images
	- Custom images cannot be used
- Can manage traffic to active instances