## Cloud Benefits & Adoption Perspectives
Why would a company want to migrate to a cloud infrastructure?
- To convert CAPEX costs into OPEX, mainly due to upfront cost involvement
	- Data Center Investment based on forecast
		- CAPEX (CAPital EXpenditure)
			- Running facilities. e.g. Funds to start a business i.e. location and furnishing costs
			- Required to pay upfront & in large amounts
		- OPEX (OPerational EXpenditure)
			- `Add in later`
	- Pay only for what you consume
	- Massive Economies of Scale
		- Scaling up a business also increases the margin of profit
			- Either sell more and have a low profit margin per device
			- or sell less and have a high profit margin per device
	- Avoid Guessing Usage Capacity
		- Scale on demand to users
		- Avoid Underestimate/Overestimating server loads
			- Either way its a waste of money, use your head to figure out why if doesn't make sense
	- Increase Speed and Agility
		- Usually with traditional hardware, there is a long waiting list in between getting the hardware ready and implemented in a system
		- In the cloud, additional hardware already exists, it just needs to be activated and that usually takes a couple of minutes at best
	- No need to spend resources on running and maintaining local data centers
		- Allocate more resources towards the business instead of setting and maintaining the business.
	- Global in minutes
		- Not relevant for all cloud providers, but it is best if for a business that might best scale on a global level
		- No need to setup infrastructure over in target countries, rather just grant access to that country's domain with the properly licensed and owned machines
`Sir will not ask all 6, but rather a question will ask for insight on one point in context to the rest`

### Web Service
- Any software/service that is available over the internet
- Uses a standardized format, i.e. JSON or XML
- API calls for request and responses 
	- REST API or AJAX API

AWS provides web services that work together like building bricks. Its name is a bit old (web services instead of cloud services )but it is in essence a cloud provider now. 

##### Core Cloud Services
- Analytics
- Compute
- Networking
- Storage
- Database

##### Amazon User Network
- AWS Cloud
	- Virtual Private Cloud (VPC)
		- Amazon EC2
		- `add later`
		- `add later`


#### Interface with AWS
- Since its just API calls, the services can be accessed by sending a specific call by 
	- CLI
	- Management Console
	- SDK 
		- API calls within your own code


#### Cloud Adoption Framework (AWS CAF)
Whenever a company is to adopt a cloud computing framework, the considerations in mind of the company board are given guidances and best practices by AWS CAF to accelerate successful cloud adoption and transfer of the company's local infrastructure to the cloud
CAF Perspectives are 6 in total, divided into 2 sections. One being Staff and the other being Processes
- People/Processes
	- Business
		- Ensure that IT is aligned with business needs and investments can be traced into demonstrable business results
		- Capabilities
			- IT Finance
			- IT Strategy
			- Benefits Realization
			- Business Risk Management
	- People (HR, Staffing and People Managers)
		- Prioritize training, staffing, and organizational changes to build an agile organization
		- Capabilities
			- Resource Management
			- Incentive Management
			- Career Management
			- Training Management
			- Organizational Change Management
	- Governance (CIO, CISO (head of security ops), Program Managers, Enterprise Architects, Business Analysts and Portfolio Managers)
		- Ensure that skills and processes align IT strategy and goals with business strategy and goals to maximize IT investment
		- Capabilities
			- Portofolio Management
			- Program and Project Management
			- Business Performance Measurement
			- License Management
- Technical
	- Platform
	- Security
	- Operations
These Perspectives are just sets of capabilities
