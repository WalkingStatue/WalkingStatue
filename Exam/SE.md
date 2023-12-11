**Chapter 1**

*Software can be described as a collection of
instruction that are executed to get desired
functionalities.

Software is made-up of
-instructions provide desired function and performance
-data structures manipulate information
-documents use of the programs


*Types of Software

■ system software
■ application software
■ engineering/scientific software
■ embedded software
■ product-line software (word
processing, spread sheet)
■ WebApps (Web applications)
■ AI software (solve better than
human)
■ Open world computing
■ Netsourcing
■ Open source


*Characteristics of Software

􀀀 Not “Manufactured” in the Classical Sense
􀀀 A logical rather than physical system element
􀀀 Invisibility
􀀀 Does Not “Wear-Out”
􀀀 Invariably Custom-Built
􀀀 Has reusable components
􀀀 Flexible


*Software Engineering

IEEE Definition
“A Systematic Approach to the Development,
Operation, Maintenance and Retirement of
Software, where Software is Computer
Programs, Procedures, Rules and Associated
Documents and Data pertaining to the Operation
of a Computer System.”


*Software Engineering Layers

![[Pasted image 20231211142018.png]]

■ Engg. Approach must rest on quality
■ Process manage and control s/w projects and
delivery of quality work products
■ Method provide technical how-to’s for
communication, requirements analysis, design
modeling, program construction, testing …
■ Tools provide automated and semi automated
support for the process and methods


*The Software Process

Software Process is the Collection of Activities ,Actions
and Tasks , that are performed when some work
product is to be created

A process frame work establishes the foundation for a
complete software engineering process by identifying a
small number of a framework activities , applicable to all
software project , regardless of size, complexity


*Process Framework Activities

■ Communication-Communicate with stakeholders and
customers
■ Planning-resources
needed, tasks and risk factors likely to occur, schedule
■ Modeling-Architectural models and design
■ Construction-Generation of code and testing
■ Deployment-completed product is delivered

*Umbrella Activities

■ Software project tracking and control
■ Risk management
■ Software quality assurance (SQA
■ Technical reviews
■ Measurement
■ Software configuration management (SCM)
■ Reusability management
■ Work product preparation and production


*The Essence of Practice

■ General steps in carrying out in software
engineering are
1. Understand the problem through communication.
2. Plan a solution by modeling and software design.
3. Carry out the plan for code generation.
4. Examine the result for accuracy by testing and quality
assurance.


*Hooker’s General Principles

■ 1: The Reason It All Exists : s/w system is required to , provide value
to its user, so before starting any project ask “ Does this add real value to the system “ if
answer is “no” , then do not do it
■ 2: KISS (Keep It Simple, Stupid!) : so easy to maintain and
generate less error
■ 3: Maintain the Vision : without conceptual integrity , a system become
patchwork of incompatible design
■ 4: What You Produce, Others Will Consume
■ 5: Be Open to the Future
■ 6: Plan Ahead for Reuse
■ 7: Think! : placing clear, complete thought before action always produce better
result


*Software Myths

■ Management
 We have standards
We have new computers
 We’ll add more people to catch up
I outsourced it, I’m done
■ Customer
 We have general objectives, let’s start
 Change is easily accommodated
■ Practitioner
 We’ll write it and be done
I can’t assess quality until it is running
 I only need deliver code
 Software engineering is about meaningless documents




**Chapter 2**
■ Process Models

![[Pasted image 20231211142855.png]]
![[Pasted image 20231211142917.png]]
![[Pasted image 20231211142931.png]]

*Iterative Development

⚫ Benefits
 Get-as-you-pay
 feedback for improvement
⚫ Drawbacks
 Architecture/design may not be optimal
 Amount of refactoring may increase
Total cost may increase
⚫ Applicability
where response time is important,
 risk of long projects cannot be taken,
 all req not known
⚫ Execution
 Each iteration is a mini waterfall – decide the specs,
then plan the iteration 
 Length of iteration driven by amount of new
functionality to be added in an iteration

![[Pasted image 20231211143208.png]]

⚫ Advantages
 Requirement will be more stable and more likely to
satisfy user needs
 Early opportunity to explore scale/performance issues
Ability to modify or cancel the project early
Enhanced user engagement
⚫ Disadvantages:
 Potential hit on cost and schedule and Risk
⚫ Applicability:
 When req are hard to elicit
 When confidence in reqs is low
 Where reqs are not well understood
 When design is driven by user needs

![[Pasted image 20231211143313.png]]

Use :
• Projects with unclear business needs or too
ambitious/innovative requirements.
• Projects that are large and complicated.
• Research and development (R&D) activity or the
introduction of a new service or a product



**Chapter 3**
Agile Development


*What is “Agility”?

■ Effective response
■ Effective communication
■ Drawing the customer
■ Organizing a team
■ Rapid

*An Agile Process

-customer descriptions
-plans are short-lived
-Develops software iteratively
-multiple ‘software increments’
-Adjusts as changes occur

*Agility Principles 
1. Our highest priority is to satisfy the customer through early
and continuous delivery of valuable software.
2. Welcome changing requirements, even late in development.
Agile processes binds change for the customer's reasonable
advantage.
3. Deliver working software frequently, from a couple of weeks to
a couple of months, with the shorter timescale.
4. Business people and developers must work together daily
throughout the project.
5. Build projects around motivated individuals. Give them the
environment and support they need, and trust them to get the
job done.
6. The most efficient and effective method of conveying
information to and within a development team is face–to–face
conversation.
Agility Principles - I
7. Working software is the primary measure of progress.
8. Agile processes promote sustainable development. The
sponsors, developers, and users should be able to
maintain a constant pace indefinitely. (work together )
9. Continuous attention to technical excellence and good
design enhances agility.
10. Simplicity – the art of maximizing the amount of work
not done – is essential.
11. The best architectures, requirements, and designs
emerge from self–organizing teams.
12. At regular intervals, the team reflects on how to become
more effective, then tunes and adjusts its behavior
accordingly.

*Human Factors

■ the process molds to the needs of the people and
team, not the other way around
■ Competence. (capability)
■ Common focus.
■ Collaboration.
■ Decision-making ability.
■ Fuzzy (uncertain) problem-solving ability.
■ Mutual trust and respect.
■ Self-organization

*Extreme Programming (XP)

■ XP Planning
■ Begins with the creation of “user stories”
■ Agile team assesses each story and assigns a cost
■ Stories are grouped to for a deliverable increment
■ A commitment is made on delivery date
■ After the first increment “project velocity” is used to
help define subsequent delivery dates for other
increments
■ XP Design
■ Follows the Keep It Simple principle
■ Encourage the use of CRC cards (class responsibility collabrator)
■ For difficult design problems, suggests the creation of “spike
solutions”—a design prototype
■ Encourages “refactoring”—an iterative refinement of the internal
program design
■ XP Coding
■ Recommends the construction of a unit test for a store before
coding commences
■ Encourages “pair programming”
■ XP Testing
■ All unit tests are executed daily
■ “Acceptance tests” are defined by the customer and excuted to
assess customer visible 
functionality

![[Pasted image 20231211144159.png]]



**Chapter 5**

*Requirements Engineering-I

■ Inception—ask a set of questions that establish …
■ basic understanding of the problem
■ the people who want a solution
■ the nature of the solution that is desired, and
■ the effectiveness of preliminary communication and collaboration
between the customer and the developer
■ Elicitation—elicit (obtain) requirements from all stakeholders
■ Elicitation is not simple it faces following problems
• Problem of scope
• Problem of understanding
• Problem of volatility (requirement change )
■ Elaboration—create an analysis model that identifies data, function
and behavioral requirements
■ Negotiation—agree on a deliverable system that is realistic for
developers and customers
■ Specification—can be any one (or more) of the following:
■ A written document
■ A set of models
■ A formal mathematical models
■ A collection of user scenarios (use-cases)
■ A prototype
■ Validation—a review mechanism that looks for
■ errors in content or interpretation
■ areas where clarification may be required
■ missing information
■ inconsistencies (a major problem when large products or systems
are engineered)
■ conflicting or unrealistic (unachievable) requirements.
■ Requirements management : A set of activities that helps the project
team – identify , control, and track requirements and changes to
requirements at any time as project proceeds

*Quality Function Deployment

■ Function deployment
■ Information deployment
■ Task deployment
■ Value analysis


**Chapter 6**
Requirements Modeling: Scenarios, Information,
and Analysis Classes

■ Requirements analysis
specifies software’s operational characteristics
indicates software's interface with other system elements
establishes constraints that software must meet

*Rules of Thumb

■ The model should focus on requirements that are visible
within the problem or business domain. The level of
abstraction should be relatively high.
■ Each element of the analysis model should add to an overall
understanding of software requirements and provide insight
into the information domain, function and behavior of the
system.
■ Delay consideration of infrastructure and other
non-functional models until design.
■ Minimize coupling throughout the system.
■ Be certain that the analysis model provides value to all
stakeholders.
■ Keep the model as simple as it can be.

*Domain Analysis

S/W Domain Analysis is the identification,
analysis and specification of common
requirements from a specific application domain

*Elements of Requirements Analysis

![[Pasted image 20231211144949.png]]

• Model propose combine features of
structured analysis and object
oriented analysis
• Analysis modeling leads to the
derivation of each of these modeling
elements
• Each element presents the problem
from different point Of view.
• The specific content of each element
may differ from project to project
• only those modeling elements That
add value to the model Should be
used.

*Scenario-Based Modeling

-Use-Cases
-Activity Diagram
-Swimlane Diagrams


*Flow-Oriented Modeling

it
provide a view of the system that is
unique—it should be used to
supplement other analysis model
elements

*Class-Based Modeling

■ objects that the system will manipulate
■ operations (also called methods or services) that will
be applied to the objects to effect the manipulation
■ relationships (some hierarchical) between the objects
■ collaborations that occur between the classes that are
defined.


*Class-responsibility-collaborator (CRC)

A CRC model is really a collection of standard
index cards that represent classes. The cards
are divided into three sections. Along the top of
the card you write the name of the class. In the
body of the card you list the class
responsibilities on the left and the collaborators
on the right.

*Behavioral Modeling

• Evaluate all use-cases to fully understand the sequence of
interaction within the system.
• Identify events that drive the interaction sequence and
understand how these events relate to specific objects.
• Create a sequence for each use-case.
• Build a state diagram for the system.
• Review the behavioral model to verify accuracy and
consistency.


*The States of a System

■ state—a set of observable
circum-stances that characterizes the
behavior of a system at a given time
■ state transition—the movement from one
state to another
■ event—an occurrence that causes the
system to exhibit some predictable form
of behavior
■ action—process that occurs as a
consequence of making a transition



**Chapter 8**
Design Concepts

■ Good software design should exhibit:
■ Firmness: A program should not have any bugs that
inhibit its function.
■ Commodity: A program should be suitable for the
purposes for which it was intended.
■ Delight: The experience of using the program should
be pleasurable one.

![[Pasted image 20231211151812.png]]

*Characteristics as a
guide for good
design

■ the design must implement all of the explicit
requirements
■ the design must be a readable,
understandable guide
■ the design should provide a complete picture
of the software


*Quality Guidelines

■ A design should exhibit an architecture
■ A design should be modular
■ A design should contain distinct representations
■ A design should lead to data structures that are appropriate
■ A design should lead to components that exhibit independent functional
characteristics.
■ A design should lead to interfaces that reduce the complexity
■ A design should be derived using a repeatable method
■ A design should be represented using a notation that effectively communicates
its meaning.


*Quality Attributes

■Functionality
Assessed by evaluating the feature set and capabilities of
the program(i.e Functions, Security)
■Usability
Assessed by considering human factors (aesthetic,
consistency, documentation)
■Reliability
Assessed by measuring accuracy of output
■Performance
Assessed by processing speed, response time, resource
consumption, throughput, efficiency
■Supportability : assess based on maintainability


*Fundamental  Concepts

■Abstraction
■Architecture
■ Patterns
■ Separation of concerns
■ Modularity
■ Hiding
■ Functional independence
■ Refinement
■ Aspects
■ Refactoring
■ OO design concepts
■ Design Classes



**Chapter 9**
Architectural Design

The architecture is not the operational software. Rather,
it is a representation that enables a software engineer
to:
(1) analyze the effectiveness of the design
(2) consider architectural alternatives
(3) reduce the risks


*Architectural Styles

■ Data-centered architectures
■ Data flow architectures
■ Call and return architectures
■ Object-oriented architectures
■ Layered architectures

![[Pasted image 20231211152650.png]]


![[Pasted image 20231211152720.png]]

![[Pasted image 20231211152737.png]]

![[Pasted image 20231211152751.png]]



*Architectural Design

the design should define the external entities (other
systems, devices, people) that the software interacts
with and the nature of the interaction

![[Pasted image 20231211152855.png]]

![[Pasted image 20231211152911.png]]

![[Pasted image 20231211152928.png]]

![[Pasted image 20231211152942.png]]




**Chapter 10**
Component level Design

component 
“… a modular, deployable, and replaceable part of a system that encapsulates implementation and exposes a set of interfaces.””

nOO view:  a component contains a set of collaborating classes

nConventional view: a component contains processing logic, the internal data structures that are required to implement the processing logic, and an interface that enables the component to be invoked and data to be passed to it.

![[Pasted image 20231211153137.png]]

