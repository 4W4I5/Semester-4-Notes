## Software Process Models

- ##### Generic process framework
	- Communication
	- Planning
	- Modelling (analyze, design)
	- Construction (code, testing)
	- Deployment
- ##### Waterfall model
	- Oldest
	- Used When 100% requirements are accurate
	- Linear
	- Cons
		- Iteration is not possible, any change causes confusion
		- Quality is impacted hard whenever it is noticed that one of the phases went kaput
		- It is required that you still continue and deliver the product
		- Customer wont always state all the requirements up front, change is inevitable
		- Working version is not ready until the final phase
		- Overall it provides very low accommodation to changes
- ##### Waterfall model with feedback loop
	- Flexible
	- Risk mitigation
	- Time-taking, Complex
	- Cons
		- Even though it is iterative, there is still no incremental delivery of the product
		- Phase overlapping not supported
		- Risk handling not supported
		- Customer interaction only occurs during the start and the end of the project
- ##### Incremental Model
	- When requirements are well understood
	- Multiple independent deliveries
	- Workflow is linear in increment but staggered between increments
	- ##### Pros
		- Useful when staffing is low for full-scale dev
		- It lets stakeholders and developers see results with the first increment, if anyone doesn't like anything everyone finds out a lot sooner.
		- Needed functionality set is provided before the optional components
		- Such a style of model is great for projects that have loosely coupled parts and have complete and clear requirements
		- Iterative in nature
			- Every product made is operational at some level
	- ##### Cons
		- Requirements must be well understood
		- Project style must have independent modules
		- Total cost is higher than waterfall
- ##### Iterative
	- Less workforce required
	- Costly, non-satisfactory usually for customers
- ##### Prototyping Model
	- Creates a model of product before final product
	- Iterative
	- When requirements are not that well understood
	- Focuses on visibility of product
	- Time taking, customer accepts “demo”, developers get lazy thus implementation compromises so discard model after getting it approved.
- ##### Spiral Model
	- When risks are high and requirements are not well understood
	- Evolutionary approach (incremental + iterative)
	- Inner spiral = taking requirements. Outer spiral = waterfall approach but allow changes
	- Requires expertise, uncertain iterations (too much= chaos, too less= very slow)
	- A decision is made after every complete spiral
	- Should focus on flexibility and extensibility > high quality. Speed > zero defects
	- ##### Cons
		- Number of iterations are always unknown
			- Cause of the way requirements are not understood, the spiral keeps on going until requirements are finalized
		- Max speed of evolution unknown
			- Too fast and something will be missing
			- Too slow and productivity suffers
		- Software development should be flexible to future changes
			- After which the defects can be worked out and we can start to focus on quality


---

## Intro to Agile Development

- ##### Agility
	- Rapid response to change
	- Customer involvement in team
	- Organization team to control work
	- Incremental delivery of product
- ##### Agile process
	- User stories/scenarios
	- Plans are short-lived
	- Iterative
	- Adapts to change
	- Incremental product
	- People, not process
	- Simplicity
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
- ##### Agile Process models
	- XP programming
	- Scrum

---

## XP Programming

- ##### Best used
	- Extreme approach – iterative
	- Increments delivered every 2 weeks
- ##### Steps involved
	- Planning= user stories, values, acceptance test criteria, iteration plan, deadline, costs
	- Design= CRC cards, spike solutions(prototypes), follows KIS principal
	- Coding= pair programming, unit testing, refactoring (change code to reduce complexity, shouldn’t change functionality, automated test cases used to check running code)
	- Testing = unit tests, acceptance test criteria, automated test cases
	- = Software increment
- ##### Customer role
	- User stories (cards- > implementation task)
	- Prioritize features
	- Acceptance test
- ###### Customer Involvement
		- The role of the customer is to:
			- Develop stories that refine the requirements
			- Prioritize features to be implemented in the next release
			- Develop acceptance test which assess whether or not the system meets its requirements
		- User Requirements
			- These are expressed as scenarios/stories
			- Written on story cards which are broken into task cards. These cards are the basis of schedule and cost estimates
			- Customer chooses stories to include in the next release based on their priorities and schedule estimates
- ##### Problems
	- Customer involvement (not always representative)
	- Architectural design (costly)
	- Test complacency (more positive tests != good program)
- ###### Key Points
	- Extreme programming includes practices such as systematic testing, continuous improvement and customer involvement
		- There's always refactoring, test cases and customer feedback and input
	- Customers are involved in developing requirements which are expressed as simple scenarios
		- Customers are required to specify their requirements which are converted into scenarios by the team
	- The approach to testing in XP is a particular strength where executable tests are developed before the code is written
		- Testing happens before coding, With the help of the customer
	- Key problems with XP include difficulties of getting customers who are valuable in their input and output to the process and problems of architectural design

 ![](./media/image1.png)
 ![](./media/image2.png)
 ![](./media/image3.png)

# Scrum

- ##### Backlog
- ##### Scrum meetings
	- Plan meeting (Product owner- > team // priorities are discussed)
	- Review meeting (4 hours, team->Product owner // shows results, informal)
	- Daily scrum (15 minutes, Scrum master and team)
	- Sprint Retrospective (Product owner, scrum master, team) , meeting to review last sprint, lasts 3 hours
	- Sprints
- ##### Scrum roles
	- Product owner
	- Scrum master
	- Team
- ##### Artefacts
	- Product backlog
	- Sprint backlog
	- Sprint burndown chart
	- Product increment (product of every increment, functional, can be sold on its own)
- ##### XP vs Scrum
	- XP = more technical, scrum= focuses on framework
	- XP= small team, scrum = larger team
	- Scrum = has roles, XP= no roles
- #### Problems with scrum
	- Other Agile methods produce acceptable results
	- A project cannot always be divided into a chunk of chunks
	- Quality Control is meh, everything is irregular therefore so is quality assurance
		- "Mera masla nhi ha aglay ka masla ha"
		- If quality assurance is required alongside the project development then go for scrum
	- Embrace do what i told you to do now and forget about yesterday
	- Nobody can not agree on a completed project
	- Quality Control is given more importance over Quality Assurance
	- Extra points
		- No way a product will be functioning by the end of the First sprint
			- It will be working but not functioning as intended at least not at the very start
		- Sprint Reviews would require product owners to be there at the start of every new Sprint
		- Agile processes are adaptive therefore not suitable for situations where there is high uncertainty in both requirements and technical degree (This point is kinda meh)
		- High chance of a failed project if team chemistry is not good enough
		- Daily meeting sounds annoying
		- Team member leaving during a project is no buneo

 ![](./media/image4.png)
 ![](./media/image6.png)
 ![](./media/image7.png)

---

## Requirement Engineering

# NOTE:: Do not mix customer with user. Marks will be deducted on this

- ##### Why?
	- No understanding
	- Disorganized
	- Not much verification
	- No solid base of software
	- Developers mindset = clear as we go, will examine increments, start coding asap
- ##### Steps
	- Inception
	- Elicitation
	- Elaboration
	- Negotiation
	- Specification
	- Validation
	- Requirements Management
- ##### Inception
	- Requirement Engineer asks questions to understand clearly (customer, stakeholder, benefits) // problem and solution, effectiveness of communication
	- Scope of the project
	- Understand the Problem being addressed
	- Figure out the domain of the problem
	- Identify Stakeholders and study them
- ##### Elicitation
	- To extract information
	- Has problems (scope, understanding, volatility)
	- Collaborative requirement gathering
		- Meeting = customer, engineers, stakeholder
		- Control = facilitator = customer/developer/anyone from outside
		- Definition mechanism = tools used
		- goal = identify problems, get different approaches, requirements
	- ##### Pros
		- Clarify and refine customer requirements
		- Improves communication and collaboration b/w stakeholders
		- Increases chances of developing a system the customer actually needs
		- Avoid misunderstanding
		- Identifies potential risks and problems early on
		- Increases user and stakeholder confidence in the development process
		- Identify new business opportunities and revenue streams
	- ##### Cons
		- Most error-prone
		- Time consuming
		- Impacted by political and organizational factors
		- Bad elicitation leads to
			- Increased dev costs
			- Decreased efficiency
			- lack of buy in from stakeholders
			- incomplete product
		- Most communication intensive
		- Requires expertise
	- ###### Difficulty during this phase
		- Hard to define scope, the boundaries of the system, what it can do and what it can not do. Too much technical detail instead of overall system objectives
		- Hard to understand what is wanted, obvious info is often omitted
		- Hard to focus on a requirement, as they change over time
	- ##### Procedure
		- ##### Collaborative Requirements Gathering (CRG)
			- Meetings organized by **Facilitator** and attended by
				- Software engr
				- customers
				- stakeholders
			- Rules for participation are established
			- Informal agenda proposed, formal enough to cover all points
			- Goal of the meeting is to
				- Identify problem
				- Propose elements of the solution
				- Negotiate different approaches
				- Specify a prelim set of requirements
		- ###### Quality Function Deployment (QFD)
			- ##### Definition
				- Construct basic relationship matrices b/w
				- Technical Requirements
				- Priorities
				- Competitor Assessment (Optional, on a need basis)
				- Customer needs- > technical document
				- Normal requirements = normal goals
				- Expected requirements = not explicitly mentioned
				- Exciting requirements = extra features without extra pay
				- Benefits = avoid loss of information, improves user and team involvement, saves time of cycle, better quality product
			- ##### Done by
				- Identifying stakeholder requirements
				- Identify technical features of requirements
				- Relate requirements to the technical features
				- Evaluate features and specify a target value for each
				- Prioritize features for dev effort
			- ##### Pros
				- Improves
					- User involvement
					- Management support and involvement
					- Project Development
				- Shortens dev lifecycle
				- Supports team involvement
				- Structures communication process
				- Avoids loss of information
				- Preventive tool for improving quality
			- ##### Cons
				- The matrix can get very complex very quickly for a large project
				- Heavily dependent on the customer
				- Adapting to the market trends is tough due to the nature of observing the market and processing data
				- Focus on customer satisfaction
					- Cost, lifecycle and other strats take a heavy hit
			- Image
				- Whats are on the left
				- Hows on the top
				- Competitive and importance weightages are on the right
				- Bottom (in order)
					- Target Values
					- Competitive Evaluation
					- Importance weighting
				- Relationship Matrix
					- Rows are requirement
					- Cols are Measurable response to demanded quality
						- in short its the measure
  ![](./media/image8.png)
- ##### Elaboration
	- Analysis modelling
	- First technical diagram
	- Essential vs implementation tasks
	- Visible requirements
	- Structured analysis = Data- > attributes and relations, input // transformation // output. Consists of flow oriented modelling (flow chart showing input, processes and output)
	- Object oriented = classes and their collaborations. Consists of scenario (use user stories), class based (divide work to classes) and behavioral modelling (states of processes)
	- Scenario = use cases (find actors first), activity diagram, swim lane diagram

 ![](./media/image9.png)
 ![](./media/image10.png)

 ![](./media/image11.png)

- ##### Class based= extract nouns (class attributes) and verbs (operations) from a paragraph, CRC
	- ###### Steps in OOA
		- **Identify the objects**: Identify the objects that make up the system being modeled. This involves analyzing the requirements of the system and identifying the entities that are relevant to the problem being solved.
		- **Define the attributes**: For each object identified, define the attributes (or properties) that are relevant to that object. Attributes describe the state of an object.
		- **Define the methods**: For each object identified, define the methods (or behaviors) that are relevant to that object. Methods describe the behavior of an object.
		- **Identify the relationships**: Identify the relationships between the objects in the system. This includes identifying the associations (or connections) between objects, as well as any inheritance relationships.
		- **Create a class diagram**: Use the information gathered in steps 1-4 to create a class diagram. A class diagram is a visual representation of the classes, attributes, and relationships in the system being modeled.
	- ###### Benefits of OOA
		- **Improved understanding of the problem**: OOA helps to ensure that the problem being solved is well understood, by breaking it down into smaller, more manageable pieces.
		- **Improved communication**: By using a common set of terms and concepts, OOA helps to improve communication between the various stakeholders involved in the software development process.
		- **Code reuse**: By promoting inheritance and polymorphism, OOA can help to promote code reuse and reduce code duplication.
		- **Flexibility**: OOA provides a flexible framework for modeling systems, allowing for changes to be made easily as requirements evolve.
			- ###### Class Based
				- Class Attributes
					- Found using nouns that reasonably belong to a class
					- Can be values that describe the current properties or the state of a class
					- Can also be a rejected class that was reclassified as an attribute
					- Not an attribute if more than one is associated with a class
				- Class Operations
					- Found using verbs that relate to a problem domain which was previously identified
					- Behavior of an Object
					- Four categories
						- Data manipulation to change state of Object
						- Perform a computation
						- Inquire about State of Object
						- Monitor an Object for the occurrence of a controlling event
					- Has knowledge about state of the class and nature of its associations
					- Operation action is based on current values of attributes of class
				- Class Diagrams
					- Attributes on the top (Data members)
					- Operations on the bottom (Functions)
					- Public members/methods are shown with a '+'
					- Private members/methods are shown with a '-'
				- CRC Modelling (Class-Responsibility-Collaborator)
					- Identify Classes, their responsibilities and collaborations b/w them
					- Process
						- Identify Classes
						- Define Class Responsibilities
							- Responsibilities are tasks or functions that a class is responsible for performing
						- Identify Collaborations
							- Collaborations define how classes work together to achieve their responsibilities
						- Iterate and Refine
				- Class Selection Criteria
					- Retained information
					- Needed services
					- Multiple attributes
					- Common attributes
					- Common operations
					- Essential requirements
				- CRC Cards are used to create Class diagrams later on
  ![](./media/image12.png)
  ![](./media/image13.png)
 ![](./media/image14.png)
 ![](./media/image15.png)
Flow based = DFD, CFD
- ## Process of creating a Flow Diagram
- ### Data Flow Diagram
- ### Control Flow Diagram
	- Aka flowchart
	- Graphed as a sequence of steps and in what order they are executed.
	- Refer to the
Behavior model = State diagram, sequence diagram

- ##### Negotiation
	- Wants vs can be done
	- Requirements are ranked
	- Risk analysis
	- Costs and deadline
	- Iterative, requirements can be cut/modified to reach common ground, try to satisfy customers
- ##### Specification
	- Final work product (SRS Document)
	- Foundation
	- Functions, behavior, constraints, information
	- All kind of requirements, tests, linkage of requirements = crux of everything
- ##### Validation
	- SRS quality assessment
	- To check if everything is met and mentioned = confliction, clear information, test analysis
	- Primary requirement validation mechanism
	- Engineers, customers, users, stakeholders involved
- ##### Requirement management task
	- Each requirement has identifier
	- More focus on requirement traceability tables = RTM (Requirement Traceability Matrix)
	- Requirement dependence
	- Linkage between requirements, test cases, diagrams used

---

Diagrams
Use cases
  ![](./media/image16.png)
  ![](./media/image17.png)

- ##### Activity diagram
	- Analyze use cases
	- Can add parallel activities (differs from flowchart)
	- Multi-threaded
	- Doesn’t show object collaboration or behavior over a lifetime
	- Can be used to define event in a use case
	- Workflow
	- Special case of state chart diagram
	- Control flow edge?
	- Object flow edge?
	- Initial node = dot
	- Decision node = diamond
	- Merge nodes= 3->1
	- Fork nodes= 1->3 /// ?? control nodes
	- Final nodes
		- flow final (circle w inside as X) incase of all tokens
		- final node = dot in a circle, incase of 1 token
	- Object nodes
		- Activity, w/pins
		- central buffer (multiple inputs and output)
		- data store = holds data persistently like a database


Activity diagram (CHATGPT)
**Object Nodes:**

1. Object Nodes are UML elements that represent an instance of a class or an object in a UML activity diagram.
2. Object Nodes can have a type and can be connected to other nodes through control and object flows.
3. Object Nodes can be used in a variety of ways, including to represent input/output data or to represent objects that are created or destroyed during the execution of an activity.

**Activity Parameter, Pins, Central Buffer, Data Stores:**

1. Activity Parameters are UML elements that represent data inputs or outputs for an activity.
2. Pins are UML elements that represent specific types of activity parameters, including input pins, output pins, and inout pins.
3. Central Buffers are UML elements that represent a shared buffer that can be used to exchange data between different parts of an activity.
4. Data Stores are UML elements that represent a place where data can be stored and retrieved during the execution of an activity.

**Multiplicities, Upper Bound, Effect, Ordering:**

1. Multiplicities are used in UML to specify the number of times an element can occur.
2. Upper Bound is used to specify the maximum number of times an element can occur.
3. Effect is used in UML to specify the effect that an operation or activity has on an object or data.
4. Ordering is used in UML to specify the order in which objects or data are processed within an activity.

**Activity Edges:**

1. Activity Edges are UML elements that represent the flow of control or data between nodes in an activity diagram.
2. There are several types of activity edges, including control flows, object flows, and exception flows.
3. Activity Edges can be labeled to provide additional information about the flow of control or data.

**Labels, Transformations, Selection:**

1. Labels are used in UML to provide additional information about an element or edge in a diagram.
2. Transformations are used in UML to specify how an object or data is transformed or modified during the execution of an activity.
3. Selection is used in UML to specify which objects or data are selected or processed within an activity.

**Activity Partitioning:**

1. Activity Partitioning is used in UML to divide an activity into smaller, more manageable parts.
2. Activity partitions are represented in a swim lane diagram, with each partition representing a different actor, system, or process.
3. Activity partitioning can be used to improve the clarity and organization of an activity diagram.

**Pre/Post conditions:**

1. Pre-conditions are used in UML to specify the conditions that must be true before an activity can be executed.
2. Post-conditions are used in UML to specify the conditions that must be true after an activity has been executed.
3. Pre/Post conditions are useful for specifying the expected behavior of an activity and for verifying that the activity has been executed correctly.

**Event actions:**

1. Event actions are UML elements that represent the occurrence of an event within an activity.
2. There are several types of event actions, including SendSignalAction, AcceptEventAction, WaitTimeAction, Time trigger, and time events.
3. Event actions can be used to trigger other activities or to respond to external events.

**Interruptible activity region:**

1. An Interruptible Activity Region is a UML element that represents a region within an activity that can be interrupted by an external event.
2. Interruptible Activity Regions can be used to model activities that can be interrupted by a user or a system event, such as a timeout or an error condition.
3. Interruptible Activity Regions can also be used to model

**Expansion region:**

1. An Expansion Region is a UML element that represents a region within an activity that can be expanded into a set of parallel activities.
2. Expansion Regions are used to model activities that can be performed in parallel or that can be performed multiple times.
3. Expansion Regions can be used to improve the performance and efficiency of an activity.

**Swim lane diagrams:**

1. Swim Lane Diagrams are UML diagrams that are used to represent the flow of activities between different actors, systems, or processes.
2. Swim Lane Diagrams consist of a series of parallel lanes, with each lane representing a different actor, system, or process.
3. Swim Lane Diagrams can be used to model complex workflows and to improve the clarity and organization of an activity diagram.
