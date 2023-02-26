### Waterfall Model (Obsolete)
- Phases
	- Communication
		- Project initiation
		- Requirements Gathering
	- Planning
		- Estimating
		- Scheduling
		- Tracking
	- Modelling
		- Analysis
		- Design
	- Construction
		- Code
		- Test
	- Deployment
		- Delivery
		- Support
		- Feedback
- Requirement Gathering 
- Software & System Design
- Implementation & Unit Design
- Operation & Maintenance

- Waterfall comes from the fact that any changes into the previous phase cannot be implemented
- Quality is impacted hard whenever it is noticed that one of the phases went kaput
	- It is required that you still continue and deliver the product
- Waterfall might be a viable choice only when you are sure that you have successfully completed the requirement gathering phase (which rarely happens)
- Overall it provides very low accommodation to changes

###### Cons of Waterfall
- Iteration is not possible, any change causes confusion
- Customer wont always state all the requirements up front, change is inevitable
- Working version is not ready until the final phase

##### Waterfall Model With Feedback (Iterative)
- Each phase has a feedback session which allows for easier error correction in the next iteration
- Cons
	- Even though it is iterative, there is still no incremental delivery of the product
	- Phase overlapping not supported
	- Risk handling not supported
	- Customer interaction only occurs during the start and the end of the project

---
### Incremental Model (Traditional)

- Divides system functionality into small increments that are delivered one after the other in quick succession
- Every increment expands on the previous one until everything has been updated and implemented
	- It passes through requirement, design, coding and testing stages
- It lets stakeholders and developers see results with the first increment, if anyone doesn't like anything everyone finds out a lot sooner.
- Such a style of model is great for projects that have loosely coupled parts and have complete and clear requirements

- Pros
	- Useful when staffing is low for full-scale dev
	- Needed functionality set is provided before the optional components
	- Iterative in nature
		- Every product made is operational at some level
- Cons
	- Requirements must be well understood
	- Project style must have independent modules
- Phases
	- Communication
	- Quick Planning
	- Quick Design (Modelling)
	- Prototype
	- Deployment
		- Delivery
		- Feedback
	- Repeat

###### Example of the incremental process
- Outline Description
- Specification
	- Initial Version
- Development
	- Intermediate Version
- Validation
	- Final Version

---
### Prototyping Model (Evolutionary)
- Unsure requirements from customer, this is when it is used the best
- Throw out a prototype that might work, and see if itll happen
- Hard to convince the customer that the original isn't the project you were working on
- Devs are lazy

### ---THIS POINT ONWARDS IS STUFF FROM THE NET NOT THE CLASS---
Best used for developing Online systems where users are expected to fill forms or go through various screens before data is processed
- Basic Requirement Identification
	- Understanding the very basic product requirements especially in terms of user interface
	- Intricate aspects such as security and performance can be ignored at this stage
- Developing the initial prototype
	- Very basic requirements are showcased and user interface are provided
	- Workarounds simulate the intended meaning of the final product
	- Expect lots of uses of stub functions
- Review of the prototype
	- Customer and Stakeholders share important feedback vital to the project 
	- Used to revise and enhance the product
- Revise and Enhance the prototype
	- Customer negotiations happen, time and performance is discussed alongside feasible implementation of functionality in a given time is also negotiated.
		- Horizontal Prototype displays the UI and gives a broader view of the entire system
			- Little to no work is done on the internal systems
		- Vertical Prototypes are technical in nature and are used to get details of the exact functioning of the sub systems. It gives a more detailed elaboration on a specific function
- Pros & Cons
	- Pros
		- Increased User involvement before its implementation
		- Users get a better understanding of the product as it is a working model albeit a little rough
		- Reduces Time and Cost as defects can be found much earlier
		- Missing functionality is identified earlier
		- Confusing or difficult functions can be identified and changed accordingly
	- Cons
		- Risk of insufficient requirement analysis owing to too much dependency on the prototype
		- Users see the prototype and attempt to buy it after a few fixes, resulting in a bad product
			- Very important to define rules up front, before starting the project
		- Devs may try to reuse existing prototypes to build the actual system even when its not technically feasible
			- They also try to compromise on implementation in order to get the prototype up and running
		- ###### Effort invested in building prototypes may be too much if not checked/monitored properly
- Types of Prototyping
	- Throwaway/Rapid
		- Keep generating prototypes with minimum requirement analysis and minimal effort
		- Once target product is understood, discard all prototypes and develop the new prototype to completion
	- Evolutionary
		- Build all functions with minimal functionality 
		- Early product prototypes are the foundations for future product prototypes
		- Requirements are well understood and added as needed
	- Incremental
		- Building multiple functional prototypes of various subsystems
		- Divide and conquer rule 
		- Integrate all available prototypes near the end of the development phase to complete the system
	- Extreme
		- Mostly used in the Web Dev domain
		- 3 Sequential Phases
			- Basic prototype with all existing pages is presented in HTML format
			- Data processing is simulated using a services layer
			- Services are implemented into the final prototype 
		- Endgoal is draw attention to the second phase. where a fully functional UI is developed with very little regard to the actual services

---
### Spiral Model (Evolutionary)

- Phases
	- Communication
	- Planning
	- Modelling
	- Construction
	- Deployment
	- Repeat
- Points
	- Is an evolutionary approach to programming
	- Used when requirements are not understood and risks are high
	- At first, gather information on software requirements and risks until understood
	- Afterwards, run the loop one more time using the classic waterfall approach but with iterations in mind.
		- Every new spiral(loop) will be a new iteration of the product
	- At the end of each spiral, risk assessment determines which features are to be kept and which to discard
	- Risk assessment expertise required
	- Realistic model for large scale deployment
- Cons
	- Number of iterations are always unknown
		- Cause of the way requirements are not understood, the spiral keeps on going until requirements are finalized
	- Max speed of evolution unknown
		- Too fast and something will be missing
		- Too slow and productivity suffers
	- Software development should be flexible to future changes
		- After which the defects can be worked out and we can start to focus on quality

