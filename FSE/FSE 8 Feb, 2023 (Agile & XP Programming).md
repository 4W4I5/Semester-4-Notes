#### Fears of a programmer
- Deadline
- Cost of resources
- Cost of personal time
- Quality Product
- Any Flaws??
- Possible Wrong Track
- No fun
---
# Agile Model (Non-Traditional Model)
- Agile is a effective (Rapid and Adaptive) response to change
- Effective communication among all stakeholders
- Drawing customer onto the team
- Organizing the team so that it is in control of the work performed 
- Leading to a rapid, incremental delivery of software
- Agile welcomes changes in the requirements
- Very thorough testing of the product chunks
- No need for planning, just start working

### Agile Process
- ##### Scenarios
	- User stories, descriptions of the products' intent
- ##### Short-lived Planning, Get work done as soon as possible, trash prototypes, more failure = more success
- ##### Incremental Delivery
	- Develops software iteratively with heavy emphasis on construction activities
	- Due to multiple prototyping standards per component, multiple fully functional versions of the software are available in increments 
- #####  Embrace Change
	- Adapts to changes as they occur
- #####  People Not Process
	- Banda ziada important ha process ki jagah, Focus more on practicality instead of by book
- ##### Very important to understand the divide and conquer rule, Divide a very big problem into small chunks that can be programmed into quick functioning prototypes

- ##### Pros
	- Working software is delivered frequently in weeks instead of months
	- Face-to-Face is the best form of communication b/w a dev team and the customer
	- Continuous attention to technical excellence and good design
	- Even late changes are welcomed
- ##### Cons
	- Large software deliverables are hard to assess for level of difficulty
	- Lack of emphasis on necessary documentation
	- Easily taken off track if customer is not clear on the final outcome
	- Advanced technique, newbie programmer are better off with traditional models

Some examples of agile process models are:
- eXtreme Programming
- Scrum
- Adaptive Software Development
- Dynamic System Development Method (DSDM)
- Crystal
- Feature Driven Development
- Agile Modeling (AM)


- # eXtreme Programming Process Model
	- ###### Best Known and Most used
	- Extreme Approach to iterative development
		- New Versions may be built several times a day
		- Increments are delivered to customers every 2 weeks
		- All tests must be run for every build and the build is only accepted if tests run successfully
	- ###### eXtreme Programming Values:
		- Communication
		- Simplicity
		- Feedback
		- Courage
		- Respect
	- ###### Planning
		- User Stories
			- Assess each Story and assign a cost
		- Values
		- Acceptance test criteria
		- Iteration Plan
		- Delivery
			- Commitment is made on the Delivery date
	- ###### Design
		- Simple Design
			- KIS, Keep It Simple Principle
			- For difficult design problems, creation of spike solutions, a design prototype
		- CRC Cards (Class Responsibility Cards)
		- Spike Solutions (Stub prototypes)
		- Prototypes
	- ###### Coding
		- Pair Programming
			- Two people sit down together and code, improving on code at the same time
			- Multiple Pairs
			- Informal review process
		- Refactoring
		- Unit Testing 
			- Testing on a modular level
		- Continuous Integration
	- ###### Testing (Involves a lot of testing)
		- Follows a Test First, Code later approach
			- Clarifies the requirements to be implemented
			- Written as programs to allow for automatic execution, includes a check that it executed correctly
			- All previous and new tests run automatically at every release. New functionality should not introduce errors
		- User is involved during this stage as well
		- Automated test harnesses are used to run component tests each time that a new release is built
		- ###### Unit Testing
			- Modular Level, A brick in a room
			- All Unit tests are executed daily
		- ###### Integration Testing
			- Inter-Modular level, Multiple Bricks connected together
		- ###### System Testing
			- Final Room test
		- ###### Acceptance Testing
			- Controlled setting tests, revise whatever needs to be revised
			- Tests defined by the customer and executed to assess customer visible functionality
	- ###### Final Release
		- Software Increment
		- Project Velocity Computed
	- ###### Customer Involvement
		- The role of the customer is to:
			- Develop stories that refine the requirements
			- Prioritize features to be implemented in the next release
			- Develop acceptance test which assess whether or not the system meets its requirements
		- User Requirements
			- These are expressed as scenarios/stories
			- Written on story cards which are broken into task cards. These cards are the basis of schedule and cost estimates
			- Customer chooses stories to include in the next release based on their priorities and schedule estimates

How important is change in XP, very important. Software houses that embrace change are the ones that flourish

###### Refactoring
- Process of revising code over and over making it efficient and easier to read
- Testing code at the same time
- Doesn't change the functionality of the system
- Automated testing simplifies refactoring as the code can be checked if it runs appropriately

#### Problems with XP
- Customer Involvement
	- No customer is free enough to sit down with the team to always give input and feedback
- Architectural Design
	- Its a people style design, its more people based
	- They make the design and then further improve upon every revision
- Test Cases
	- Automated test cases might not go over the entire program
		- They are easy to automate rather than be a good test case
	- Even if there are lots of tests a program might not fully be tested for flaws
###### Key Points
- Extreme programming includes practices such as systematic testing, continuous improvement and customer involvement
	- There's always refactoring, test cases and customer feedback and input
- Customers are involved in developing requirements which are expressed as simple scenarios
	- Customers are required to specify their requirements which are converted into scenarios by the team
- The approach to testing in XP is a particular strength where executable tests are developed before the code is written
	- Testing happens before coding, With the help of the customer
- Key problems with XP include difficulties of getting customers who are valuable in their input and output to the process and problems of architectural design


---
