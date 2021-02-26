## DDD vs Clean Architecture

- https://khalilstemmler.com/articles/software-design-architecture/domain-driven-design-vs-clean-architecture/

## Command Query Segregation

- https://khalilstemmler.com/articles/oop-design-principles/command-query-segregation/

- A *method* is either a `COMMAND` (which performs an action) OR a `QUERY` (that returns data to the caller), but never both
    - `Asking a question shouldn't change the answer`

## Domain Driven Design

- Pluralsight, `Domain-Driven Design Fundamentals`
- Domain driven design is useful when you have a `complex business domain` not `technical complexity`

![](./images/45.png)

### DDD: Modeling Problems in Software

#### Value Objects

#### Bounded Context

- Each bounded context should have it's own team, codebase, and database schema

![](./images/1.png)

- Models mean different things in different contexts
- For example, it wouldn't make sense to stop a client from scheduling an appointment if they didn't have a credit card on file yet

![](./images/2.png)

- If you have multiple contexts you'll want to keep them bounded
    - One way to do this is to keep team members, data, and code separate from one another
    - Rarely seen in real world
    - Having concept in mind helps keep the idea of separation in mind

![](./images/3.png)

#### SubDomain vs Bounded Context

- Subdomain is a problem space concept
- Bounded context is a solution space concept
- Ideally a subdomain would live within a single bounded context cleanly

```
A subdomain is a part of your business. There are core domains, supporting domains and generic domains. Core domains are where the money is, supporting domains support your core business, and generic domains are the ones you need, but don't care a lot about, so you would probably buy them of the shelf. For an insurance company, the core domain is insurance, a supporting domain could be client portfolio, and a generic domain could be something like timesheets.
```

- Think of a floor with carpeting - those are two distinct things
    - The bounded context is the carpeting that had been shapped to fit the flooring (the subdomain)

#### Context Maps

- If an organization has multibounded contexts (ideally separated), there may be confusion when the different teams are talking to one another
- `Context Maps` to visualize and demonstrate to the teams where their boundaries lie
- Common for one team to handle multiple bounded contexts that reside in a single app and with one data source

![](./images/4.png)

- Part of creating a context map involves explicitly defining each bounded context's boundary

<br>

- Nonideal case
![](./images/5.png)

- Ideal case

![](./images/6.png)

- How do you share cross cutting concerns between these apps like authentication?
    - `Shared Kernel`

![](./images/7.png)

#### Our Bounded Contexts for this App

- Because these two teams share `Authentication` now, they agree to not change it without discussing with the other team first

![](./images/8.png)

![](./images/9.png)

- Note here that there are several contexts within the same application which is why the solution is set up the way that it is

![](./images/10.png)

#### Ubiquitous Language

- Effective communication among all stakeholders is key to a successful initiative
- One of the fundamental processes
- Developers and business partners should speak the same language - no translation should be necessary
- Good practice is to explain back to business partners what you think the system should do in terms of the domain
- For a single bounded context the ubiquitous language should be used throughout that context - from conversations to design documents to whiteboarding to emails to code - literally everywhere

#### Terms

- `Problem Domain` - The specific probelm the software you're working on is trying to solve
- `Core Domain` - the key differentiator for the customer's business - something you must do well and cannot oursource
- `SubDomain` - separate applications or features your software must support or interact with
- `Bounded Context` - a specific responsibility, with explicit boundaries that separate it from other parts of the system
    - *Within the context of appointment scheduling, this is what a client looks like*
    - *Within the context of billing, this is what a client looks like*
- `Context Mapping` - the process of identifying bounded contexts and their relationships to one another
- `Shared Kernel` - part of the model that is shared by two or more teams, who agree not to change it without collaboration
    - Authentication
- `Ubiquitous Language` - a language usig terms from the domain model that programmers and domain experts use to discuss the system
    - This is what allows us to be precise within the domain
    - `SchedulingApp.Client` vs `Billing.Client`

<br>

- Common for something like `Customer` to become a god object that everyone in your organization uses but applications really only want a tiny subset of that object for its own use

### Elements of a Domain Model

#### Focus on the Domain

- Not the user interaction
- Not the data access

```
The Domain Layer is responsible for representing concepts of business, information about the business situation, and business rules. State that relects the business situation is controlled and used here, even though the technical details of storing it are delegated to the infrastructure. *This layer is the heart of business software*
```

- Focus on the domain not the technical details of how the software will function
- Focus on the behaviors within the domain not attributes
    - Schedule an appointment for a checkup
    - Note a pet's weight
    - Request lab work
    - Notify pet owners of vaccinations due
    - Accept a new patient
    - Book a room

#### Anemic and Rich Models

- In DDD, models that simply have getters/setters are considered `anemic` and are an anti-pattern
- The domain models should contain the behaviors of the domain

#### Entities in DDD and in Our Bounded Context

- Entities have identity and are mutable

![](./images/11.png)

- Appointment is the main entity here and it extendeds from a base class called entity which assigns an guid (no database required)

![](./images/12.png)

- The other entities in this context are simple crud (not DDD) classes in this context - they don't have complex business rules and it's easy just to have the database assign the int (the id)

<br>

- Using a unique ID for appointment allows us to retrieve, track, and edit an appointment even if some of its values change
- The other classes here needed to be retrieved but not editing is required

![](./images/13.png)

- Notice here that terms like `ClientView`, `ClientDetails` are not used
- We just use `Client` and know what it means because of the context in which we are speaking about it

![](./images/14.png)

#### Entities & Single Responsibility Principle

- Does having a lot of business logic in an entity violate SRP?
- An entity should't have a lot of business logic in it - otherwise as you build out your system, you have to put more and more into the class
- Entities should be responsible for identity and lifecycle
- identity isn't always just an id field
    - This might work where you have something like a UPS package where you have a tracking number for the id that is with it from beginning to end
- If you're trying to identify a customer - you might need their name, address, some other secret information
- Sometimes identity can be so complex you need another object or set of objects to help the entity handle identification
- Lifecycle can be something like a UPS package where it can be `in transit`, `shipped`, `received`, etc
    - If there is a lot of logic around updating/handling the lifecycle, you may want some other services to help with this
    - Entity may also delegate to a value object

#### Should Entities Have Equality Comparers?

- Need to take the cases individually - determing if entities are equal, it can be nontrivial

#### Implementing Entities of Code

- Use static factory methods to help avoid entities being in an *inconsistent state*

![](./images/15.png)

#### Associations (aka relationships)

- Typically we think of relationships bidirectionally

![](./images/16.png)

- Bidirectional relationships can make things more complex

- Domain driven design pushes towards one way relationships
    - You can have them but it is extra complexity
- If you have a bidirectional relationship, neither can be defined without the other
    - `Is a Client without a Patient still a Client?`
    - `Is a Patient without a Client still a Patient?`

![](./images/17.png)

- Start with one-way relationships
    - A client needs a patient to schedule a patient
    - A client would not need a patient to pay a bill
    - A patient (an animal) doesn't schedule an appointment
    - A patient (an animal) doesn't pay a bill

![](./images/18.png)

- After this investigation, it only makes sense for `Client` to have `Patients` in the `Appointment Scheduling Bounded Context`

![](./images/19.png)

#### Value Objects

- Play equally important role as entity object
- It measures, quantifies, or describes a thing in the domain
- Identity is based on the composition of alues
- Immutable - once the instance is created, you'd never change the values
- Compared using all values
- No side effects
    - Should only compute things
    - Should not change state of itself or the system

<br>

- A string is a great example of a value object
- The contents of the string is what gives that thing meaning
- Say the string is `CAR`
    - Changing the `R` -> `T` to be `CAT` gives the string very different meaning even though it'd technically be the same object

<br>

- Money is a great value object
- If a company is worth $USD 50,000,000

![](./images/20.png)

- A good example of a value object inside of our domain is the start and end time for the appointment, you need them together 

![](./images/21.png)

- We should strive to have entities which have very few primitives themselves and instead are made up of value objects
- Try starting with looking at it from the perspective of should it be a value object
- Do certain properties always go together? Maybe that's a good case for a value object

<br>

- From Eric Evans, value objects are a really good place to put methods and logic
    - Better place than entities

![](./images/22.png)

- Value objects don't make sense on their own


#### Value Objects in Code

- Private setters
- User can't set/update state once object is created
- `NewEnd`, `NewDuration`, `NewStart` return a new `DateTimeRange`

![](./images/23.png)
![](./images/24.png)

- In the `AnimalType` example, there's not much logic but it gives us a container for encapsulating the two related properties together as a single value object

#### Entity Logic in Value Objects

- If there is logic that is `classic software logic`, you should put that in value objects
    - Value objects are usually easier to test than entities
    - Entities also then become a critical piece of glue (or orchestrator) between the different value objects
        - But it doesn't do a lot on its own
- You look in the methods of the entities and they read like use cases vs the details of those use cases

#### Domain Services

- Important operations that don't belong to an particular entity or value object
- These services operate as `orchestators` for several different collaboratoring entities/value objects

![](./images/25.png)

- Note here that calling a method on a domain service can adjust the state of the system

- UI layer
    - Frequently combined with Application layer which has behavior necessary for the application but unrelated to the problem domain
        - This is why you see examples like message sending, message processing here
- Domain layer
    - Operations on multiple domain elements
    - Orchestrating some type of workflow
    - Processing an order may require series of steps in multiple domain elements (checks customer info, notify customer, reduce inventory, charges customer, checks inventory, etc)
- Infrastructure often implements interfaces that are defined in the `Domain` layer

![](./images/26.png)

#### Glossary

- Anemic Domain Model
    - Model with classes focused on state management. Good for CRUD
- Rich Domain Model
    - Model with logic focused on behavior, notjust state. Preferred for DDD.
- Entity
    - A mutable class with an identity (not tied to it's property values) used for tracking and persistence
    - Can track it
- Immutable
    - Refers to a type whose state cannot be changed once the object has been instantiated
- Value object
    - Immutable class whose identity is dependent on the combination of its values
- Services
    -Place a model in the model to hold behavior that doesn't belong else where in the domain (e.g. your entities or value objects)
- Side Effects
    - Changes in the state of the application or interaction with the outside work (e.g. infrastructure)
    - For example, if querying state changed a piece of state, that would be a side effect

### Aggregates in Domain-Driven Design

#### Tackling Data Complexity

- One way to reduce complexity is reducing bidirectional relationships
- Another way is using aggregates and aggregate roots
- If your application doesn't have a clear notion of aggregates then the dependencies between your entities can grow out of control

#### Aggregates

- Aggregates consist of one or more aggregates and value objects that change together
- All aggregates must have an `aggregate root` which is the parent object of the aggregate

![](./images/27.png)

- Aggregates can also consist of just one object and that one object would also be the aggregate root
- Data changes to the aggregate should follow `ACID`
    - Atomic, Consistent, Isolated, and Durable
- It is the responsibility of the aggregate root to maintain `invariance`
    - An invariant is something that should always be true for the system to be in a consistent state

![](./images/28.png)

- When thinking about aggregate roots, you should think about what it would mean to the system if you delete it
    - If you have to delete other objects in the aggregate hierarchy, then it's likely the object should be considered an aggregate root 

![](./images/29.png)

- `An aggreagte is a cluster of associated objects that we treate as a unit for the purpose of data changes`

#### Interacting with Aggregates

- You have to go through the aggregate root to talk to other parts of the aggregate
- Only way to get to `Address` is through the `Customer`
- `Customer` can be referenced by other aggregates since it's the aggregate root
- `Order` might reference `Customer`
- `Order` cannot access `Address`

![](./images/30.png)

![](./images/31.png)

- Note here that `Address` doesn't have a direct reference to `Customer` but instead has a `customerId` by which we can get to customer
    - This pattern reduces the number of dependency relationships within the model

![](./images/32.png)

- In this setup, saving an `Appointment` will end of scanning the rest of the nonroot aggregates and saving them as well
- In our case, we don't expect to modify any of the other objects when making an appointment
- Remember that when thinking about if something is an aggregate root, deleting the object should delete the nonroot aggregates as well
    - That is not the case in this example

![](./images/33.png)

- This reflects more of the real world scenario, where an appointment just references the things it needs to make that appointment valid
    - That is why `ids` are used here

#### Using Invariants

- Appointments shouldn't be double booked
- Aggregate Roots responsibility to verify invariants

![](./images/34.png)

![](./images/35.png)

- In this example, `Purchase Order` would be responsible for verifying this invariant
- The individual line items don't know anything about each other

<br>

- Looking back at our own example, `Appoinment` won't know if another `Appointment` has been booked at the same time - but a `Schedule` would

#### Modeling Breakthroughs and Refactoring

- You're not going to get it 100% right the first time
- Your understanding will evolve

![](./images/36.png)

![](./images/37.png)

#### Aggregate Tips

- Exist to redue complexity
- May not always be the answer
- Aggregates can connect only by the root
- Don't overlook using foreign keys for non root entities
    - In Aggregate A, you can reference Aggregate B's non root entities via this foreign key
    - Too many FKs to non-root entities may suggest a problem
- Aggregates of one are acceptable
- Rule of cascading deletes
    - For aggregate roots, deleting it should delete the other nonroot entities

#### Glossary

- Aggregate
    - A group of related objects that work together in a transaction
- Aggregate Root
    - The entry point of an aggregate which ensures the integrity of the entire aggregate
- Invariant
    - A condition that should always be true for the system to be in a consistent state
    - An aggregate root enforces this
- Persistence ignorant classes
    - Classes that have no knowledge about how they are persisted

### Repositories

- Only specific objects, the aggregate roots, should be available upon global request

![](./images/38.png)

- Object life cycles
    - No persistence
    - With persistence

![](./images/39.png)

- The `repository` manages the persistence relevant operationsfor the object
    - The objects that the repository persistences are called `persistence ignorant`

- Eric Evans: `A repository represents all objects of a certain type as a conceptual set...like a collection with more elaborate querying capability`


#### Tips

- Think of it as an in-memory collection - an illusion of a collection
    - Adding, removing, retrieving
- Set up access through a known, common interface

![](./images/40.png)

- Provide methods that predefine criteria for object selection

![](./images/41.png)

- Provide repositories for aggregate roots
- Client focuses on the model, repository focuses on persistence

**Benefits**

- Provide common abstraction for persistence
- Promotes separation of concerns
- Communicates design decisions
    - Only certain objects should be accessed directly and repositories provide and control this
- Enables testability
- Improves maintainability because of the separation of data access from the rest of the application

<br>

- Client code can be ignorant of repository implementation but developers cannot

#### Repositories vs Factories

- Factories create new objects
- Respositories are used to find and exist objects
    - They exist somewhere in persistence
- A repository can use a factory to create its objects

<br>

- Factories do not do anything with persistence
- Repositories do persistence

#### Using a Generic Repository Interface

- Using something like IRepository<T> makes sense when you have standard aggregates that all use CRUD operations, having a generic repository makes a lot of sense
- If you have nonstandard aggregates, then you need to evaluate whether this makes sense or not
- In this course's application's aggregate root - `Schedule` would only need a repository to `GetScheduledAppointmentsForDate` and `Update` an appointment

#### Generic Repositories in DDD

- A generic repository makes life simple but than it means classes can bypass the aggregate root and get information about entities directly via the repository

#### Repositories in this Application

![](./images/42.png)

- Note here that the `IScheduleRepository` is defined within the core of `AppointmentScheduling`
- Implemenation is within the infrastructure of that bounded context

<br>

- You design the domain how you want it to and then persistence layer will likely require some extra work to get the data how you want it

#### Glossary

- Repository
    - A class that encapsulates the data persistence for an aggregate root
    - Don't create repositories for entities within the aggregate
- ACID
    - Atomic (whole transaction occurs or none of it does), Consistent (contrainsts of data are applied), Isolated (if two different aggregates are being committed at the same time, they don't conflict one another - need them to occur in a sequence), and Durable (once transaction has occurred, if something happens to the system, we should be able to reload the state)

### AntiCorruption Layer and Domain Events

- Way to describe important events for state changes within the system so that other parts of the system can respond to the events
- Domain events are encapsulated as objects
- Domain events should be part of the ubiquitous language

![](./images/43.png)

- `When this happens, then something else should also happen`
- Also listen for:
    - `If that happens...`
    - `Notify the user when...`
    - `Inform the user if...`
- Domain events represent the past

**Examples**

- UserAuthenticated
- AppointmentConfirmed
- PaymentReceived

<br>

- Only create them when you need them

##### Designing Domain Events

- Each event is its own class
- Include when the event took place
    - Can be helpful to define an interface to describe common things
- Capture event-specific details
    - What would you need to know to trigger the event again?
    - Any parts of the aggregates?
- Event fields are initialized in the constructor
- No behavior or side effects
- Lightweight

#### Anti-Corruption Layer

- Helps prevent corruption in domain model
- When workign with another bounded context (even in your own system) or some or legacy system, the anti-corruption layer protects assumptions about the other system from leaking into your model
- Translates between foreign systems' models and our own
- May provide patterns like facade, adapter, or custom translation
- `Even when the other system is well designed, it is not based on the same model as the client. And often teh other system is not well designed`

##### The structure of an anti-corruption layer

![](./images/44.png)

- What is needed to insulate your system from other systems
- Their decisions should not bleed into your design

#### Glossary

- Domain event
    - A class that cpatures the occurrence of an event in a domain object
- Hollywood Principle
    - `Don't call us, we'll call you`
    - Domain events allows controlling object to call back to listening objects
- Inversion of Control
    - A pattern for loosely coupling a dependent object with an object it will need at runtime
- Anti-Corruption Layer
    - Functionality that insulates a bounded context and handles interaction with foreign systems or contexts

## Domain Driven Design Distilled

- https://learning.oreilly.com/videos/domain-driven-design-distilled

### Lession 1: DDD for Me

#### Good, Bad, and Effective Design

- When a new framework, some new technology, etc is seen as the means to conquer a particular software problem, the solution often turns out worse than simply using good design principles
    - Favor software development through good design
- One of those things that is often focused on too heavily is the database
    - Database and data model given priority over business process and operations
- Developers oftentimes do not place proper emphasis on naming objects and operations with a business focus
    - Naming is very important
    - Ties mental model of business into software
- Should be able to look at the software and understand the business operations and business processes
- Poor collaboration between stakeholders and developers is a recipe for disaster
    - Software development and business should be melded together
    - Collaboration is a very important tool
- Poor estimates given too much attention and cause delays in productive development
- "Task board shuffle" and "No design" loead to developing a *Big Ball of Mud*
    - Task board shuffle is like a scrum board where task is moved to the `In progress` column and the developers work on it immediately - `No design`
    - Design happens as the code is written
- Developers often house business logic in the user interface and persistence code
- Wrong model abstractions lead to wrong solutions that miss the concrete business needs
- Strong coupling between systems make systems difficult to maintain
    - SOA
    - Microservices
- Failed coupling between services leads to failed business operations and unreconcilable data within the whole system (made up of multiple systems)
- `No design` is a fallacy

##### Effective Design Is Best

- Meets the needs of the business and distinguishes the business from its competition
- This forces companies to focus on what they're best at
    - An insurance company can't be the best database company, it can't be the best framework company

#### Strategic Design

- Most critical software design tools in DDD toolbox
- Bounded context, ubiquitous langauge, sub domains, context mapping

#### Tactical Design

- Aggregates and domain events
    - Aggregates help you to control transactions and maintain invariants with data consistency in your models
    - Domain events help you by modeling facts - the significant events in your model
- Strategic tools are far more important
- Sometimes limited based on language, technical platform, technique using (fp vs oop)

### Strategic Design with Bounded Contexts and the Ubiquitious Language

#### Introduction

- Two of most important tools are the bounded context and the ubiquitous language
- A bounded context is a contextual/semantic boundry
- Everything within this boundary is explicit about the model - it has a specific meaning
    - We know explicitly what each term means
- This language is called ubiquitous because it's spoken by team and it's prevelant in software model
- The language is not ubiquitious in the entire organization
    - This is just talking about a single software project
- The bounded context can be as big as an application
    - The ubiquitious language is what makes the model a specific size
- Ubiquitious language is created by a team and is the result of collaborating with a domain expert in the business (or particular part of the business)
- You can think of a ubiquitous language as similar to human languages
    - Crossing boundaries of countries changes the official language
    - At the same time, speaking Spanish in Spain is slightly different than speaking Spanish in Colombia
    - The same word used in different bounded contexts will likely mean slightly different thing

#### Domain Experts and Business Drivers

- The domain expert has specific knowledge in a particular area of business
- Domain expert is responsible for carrying vision that will create competitive advantage for the business

<br>

- In insurance - underwriting, claims, and inspections are different areas of the business
- Each of these have the concept of a `policy`
- Each area of the business should have a bounded context for their specific model
    - For example, in one bounded context we have a policy specifically modeled for the underwriting area of the business

#### Case Study

- In the area of scrum product management
- Will look at the model for a scrum project management tool

![](./images/46.png)

- A product is the software that the team is developing
- Backlog item is a user story and a set of tasks that a team will be executing on in order to deliver a release within a specific number of sprints
- Sprints have a set of backlog items that are being worked on at a given time

<br>

- Some other things to consider, users need to have different permissions to read/write
- There should be forums where discussions can happen
- There should be calendars and calendar entries

![](./images/47.png)

<br>

- Don't forget that tenant's need to be able to pay for their account
- User's should also be able to report issues

![](./images/48.png)

<br>

- Team than realizes it would be helpful if they could track the product owner and other team members, so that we they can understand how much time-consuming resource each of those has for a specific sprint/release
    - Schedule time and availability
    - This way we can use members of each team on different teams

![](./images/49.png)

<br>

- If they are going to have reminders, milestones, target dates, retrospectives, and planning meetings - model those after a CalendarEntry

![](./images/50.png)

<br>

- This model can keep growing and growing
- This is very quickly leading to a big ball of mud

#### Fundamental Strategic Design Needed

- What tools can we use to avoid the big ball of mud?
    - Bounded context and ubiquitous language
- We want to apply bounded context to the previous modeling situation

<br>

![](./images/51.png)

- How do we do this?
    - Collaboration between domain experts and developers
- Domain expert will have expertise in a specific section of the business

![](./images/52.png)

- There should be a feedback loop between developers and domain experts
- Aha moments will happen when this collaboration occurs

#### Challenge and Unify

- Can break up the big ball of mud by challenging our previous model by using bounded context and ubiquitous language to understand what belongs in and out of the bounded context
- Does tenant, user,and permission belong with the ubiquitous language of scrum?

![](./images/53.png)

- This part of the model, while important to the success of the project, it is NOT part of the scrum bounded context

<br>

- In Scrum, we do think about individuals and how they make up a team
    - ProductOwners and TeamMembers

![](./images/54.png)

<br>

- Does account, supportplan, payment, and incident belong in our Scrum project management tool?
    - No, these ideas are NOT apart of Scrum

![](./images/55.png)

- What about ResourceManager, TimeConsumingResource, Schedule, and Availability
    - This has nothing to do with Scrum itself

![](./images/56.png)

<br>

- What about `Volunteer`?
- Volunteers are people assigned to work on a task
    - This is apart of Scrum

![](./images/57.png)

<br>

- What about Calendar, CalendarEntry, Reminder, Milestone, TargetDate, Retrospective, and Planning?
    - Scrum does talk about retrospectives, planning, milestones
- Put this aside for now, requires more modeling effort

![](./images/58.png)

<br>

- What about `Discussion`?
- Discussion is vital to Scrum, so we do want to model a discussion within our core domain

![](./images/59.png)

- To do this, we will integrate with another bounded context
    - This bounded context deals with collaboration

![](./images/60.png)

<br>

- Actual core domain

![](./images/61.png)

<br>

- What about the rest of the things we took out of the core domain?
- Each of these likely belong to own bounded context

![](./images/62.png)

- **Every DDD project will contain multiple bounded contexts**

#### Architecture

- What does a bounded context actually look like in code?
- What sort of architectural patterns can be used?
- Ports and adapters is pretty common

![](./images/63.png)

- Domain is at the center
- `Application services` manage our transactions for us, maybe security as well
    - Task maangers for the use cases that the software needs to perform
    - These invoke methods on the domain model to carry out the operations
- `Adapters` exist on the outside for the various ports
    - Right side of diagram are ports that are incoming request operations from the outside world
        - For example, for upper left hand corner globe operation - a browser is sending requests to our application
            - Those requests are being adapted by a port adapter specifically made for browsers and it is adapting the requests to the internal application services so that the application services can delegate to the domain model to have the operation executed
        - Mobile phone is another example
    - Left hand side of the diagram are output ports
        - Good example is a repository that talks to a database
        - Sending messages to some messaging engine
            - **Note that the messaging engine (lightning bolt) is an input and output port**
- This architecture is typical for DDD

<br>

- Another view of the architecture tipped on its side

![](./images/64.png)

<br>

- Other architectural patterns that can be used
    - Event driven and event sourcing
    - Command Query Responsibility Segregation (CQRS)
    - Reactive software development with the actor model
        - Allows CQRS and event driven architecture within a bounded context
    - REST
    - Microservices and SOA

### Strategic Design with Subdomains

#### What Is a Subdomain?

- It is a sub-part of the whole business domain
- Business domain is broken up into logical subdomains
- With legacy systems, it may not be possible to talk about one explicit domain model
    - May have multiple logical models
    - Each of these logical models can be referred to as subdomain (as if they were developed using DDD)
- Sphere of knowledge and understanding should be limited to current problem space
    - This includes core domain and other bounded contexts that will need to be intregrated with
- Subdomain can be thought of as a specific area of expertise
    - It should have one clean *Bounded Context* as the *Core Domain*
    - There will be other supportign *Bounded Contexts*

#### Types of Subdomains

##### Core domain

- Core domain
    - Where your organization is making strategic investment in sotware
    - Among highest priority projects
    - Addresses at what your organization must excel by means of software
        - You can't be best IAM service and best project management service
    - How your organizatin will distinguish itself from all others
        - Scrum application management tool in our case

<br>

##### Supporting Subdomain

- Necessary to support a *Core Domain*
Requires custom development because an off-the-self product doesn't exist
- This software doesn't deserve the investment the *Core Domain* gets
    - Decision at the business will have to make
- Consider outsourcing development to avoid heavy investment
- Our scrum application management tool interacts with collaboration context
    - The business may also want to exce in collaboration context, so that could be a core domain as well
    - But in our case, the collaboration context is still a supporting subdomain in the context of our scrum application management application

##### Generic Subdomain

- Necessary, but generic
    - You can't have scrum application tool without it (IAM for example)
- May be possible to purchase off the shelf
- If developed in house, don't assign developers with elite skills, such as with the *Core Domain* team
- IAM is a good example
- Don't want to put same investment as you do the core example

#### Dealing With Complexity

- What happens when you have to integrate with a big ball of mud at some time
- How do you deal with this?
- Can treat each of the logical models within the big ball of mud as if they were their own bounded context

### Strategic Design With Context Mapping

- In our application we have the core domain (agile project management) and then there are various supporting subdomains
- When we integrate our core domain with these other domains, how do we do those integrations?
- What are the relationships between the teams?

#### Partnership

- Two teams work on two different bounded contexts but they have common goals and they support each other
    - Team 1 is in a bounded context
    - Team 2 is in a bounded context
- Teams have to coordinate delivery together, release at the same time
    - No upstream/downstream relationship

![](./images/65.png)

#### Shared Kernel

- At least two teams have a very similar software model
- They develop a single shared portion of a model
- Relatively unusual - takes a lot of coordinating and integration testing

![](./images/66.png)

#### Customer-Supplier

- Upstream/downstream relationship between two teams
- U = upstream (team 1)
- D = downstream (team 2)
- Changes in model for team 1 (upstream) will have an impact on team 2 (downstream)
- Team 2 will request certain features in model developed by team 1
- Requires coordination between the teams
- Typically works when the cusomter is the sole client of the supplier

![](./images/67.png)

#### Conformist

- Upstream/downstream relationship
- Team 1 has upstream model that will directly impact team 2
- Team 2 basically consumes model directly from team 1
    - Team 2 conforms to the model
    - Model is so big and complex that team 2 doesn't want to deal directly with it
- Team 1 has no interest in supporting downstream which is why downstream must conform to whatever the upstream provides

#### Anti-corruption Layer

- Two teams with two separate models
- Downstream team doesn't want to be influenced by upstream model
- Upstream team has its own model
    - Downstream model receives model from team 1 and then translates it to its own model internally
- Opposite of `Conformist` pattern
![](./images/68.png)

#### Open Host Service

- Team 1 publishes API (restful, messaging, rpc, etc) that team 2 directly integrates with because it is very convenient to do so
- Team 2 consumes model as it is without translating (or can easily translates with ACL)

![](./images/69.png)

#### Published Language

- Upstream, team 1,produces well defined well document data exchange format that allows team 2 to easily and comfortably consume data from team 1
- Common for the producer of an `open host service` to provide a published language to the downstream service

![](./images/70.png)

#### Separate Ways

- Team 2 stops using Team 1's service and consuming their model
    - Could be variety of reasons like inconvenience

![](./images/71.png)

#### Big Ball of Mud

- You will likely need to integrate with a big ball of mud at some point
- When you make changes in one part of the model it will likely have a negative impact on another part of the model
- Rippling effects
- If you do need to integrate with it, use an ACL in your service to protect yourself against it

#### Making Good Use of Context Mapping

- How will we actually use context mapping for integration between context mapping?
- 3 main different stypes: RPC, RESTful, and Messaging

##### RPC with SOAP

![](./images/72.png)

- Disadvantage is RPC can fail because of network situations, bandwidths, interruptions in network connections
- When RPC works, it can be convenient way to implement an integration
    - Service bounded context will likely benefit from using Open Host Service and Published Language
    - Client can use anticorruption language

![](./images/73.png)

##### RESTful HTTP

- Client bounded context communicates with service bounded context over the network
    - Service bounded context will likely benefit from using Open Host Service and Published Language
    - Client can use anticorruption language
- Networking can be a problem here just like RPC
- When designing resources for your service, you should design the resources according to the use cases that your client wants to consume
    - Multiple clients could mean the service having different resource actions per client
    - This stops services from forcing a conformist relationship
    - Services cause a conformist relationship when resources are designed around its own internal domain model

##### Messaging

![](./images/74.png)

- An aggregate will publish a domain event, that domain event will be made available to other subscribing bounded contexts
    - In the below diagram, this impacts the aggregate in the client bounded context

![](./images/75.png)

- Sometimes the client will need to issue a `command` so that the publishing bounded context will emit a domain event which will eventually come back to itself (the client)

![](./images/76.png)

- When using domain events with a messaging mechanism, the messaging mechanism must support `at least once delivery` and the subscribing bounded context must be an `idempotent receiver` (client must be able to handle messages it has already received)

![](./images/77.png)

- A duplicate message from the messaging mechanism could be sent to the receiver because receiver didn't send ACK quickly enough
- Receiver must be able to handle this
- Deduplication is common to handle this

##### An Example in Context Mapping

- Example of insurance policy in 3 different areas of insurance: underwriting, inspections, claims

![](./images/78.png)

- Policy first becomes created in the `underwriting context`
    - Agreement with customer to insure them
    - Policy is `issued`

![](./images/79.png)

- Claims context will created policy of its own type in reaction to the policy issue domain event from the underwriting context
    - Same is true for inspections context
- How much data does the `policy issue` domain event have?
    - Should be somewhat limited - shouldn't be the entire policy from the underwriting context
    - Should be enough for the subscribers to do something with it
- What if one subscribing context needs more data than others?
    - You can allow the subscribing context to query back to the underwriting context using `issuedPolicyId` to get the remaining data that it needs

![](./images/80.png)

- The underwriting context will have some sort of OHS/PL that allows the subscribing bounded context to query it
    - For example, `GET /policies/{issuedPolicyId}`

![](./images/81.png)

### Tatical Design With Aggregates