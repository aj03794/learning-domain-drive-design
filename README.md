
* 1. [DDD vs Clean Architecture](#DDDvsCleanArchitecture)
* 2. [Command Query Segregation](#CommandQuerySegregation)
* 3. [ 3. Domain-Driven Design Fundamentals](#3.Domain-DrivenDesignFundamentals)
	* 3.1. [DDD: Modeling Problems in Software](#DDD:ModelingProblemsinSoftware)
		* 3.1.1. [Value Objects](#ValueObjects)
		* 3.1.2. [Bounded Context](#BoundedContext)
		* 3.1.3. [SubDomain vs Bounded Context](#SubDomainvsBoundedContext)
		* 3.1.4. [Context Maps](#ContextMaps)
		* 3.1.5. [Our Bounded Contexts for this App](#OurBoundedContextsforthisApp)
		* 3.1.6. [Ubiquitous Language](#UbiquitousLanguage)
		* 3.1.7. [Terms](#Terms)
	* 3.2. [Elements of a Domain Model](#ElementsofaDomainModel)
		* 3.2.1. [Focus on the Domain](#FocusontheDomain)
		* 3.2.2. [Anemic and Rich Models](#AnemicandRichModels)
		* 3.2.3. [Entities in DDD and in Our Bounded Context](#EntitiesinDDDandinOurBoundedContext)
		* 3.2.4. [Entities & Single Responsibility Principle](#EntitiesSingleResponsibilityPrinciple)
		* 3.2.5. [Should Entities Have Equality Comparers?](#ShouldEntitiesHaveEqualityComparers)
		* 3.2.6. [Implementing Entities of Code](#ImplementingEntitiesofCode)
		* 3.2.7. [Associations (aka relationships)](#Associationsakarelationships)
		* 3.2.8. [Value Objects](#ValueObjects-1)
		* 3.2.9. [Value Objects in Code](#ValueObjectsinCode)
		* 3.2.10. [Entity Logic in Value Objects](#EntityLogicinValueObjects)
		* 3.2.11. [Domain Services](#DomainServices)
		* 3.2.12. [Glossary](#Glossary)
	* 3.3. [Aggregates in Domain-Driven Design](#AggregatesinDomain-DrivenDesign)
		* 3.3.1. [Tackling Data Complexity](#TacklingDataComplexity)
		* 3.3.2. [Aggregates](#Aggregates)
		* 3.3.3. [Interacting with Aggregates](#InteractingwithAggregates)
		* 3.3.4. [Using Invariants](#UsingInvariants)
		* 3.3.5. [Modeling Breakthroughs and Refactoring](#ModelingBreakthroughsandRefactoring)
		* 3.3.6. [Aggregate Tips](#AggregateTips)
		* 3.3.7. [Glossary](#Glossary-1)
	* 3.4. [Repositories](#Repositories)
		* 3.4.1. [Tips](#Tips)
		* 3.4.2. [Repositories vs Factories](#RepositoriesvsFactories)
		* 3.4.3. [Using a Generic Repository Interface](#UsingaGenericRepositoryInterface)
		* 3.4.4. [Generic Repositories in DDD](#GenericRepositoriesinDDD)
		* 3.4.5. [Repositories in this Application](#RepositoriesinthisApplication)
		* 3.4.6. [Glossary](#Glossary-1)
	* 3.5. [AntiCorruption Layer and Domain Events](#AntiCorruptionLayerandDomainEvents)
		* 3.5.1. [Anti-Corruption Layer](#Anti-CorruptionLayer)
		* 3.5.2. [Glossary](#Glossary-1)
* 4. [Domain Driven Design Distilled](#DomainDrivenDesignDistilled)
	* 4.1. [Lession 1: DDD for Me](#Lession1:DDDforMe)
		* 4.1.1. [Good, Bad, and Effective Design](#GoodBadandEffectiveDesign)
		* 4.1.2. [Strategic Design](#StrategicDesign)
		* 4.1.3. [Tactical Design](#TacticalDesign)
	* 4.2. [Strategic Design with Bounded Contexts and the Ubiquitious Language](#StrategicDesignwithBoundedContextsandtheUbiquitiousLanguage)
		* 4.2.1. [Introduction](#Introduction)
		* 4.2.2. [Domain Experts and Business Drivers](#DomainExpertsandBusinessDrivers)
		* 4.2.3. [Case Study](#CaseStudy)
		* 4.2.4. [Fundamental Strategic Design Needed](#FundamentalStrategicDesignNeeded)
		* 4.2.5. [Challenge and Unify](#ChallengeandUnify)
		* 4.2.6. [Architecture](#Architecture)
	* 4.3. [Strategic Design with Subdomains](#StrategicDesignwithSubdomains)
		* 4.3.1. [What Is a Subdomain?](#WhatIsaSubdomain)
		* 4.3.2. [Types of Subdomains](#TypesofSubdomains)
		* 4.3.3. [Dealing With Complexity](#DealingWithComplexity)
	* 4.4. [Strategic Design With Context Mapping](#StrategicDesignWithContextMapping)
		* 4.4.1. [Partnership](#Partnership)
		* 4.4.2. [Shared Kernel](#SharedKernel)
		* 4.4.3. [Customer-Supplier](#Customer-Supplier)
		* 4.4.4. [Conformist](#Conformist)
		* 4.4.5. [Anti-corruption Layer](#Anti-corruptionLayer)
		* 4.4.6. [Open Host Service](#OpenHostService)
		* 4.4.7. [Published Language](#PublishedLanguage)
		* 4.4.8. [Separate Ways](#SeparateWays)
		* 4.4.9. [Big Ball of Mud](#BigBallofMud)
		* 4.4.10. [Making Good Use of Context Mapping](#MakingGoodUseofContextMapping)
	* 4.5. [Tatical Design With Aggregates](#TaticalDesignWithAggregates)
		* 4.5.1. [Why Used?](#WhyUsed)
		* 4.5.2. [Aggregate Rules of Thumb](#AggregateRulesofThumb)
		* 4.5.3. [Modeling Aggregates](#ModelingAggregates)
		* 4.5.4. [Choose Your Abstractions Carefully](#ChooseYourAbstractionsCarefully)
		* 4.5.5. [Right-Sizing Aggregates](#Right-SizingAggregates)
		* 4.5.6. [Testable Units](#TestableUnits)
	* 4.6. [Tactical Design with Domain Events](#TacticalDesignwithDomainEvents)
		* 4.6.1. [Introduction](#Introduction-1)
		* 4.6.2. [Designing, Implementing, and Using Domain Events](#DesigningImplementingandUsingDomainEvents)
		* 4.6.3. [Event Sourcing](#EventSourcing)
	* 4.7. [Acceleration and Management Tools](#AccelerationandManagementTools)
		* 4.7.1. [Introduction](#Introduction-1)
		* 4.7.2. [Event Storming](#EventStorming)
		* 4.7.3. [Managing DDD on an Agile Project](#ManagingDDDonanAgileProject)
* 5. [Domain Services vs Application Services](#DomainServicesvsApplicationServices)
	* 5.1. [Domain Services vs Application Services](#DomainServicesvsApplicationServices-1)
	* 5.2. [When to extract to a domain service?](#Whentoextracttoadomainservice)

<!-- vscode-markdown-toc-config
	numbering=true
	autoSave=true
	/vscode-markdown-toc-config -->
<!-- /vscode-markdown-toc -->

## <a name='DDDvsCleanArchitecture'></a>DDD vs Clean Architecture

- https://khalilstemmler.com/articles/software-design-architecture/domain-driven-design-vs-clean-architecture/

## <a name='CommandQuerySegregation'></a>Command Query Segregationn

- https://khalilstemmler.com/articles/oop-design-principles/command-query-segregation/

- A *method* is either a `COMMAND` (which performs an action) OR a `QUERY` (that returns data to the caller), but never both
    - `Asking a question shouldn't change the answer`

## <a name='3.Domain-DrivenDesignFundamentals'></a> 3. Domain-Driven Design Fundamentalss

- Pluralsight, `Domain-Driven Design Fundamentals`
- Domain driven design is useful when you have a `complex business domain` not `technical complexity`

![](./images/45.png)

### Benefits

- Flexible
- Customer's vision/perspective of the problem
- Path through a very complex problem
- Well-organized and easily tested code
- Business logic lives in one place

### Drawbacks

- DDD is designed to work in a domain with a lot of business complexity - NOT technical complexity
- Getting team or company buy-in to DDD

### <a name='DDD:ModelingProblemsinSoftware'></a>DDD: Modeling Problems in Softwaree

#### <a name='ValueObjects'></a>Value Objects

#### <a name='BoundedContext'></a>Bounded Context

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

#### <a name='SubDomainvsBoundedContext'></a>SubDomain vs Bounded Contextt

- Subdomain is a problem space concept
- Bounded context is a solution space concept
- Ideally a subdomain would live within a single bounded context cleanly
- `A subdomain is a part of your business. There are core domains, supporting domains and generic domains. Core domains are where the money is, supporting domains support your core business, and generic domains are the ones you need, but don't care a lot about, so you would probably buy them of the shelf. For an insurance company, the core domain is insurance, a supporting domain could be client portfolio, and a generic domain could be something like timesheets.`

- Think of a floor with carpeting - those are two distinct things
    - The bounded context is the carpeting that had been shapped to fit the flooring (the subdomain)

<br>

- Ideally each subdomain would live in its own bounded context

#### <a name='ContextMaps'></a>Context Mapss

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

#### <a name='OurBoundedContextsforthisApp'></a>Our Bounded Contexts for this Appp

- Because these two teams share `Authentication` now, they agree to not change it without discussing with the other team first

![](./images/8.png)

![](./images/9.png)

- Note here that there are several contexts within the same application which is why the solution is set up the way that it is

![](./images/10.png)

#### <a name='UbiquitousLanguage'></a>Ubiquitous Languagee

- Effective communication among all stakeholders is key to a successful initiative
- One of the fundamental processes
- Developers and business partners should speak the same language - no translation should be necessary
- Good practice is to explain back to business partners what you think the system should do in terms of the domain
- For a single bounded context the ubiquitous language should be used throughout that context - from conversations to design documents to whiteboarding to emails to code - literally everywhere

#### <a name='Terms'></a>Termss

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

### <a name='ElementsofaDomainModel'></a>Elements of a Domain Modell

#### <a name='FocusontheDomain'></a>Focus on the Domainn

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

#### <a name='AnemicandRichModels'></a>Anemic and Rich Modelss

- In DDD, models that simply have getters/setters are considered `anemic` and are an anti-pattern
- The domain models should contain the behaviors of the domain

#### <a name='EntitiesinDDDandinOurBoundedContext'></a>Entities in DDD and in Our Bounded Contextt

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

#### <a name='EntitiesSingleResponsibilityPrinciple'></a>Entities & Single Responsibility Principlee

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

#### <a name='ShouldEntitiesHaveEqualityComparers'></a>Should Entities Have Equality Comparers??

- Need to take the cases individually - determing if entities are equal, it can be nontrivial

#### <a name='ImplementingEntitiesofCode'></a>Implementing Entities of Codee

- Use static factory methods to help avoid entities being in an *inconsistent state*

![](./images/15.png)

#### <a name='Associationsakarelationships'></a>Associations (aka relationships))

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

#### <a name='ValueObjects-1'></a>Value Objectss

- Play equally important role as entity object
- It measures, quantifies, or describes a thing in the domain
- Identity is based on the composition of values
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


#### <a name='ValueObjectsinCode'></a>Value Objects in Codee

- Private setters
- User can't set/update state once object is created
- `NewEnd`, `NewDuration`, `NewStart` return a new `DateTimeRange`

![](./images/23.png)
![](./images/24.png)

- In the `AnimalType` example, there's not much logic but it gives us a container for encapsulating the two related properties together as a single value object

#### <a name='EntityLogicinValueObjects'></a>Entity Logic in Value Objectss

- If there is logic that is `classic software logic`, you should put that in value objects
    - Value objects are usually easier to test than entities
    - Entities also then become a critical piece of glue (or orchestrator) between the different value objects
        - But it doesn't do a lot on its own
- You look in the methods of the entities and they read like use cases vs the details of those use cases

#### <a name='DomainServices'></a>Domain Servicess

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

#### <a name='Glossary'></a>Glossaryy

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

### <a name='AggregatesinDomain-DrivenDesign'></a>Aggregates in Domain-Driven Designn

#### <a name='TacklingDataComplexity'></a>Tackling Data Complexityy

- One way to reduce complexity is reducing bidirectional relationships
- Another way is using aggregates and aggregate roots
- If your application doesn't have a clear notion of aggregates then the dependencies between your entities can grow out of control

#### <a name='Aggregates'></a>Aggregatess

- Aggregates consist of one or more aggregates and value objects that change together
- All aggregates must have an `aggregate root` which is the parent object of the aggregate

![](./images/27.png)

- Aggregates can also consist of just one object and that one object would also be the aggregate root
- Data changes to the aggregate should follow `ACID`
    - Atomic, Consistent, Isolated, and Durable
- It is the responsibility of the aggregate root to maintain `invariants`
    - An invariant is something that should always be true for the system to be in a consistent state

![](./images/28.png)

- When thinking about aggregate roots, you should think about what it would mean to the system if you delete it
    - If you have to delete other objects in the aggregate hierarchy, then it's likely the object should be considered an aggregate root 

![](./images/29.png)

- `An aggreagte is a cluster of associated objects that we treate as a unit for the purpose of data changes`

#### <a name='InteractingwithAggregates'></a>Interacting with Aggregatess

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

#### <a name='UsingInvariants'></a>Using Invariantss

- Appointments shouldn't be double booked
- Aggregate Roots responsibility to verify invariants

![](./images/34.png)

![](./images/35.png)

- In this example, `Purchase Order` would be responsible for verifying this invariant
- The individual line items don't know anything about each other

<br>

- Looking back at our own example, `Appoinment` won't know if another `Appointment` has been booked at the same time - but a `Schedule` would

#### <a name='ModelingBreakthroughsandRefactoring'></a>Modeling Breakthroughs and Refactoringg

- You're not going to get it 100% right the first time
- Your understanding will evolve

![](./images/36.png)

![](./images/37.png)

#### <a name='AggregateTips'></a>Aggregate Tipss

- Exist to redue complexity
- May not always be the answer
- Aggregates can connect only by the root
- Don't overlook using foreign keys for non root entities
    - In Aggregate A, you can reference Aggregate B's non root entities via this foreign key
    - Too many FKs to non-root entities may suggest a problem
- Aggregates of one are acceptable
- Rule of cascading deletes
    - For aggregate roots, deleting it should delete the other nonroot entities

#### <a name='Glossary-1'></a>Glossaryy

- Aggregate
    - A group of related objects that work together in a transaction
- Aggregate Root
    - The entry point of an aggregate which ensures the integrity of the entire aggregate
- Invariant
    - A condition that should always be true for the system to be in a consistent state
    - An aggregate root enforces this
- Persistence ignorant classes
    - Classes that have no knowledge about how they are persisted

### <a name='Repositories'></a>Repositoriess

- Only specific objects, the aggregate roots, should be available upon global request

![](./images/38.png)

- Object life cycles
    - No persistence
    - With persistence

![](./images/39.png)

- The `repository` manages the persistence relevant operationsfor the object
    - The objects that the repository persistences are called `persistence ignorant`

- Eric Evans: `A repository represents all objects of a certain type as a conceptual set...like a collection with more elaborate querying capability`


#### <a name='Tips'></a>Tipss

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

#### <a name='RepositoriesvsFactories'></a>Repositories vs Factoriess

- Factories create new objects
- Respositories are used to find and exist objects
    - They exist somewhere in persistence
- A repository can use a factory to create its objects

<br>

- Factories do not do anything with persistence
- Repositories do persistence

#### <a name='UsingaGenericRepositoryInterface'></a>Using a Generic Repository Interfacee

- Using something like IRepository<T> makes sense when you have standard aggregates that all use CRUD operations, having a generic repository makes a lot of sense
- If you have nonstandard aggregates, then you need to evaluate whether this makes sense or not
- In this course's application's aggregate root - `Schedule` would only need a repository to `GetScheduledAppointmentsForDate` and `Update` an appointment

#### <a name='GenericRepositoriesinDDD'></a>Generic Repositories in DDDD

- A generic repository makes life simple but than it means classes can bypass the aggregate root and get information about entities directly via the repository

#### <a name='RepositoriesinthisApplication'></a>Repositories in this Applicationn

![](./images/42.png)

- Note here that the `IScheduleRepository` is defined within the core of `AppointmentScheduling`
- Implemenation is within the infrastructure of that bounded context

<br>

- You design the domain how you want it to and then persistence layer will likely require some extra work to get the data how you want it

#### <a name='Glossary-1'></a>Glossaryy

- Repository
    - A class that encapsulates the data persistence for an aggregate root
    - Don't create repositories for entities within the aggregate
- ACID
    - Atomic (whole transaction occurs or none of it does), Consistent (contrainsts of data are applied), Isolated (if two different aggregates are being committed at the same time, they don't conflict one another - need them to occur in a sequence), and Durable (once transaction has occurred, if something happens to the system, we should be able to reload the state)

### <a name='AntiCorruptionLayerandDomainEvents'></a>AntiCorruption Layer and Domain Eventss

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

#### <a name='Anti-CorruptionLayer'></a>Anti-Corruption Layerr

- Helps prevent corruption in domain model
- When workign with another bounded context (even in your own system) or some or legacy system, the anti-corruption layer protects assumptions about the other system from leaking into your model
- Translates between foreign systems' models and our own
- May provide patterns like facade, adapter, or custom translation
- `Even when the other system is well designed, it is not based on the same model as the client. And often teh other system is not well designed`

##### The structure of an anti-corruption layer

![](./images/44.png)

- What is needed to insulate your system from other systems
- Their decisions should not bleed into your design

#### <a name='Glossary-1'></a>Glossaryy

- Domain event
    - A class that cpatures the occurrence of an event in a domain object
- Hollywood Principle
    - `Don't call us, we'll call you`
    - Domain events allows controlling object to call back to listening objects
- Inversion of Control
    - A pattern for loosely coupling a dependent object with an object it will need at runtime
- Anti-Corruption Layer
    - Functionality that insulates a bounded context and handles interaction with foreign systems or contexts

## <a name='DomainDrivenDesignDistilled'></a>Domain Driven Design Distilledd

- https://learning.oreilly.com/videos/domain-driven-design-distilled

### <a name='Lession1:DDDforMe'></a>Lession 1: DDD for Mee

#### <a name='GoodBadandEffectiveDesign'></a>Good, Bad, and Effective Designn

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

#### <a name='StrategicDesign'></a>Strategic Designn

- Most critical software design tools in DDD toolbox
- Bounded context, ubiquitous langauge, sub domains, context mapping

#### <a name='TacticalDesign'></a>Tactical Designn

- Aggregates and domain events
    - Aggregates help you to control transactions and maintain invariants with data consistency in your models
    - Domain events help you by modeling facts - the significant events in your model
- Strategic tools are far more important
- Sometimes limited based on language, technical platform, technique using (fp vs oop)

### <a name='StrategicDesignwithBoundedContextsandtheUbiquitiousLanguage'></a>Strategic Design with Bounded Contexts and the Ubiquitious Languagee

#### <a name='Introduction'></a>Introductionn

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

#### <a name='DomainExpertsandBusinessDrivers'></a>Domain Experts and Business Driverss

- The domain expert has specific knowledge in a particular area of business
- Domain expert is responsible for carrying vision that will create competitive advantage for the business

<br>

- In insurance - underwriting, claims, and inspections are different areas of the business
- Each of these have the concept of a `policy`
- Each area of the business should have a bounded context for their specific model
    - For example, in one bounded context we have a policy specifically modeled for the underwriting area of the business

#### <a name='CaseStudy'></a>Case Studyy

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

#### <a name='FundamentalStrategicDesignNeeded'></a>Fundamental Strategic Design Neededd

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

#### <a name='ChallengeandUnify'></a>Challenge and Unifyy

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

#### <a name='Architecture'></a>Architecturee

- What does a bounded context actually look like in code?
- What sort of architectural patterns can be used?
- Ports and adapters is pretty common

![](./images/63.png)

- Domain is at the center
- `Application services` manage our transactions for us, maybe security as well
    - Task managers for the use cases that the software needs to perform
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

### <a name='StrategicDesignwithSubdomains'></a>Strategic Design with Subdomainss

#### <a name='WhatIsaSubdomain'></a>What Is a Subdomain??

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

#### <a name='TypesofSubdomains'></a>Types of Subdomainss

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

#### <a name='DealingWithComplexity'></a>Dealing With Complexityy

- What happens when you have to integrate with a big ball of mud at some time
- How do you deal with this?
- Can treat each of the logical models within the big ball of mud as if they were their own bounded context

### <a name='StrategicDesignWithContextMapping'></a>Strategic Design With Context Mappingg

- In our application we have the core domain (agile project management) and then there are various supporting subdomains
- When we integrate our core domain with these other domains, how do we do those integrations?
- What are the relationships between the teams?

#### <a name='Partnership'></a>Partnershipp

- Two teams work on two different bounded contexts but they have common goals and they support each other
    - Team 1 is in a bounded context
    - Team 2 is in a bounded context
- Teams have to coordinate delivery together, release at the same time
    - No upstream/downstream relationship

![](./images/65.png)

#### <a name='SharedKernel'></a>Shared Kernell

- At least two teams have a very similar software model
- They develop a single shared portion of a model
- Relatively unusual - takes a lot of coordinating and integration testing

![](./images/66.png)

#### <a name='Customer-Supplier'></a>Customer-Supplierr

- Upstream/downstream relationship between two teams
- U = upstream (team 1)
- D = downstream (team 2)
- Changes in model for team 1 (upstream) will have an impact on team 2 (downstream)
- Team 2 will request certain features in model developed by team 1
- Requires coordination between the teams
- Typically works when the cusomter is the sole client of the supplier

![](./images/67.png)

#### <a name='Conformist'></a>Conformistt

- Upstream/downstream relationship
- Team 1 has upstream model that will directly impact team 2
- Team 2 basically consumes model directly from team 1
    - Team 2 conforms to the model
    - Model is so big and complex that team 2 doesn't want to deal directly with it
- Team 1 has no interest in supporting downstream which is why downstream must conform to whatever the upstream provides

#### <a name='Anti-corruptionLayer'></a>Anti-corruption Layerr

- Two teams with two separate models
- Downstream team doesn't want to be influenced by upstream model
- Upstream team has its own model
    - Downstream model receives model from team 1 and then translates it to its own model internally
- Opposite of `Conformist` pattern
![](./images/68.png)

#### <a name='OpenHostService'></a>Open Host Servicee

- Team 1 publishes API (restful, messaging, rpc, etc) that team 2 directly integrates with because it is very convenient to do so
- Team 2 consumes model as it is without translating (or can easily translates with ACL)

![](./images/69.png)

#### <a name='PublishedLanguage'></a>Published Languagee

- Upstream, team 1,produces well defined well document data exchange format that allows team 2 to easily and comfortably consume data from team 1
- Common for the producer of an `open host service` to provide a published language to the downstream service

![](./images/70.png)

#### <a name='SeparateWays'></a>Separate Wayss

- Team 2 stops using Team 1's service and consuming their model
    - Could be variety of reasons like inconvenience

![](./images/71.png)

#### <a name='BigBallofMud'></a>Big Ball of Mudd

- You will likely need to integrate with a big ball of mud at some point
- When you make changes in one part of the model it will likely have a negative impact on another part of the model
- Rippling effects
- If you do need to integrate with it, use an ACL in your service to protect yourself against it

#### <a name='MakingGoodUseofContextMapping'></a>Making Good Use of Context Mappingg

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

### <a name='TaticalDesignWithAggregates'></a>Tatical Design With Aggregatess

#### <a name='WhyUsed'></a>Why Used??

![](./images/82.png)

- All the circled items are the aggregate
    - Other object is a `value object`
- An aggregate has a few different parts to it
    - Root entity
        - Called `aggregate root`
    - May also hold other `entities` and `value objects`
- The `aggregate root` names the concept of the entire aggregate
    - Global unique identity

![](./images/83.png)

- An aggregate is a `transactional consistent boundary`
     - Inside an aggregate, everything must be consistent at the end of a transaction
     - At the beginning of a use case, a transaction is started
     - The aggregate makes its changes
     - Transaction finished
     - Transaction commits
     - Everything within a single aggregate boundary is consistent and up to date
- A single transaction does NOT span multiple aggregates
- It's a transactional boundary

![](./images/84.png)

#### <a name='AggregateRulesofThumb'></a>Aggregate Rules of Thumbb

- Protect business invariants inside Aggregate boundaries
- Design small Aggregates
- Reference other Aggregates by identity only
- Update other Aggregates using eventual consistency

##### Rule 1: Protect Business Invariants

- In our example `Product Aggregate` and `Sprint Aggregate` are `controlled under separate transactions`
- Aggregate roots are `Product` and `Sprint`
- Business invariants are being protected individually

![](./images/85.png)

- When all tasks under a backlog item have `hoursRemaining == 0`, then status of BacklogItem is `status == done`
- When there is a single task remaining status of BacklogItem is `status == inprogress`
    - When the last task is finished, a transaction is started in the BacklogItem Aggregate, at the end of the transaction, status is updated to `done` and transaction is committed
        - This is a business constraint is required to be consistent at all times so it must be done within the same transaction

![](./images/86.png)

##### Rule 2: Design Small Aggregates

- It is possible to design it this way, but that is a large aggregate

![](./images/87.png)

- This large aggregate design will likely cause transactional failures because of separate users with different goals modifying the same aggregate in separate transactions
    - Committing a backlog item to a sprint and we plan a new backlog item `at the same time by two different users`, this will change different parts of the same aggregate instance at the same time causing failure
        - One of these transactions will succeed and the other will fail
        - Concurrency violation in database
- Size of aggregate in memory takes us a lot of memory, slower to load, etc

<br>

- A smaller aggregate design could look like the following

![](./images/88.png)

##### Rule 3: Reference by Identity Only

- Child aggregates- backlog item, release, sprint - need to know parent aggregate (product), and that be done using `ProductId`
- Smaller memory footprint when doing this
- Cannot reach out to parent aggregate directly and make a modification to it at the same time one of the child aggregates is being modified
    - Not tempted to break rule 1 

![](./images/89.png)

##### Rule 4: Update Other Aggregates Eventally (Eventual Consistency)

- When a backlog item is committed to a sprint, backlog item is going to hold a reference to the sprint to which it is now committed
- When the backlog item is commited to a sprint and the sprintId is set on it, that backlog item is going to be committed in a single transaction
    - The sprint aggregate does not yet know that the backlog item has been committed to it
    - Eventually the sprint will know about it and it will now hold a committed backlog item instance
    - This entity will be set in a separate transaction
    - The `BacklogItem` will emit a `BacklogItemCommitted` message, the `Sprint` will use that to create a new `CommittedBacklogItem`

![](./images/90.png)

- This works using messaging

![](./images/91.png)

- In our instance, the `agile product management context` is listening to its own domain event

![](./images/92.png)

#### <a name='ModelingAggregates'></a>Modeling Aggregatess

- Don't model using an `anemic domain model`
    - This domain model is usually missing all of the business logic
    - Usually just have getters/setters

<br>

- How to model aggregates appropriately?
- Remember that an aggregate is a transactional consistency boundary
- You must always have a `root entity` at least for an aggregate
- May have other entites or value objects
- `Root entity` is named is such a way that it names the entire aggregate concept

![](./images/93.png)

- Don't necessarily need an `Entity` supertype if it helps
- `TenantId` allows different tenants to subscribe to this service
    - Each tenant will have a different Id
- Product class will hold 2 other properties - a name and a description

![](./images/94.png)

- Accessor will exist to `get` both `Name` and `Description`, but the `setter` is private 

![](./images/95.png)

- Why a private `setter`?
- This will make you design behavior in the product root entity
    - This is because this behavior will be able to use the private setters
- This forces clients to use the public behavior only

<br>

- As designing and modeling aggregates, we will use the ubiquitious language in code

![](./images/96.png)

#### <a name='ChooseYourAbstractionsCarefully'></a>Choose Your Abstractions Carefullyy

- The ubiqutious language in the `Scrum Project Management` domain naturally uses language like:
    - Product
    - BacklogItem
    - Release
    - Sprint
- Our model should be designed in code with these concepts in mind

<br>

- It is possible to go in a different direction
- What if developers tried to overabstract the model?
    - They wouldn't use the ubiquitious language in code
    - They might use something like
        - ScrumElement (could be used to model Product and BacklogItem)
        - ScrumElementContainer (could be used for Release and Sprint) - it would contain ScrumElement(s)
- We are moving against the ubiquitous language that is spoken in Scrum
    - ScrumElement and ScrumElementContainer do not properly represent the concrete items that live in Scrum Project Management

<br>

##### Problems with Wrong Abstractions

- Hard to model details of specific types
- Special cases and complex class hierarchies
- More code than necessary than if modeling explicitly
    - General purpose concepts require much more code
- Will influence user interface negatively
- Waste time and money pursuing wrong design
- Imagined future proofing your design will meet with failure when future concepts realized

##### Model Explicitly Per Ubiquitous Language

- Adheres to the mental model of *Domain Model*
- Creates an understandable model
- Protects the organization's software investment
- Saves time and money

#### <a name='Right-SizingAggregates'></a>Right-Sizing Aggregatess

##### Modeling Steps

- Design small aggregates
    - Design all aggregates with just one entity if possible
    - In the below example, we would remove the entity and make it the root entity in its own aggregate

![](./images/97.png)

- Protect business invariants
    - Make a chart with Aggregate names and list dependents (other aggregates that will need to be updated) under each
- Ask Domain Experts for an acceptable time frames for updates to each dependents
    - Will either need to be immediate or eventually (N number of seconds/minutes/hours/days/etc)
    - House all immediate updates under one Aggregate
        - In our example, if the entity that is dependent upon the root entity needs to be immediately updated, it will need to be housed inside our aggregate
    - If update can be eventual, plan to update all dependents eventually

![](./images/98.png)

- In this example, A2 must be updated immediately following A1
    - This means it needs to be in the same A aggregate, so they both need to be housed under Aggregate A
- Aggregate C14 can be eventually consistent, this can happen via a domain event

#### <a name='TestableUnits'></a>Testable Unitss

- Aggregate designs should accomodate unit testings

##### Unit Test Aggregates

- Designing small aggregates will help make Aggregates testable
- Unit tests are different from acceptance tests
- Test for correctness and robustness of each Component

### <a name='TacticalDesignwithDomainEvents'></a>Tactical Design with Domain Eventss

#### <a name='Introduction-1'></a>Introductionn

![](./images/99.png)

##### Causal Consistency

- Example about posts and discussions
- 1. Sue posts a message saying `I lost my Wallet`
- 2. Gary says in reply `That's terrible`
- 3. Sue replies `Don't worry, I found my wallet`
- 4. Gary replied `That's great`

<br>

- What would happen here if Sue's first post reaches servers in another area quickly
- Delay in Gary's 1st message reaching that same area
- Gary's messages appear out of order because his 2nd message reaches the servers befor Gary's 1st message
- Have to ensure that message 2 comes after message 1 (and so on and so forth)
- This is causal consistency
- `In terms of domain events, we have to be certain that each of the events are received and handled in the sequence that they occurred`

#### <a name='DesigningImplementingandUsingDomainEvents'></a>Designing, Implementing, and Using Domain Eventss

![](./images/100.png)

- Example of some domain events in our context

![](./images/101.png)

- Notice naming convention, noun + verb
    - ProductCreated
    - ReleaseScheduled

<br>

- What should be in a `ProductCreated` domain event
- The `cause` was `CreateProduct`
- In response to this command, a `Product` aggregate is created and the aggregate publishes the `ProductCreated` domain event

![](./images/102.png)

- Note the ProductCreated has the same properties as the CreateProduct command

<br>

- CommitBacklogItemToSprint example

![](./images/103.png)

- The BacklogCommited domain event is saved to an events table in the database
- The BacklogItem state is also saved to the database
- These two commits happen within the same transaction
- Either saved together or rolled back together

![](./images/104.png)

- After BacklogItemCommitted is saved, the BacklogItemCommited can then be read out of that table and published through a messaging mechanism

![](./images/105.png)

##### Domain Events are Facts

- May be caused by a non-command source
    - Time based
        - End of day/week/year
    - Example, fiscal year end, market close

#### <a name='EventSourcing'></a>Event Sourcingg

- If our `BacklogItem` aggregate was an event sourced aggregate, we would save an event for every "signifiant" thing that happens to it

![](./images/106.png)

- When each of these events occur, they are saved as an event stream to an event log in our database
- If we want to recover the state of our BacklogItem aggregate, we can read back each of those domain events and interpret those onto the state of the BacklogItem
- Step 1, CommitBacklogItemToSpring is a command that is executed on the BacklogItem aggregate
- Step 2, BacklogItem aggregate emits a BacklogItemCommited domain event
- Step 3, BackogItemCommitted domain event is saved in the order in which it occurred to a database table which is an event log
- Step 4, the BacklogItem aggregate needs to be reconsituted from its persisted state
    - We read the events from the order in which they originally occurred
        - We read BacklogItemPlanned, BacklogItemStoryDefined, BacklogItemCommitted from the stored events and reapply those to the BacklogItem aggregate which recovers its state

<br>

- Database table could look like this:

![](./images/107.png)

- StreamId is the id of the BacklogItem
- StreamVersion is the order for which the events occurred
    - 1 based sequence number
- EventType is the name of the class (name of the domain event)
- EventContent is a serialized version of the event
- Now if we reconsitute the BacklogItem aggregate, we would read the entire stream for `backlogItem123`(in this case stream version 1,2,3)

### <a name='AccelerationandManagementTools'></a>Acceleration and Management Toolss

#### <a name='Introduction-1'></a>Introductionn

- How do we get a good model under tight time constraints?

##### Modeling within Time Constraints

- Our goal is to learn about a business domain and refine a model
- Knowledge crunching takes time
- If we don't learn and model quickly, we will seem to fail even if we deliver
- We must timebox our modeling efforts
- We must not try to eliminate design

##### Facing the Time Challenging

- Event Storming
- Agile estimations

#### <a name='EventStorming'></a>Event Stormingg

- Accelerated and knowledge crunching technique
- Focus on business process
    - Not on data, database process, or model
- Model those processes as domain events
- Model the cause of those domain events (commands)
- Model the aggregates on which the commands occur
    - This in turn emit the domain events

<br>

- When performing event storming, you need the entire team
    - Domain expert(s) and developers
- Event storming has a lot to do with asking the right questions
    - Need domain experts to answer those questions

<br>

- Need stick notes
    - Orange notes for events
    - Blue for commands
    - Pale yellow for aggregates
    - May want other kind like red for caution/error scenario
    - Green which models significant UI components
    - Lilac/Purple which models policies/processes that occur in model
    - Yellow which call out personas
- Fine tipped black markers so you can write accurately
- Large modeling surface

![](./images/108.png)

##### Step 1: Model Events in Time Order

- Someone in team, take orange sticky note and write event on it that happens in our domain model
    - Verb in past tense (product created for example)
    - Doesn't need to be first event that can happen in core domain that happens
    - Kicks off process
- In time, domain events will be created in time order
- Can take a couple of hours

![](./images/109.png)

##### Step 2: Model Commands that Cause Events

![](./images/110.png)

- Now have time series of command/event pairs
- Certain commands may cause domain events in parallel or some domain events occur in parallel
    - This is okay, make note of this, and stack them using vertical spacing

##### Step 3: Model the Aggregates

- You can also call these entities or the data of the model for business people

![](./images/111.png)

- Will produce at least one aggregate that emits domain events and responds to commands
- Keep in time order, it's okay if the same aggregate receives multiple commands over time
    - That yellow sticky (the aggregate) should be on the board multiple times

##### Step 4: Identify Context Boundaries

- As you're modeling events, commands, and aggregates you're going to realize that some of these apply to core domain and some of them don't
    - Some of the commands and events belong in other bounded contexts
- Try to identify core domain, try to identify that is competitively advantageous and what is generic
- Ovals represent the contextual boundaries
- This is where modeling gets more detailed and more implementation oriented

![](./images/112.png)

- You won't capture all info here, this additional detail will come when talking about specific scenarios and defining acceptance criteria

##### Step 5: Identify Views & Other Components

- Understand certain views that are important to the user

![](./images/113.png)

- Identify certain policies where there is complexity around seeing that a certain business policy is carried out (you can represent this with a lilac/purple sticky)
    - Policy will receive events and emit commands (opposite of an aggregate)

#### <a name='ManagingDDDonanAgileProject'></a>Managing DDD on an Agile Projectt

- Reject taskboard shuffle
    - This is where design doesn't really happen

##### Agile Execution Framework

- Scrum
- Kanban
- Another agile approach

##### First Things First

- SWOT
    - Strengths - what's going well
    - Weaknesses - what needs to be improved
    - Opportunity - where do we need to focus energy
    - Obstacles - things that must be surpassed

![](./images/114.png)

###### Bottom Line: Identify Knowledge Gaps in the Model

- Find out where your model needs work
- Knowledge acquisition will lead to modeling breakthroughs

##### Modeling Spikes and Modeling Debt

###### Modeling Spikes

- Will likely having modeling spike during project inception
    - Event storming is useful here
- Will experiment with domain model using info from modeling spike
    - Write acceptance tests and flesh out the model against the acceptance tests
- Model will require ongoing refinement

###### Modeling Debt

- Dissatisfaction and late learning result in desire to refactor the model
    - Usually due to initial timeboxing
- Timeboxing modeling efforts will lead to at least some unfinished modeling
    - Timeboxing is usually the sprint or the iteration
- These naturally lead to incurring modeling debt
- Modeling debt must be paid later
    - Don't ignore this, call it out, and address it in later sprint/iteration

##### Identifying Tasks and Estimating Effort

- Find necessary tasks to work on
- Level of effort for each task
- Event storming helps us figure this out

![](./images/115.png)

- Can create table for estimations
    - This can be extended to views, domain services, etc
    - It can be used for any type of component

![](./images/116.png)

- Take each of estimation units and estimate LOE easy/moderate/complexity
- As you estimate each of the aggregates/processes/views/services/events/commands, you can combine these to come up with an estimate on how long the effort will take
- Things will need to be tuned as we go, the time estimations may change
- These estimations can include unit tests

## <a name='DomainServicesvsApplicationServices'></a>Domain Services vs Application Servicess

- https://enterprisecraftsmanship.com/posts/domain-vs-application-services/

### <a name='DomainServicesvsApplicationServices-1'></a>Domain Services vs Application Servicess

- **Domain Services hold domain logic whereas application services do not**
- Domain services participate in the business decision making process just like entities and value objects do
- Application services orchestrate those decisions the same way they orchestrate decisions made by entities and value objects

<br>

- Example

```
public void WithdrawMoney(decimal amount)
{
    _atm.DispenseMoney(amount);
    decimal amountWithCommission = _atm.CalculateAmountWithCommission(amount);
 
    _paymentGateway.ChargePayment(amountWithCommission);
    _repository.Save(_atm);
}
```

- The `WithdrawMoney` method is part of an application service and comprises a customer-facing API
- Does this application look okay or should some of it get extracted into a domain service?
- There are no branches that signal the code making any decisions
- It just asks the domain entity to do two separate things

<br>

- Similar example

```
public void WithdrawMoney(decimal amount)
{
    if (!_atm.CanDispenseMoney(amount))
        return ;
 
    _atm.DispenseMoney(amount);
    decimal amountWithCommission = _atm.CalculateAmountWithCommission(amount);
 
    _paymentGateway.ChargePayment(amountWithCommission);
    _repository.Save(_atm);
}
```

- The cyclomatic complexity in this example is higher than one now because have an `if` statement
- Does this mean the application service now contains domain knowledge?
- The actual decision-making process still residesin Atm
- The entity alone decides whether it can dispense money
- As long as the `DispenseMoney` methodin Atm has a precondition stating that `CanDispenseMoney` must hold true prior to dispensing cash, all invariants stay protected

```
public void DispenseMoney(decimal amount)
{
    if (!CanDispenseMoney(amount))
        throw new InvalidOperationException();
 
    /* ... */
}
```

- So even if the application service ignores the decision made by `CanDispenseMoney`, the Atm entity cannot enter an inconsistent state

### <a name='Whentoextracttoadomainservice'></a>When to extract to a domain service??

- In above example, the code doesn't make any business decisions
- **Note that the domain model is isolated**
    - The Atm entity doesn't save itself to the database and it doesn't directly charge payments through the payment gateway
- Nice separation of concerns
    - Business logic is attributed to domain model
    - Interactions with the external world happen through domain service
- You can notice a pattern in most codebases that adhere to this guideline
    - Prepare all info needed for business operation
        - Loading entities from database
        - Retrieve any required data from other external sources
    - Execute the operation
        - Operation consists of one or more business decisions made by the domain model
        - Those decisions result in either changing the model's state, generating some artifacts, or both
    - Apply the results of the operation to the outside world
- Only the 1st and 3rd steps involve work with external dependencies
- 2nd step is done using the data retrieved in the 1st operation
    - the arguments it accepts and output it generates consists of entities, value objects, and primitive types *only*

<br>

- In simple CRUD apps, there's no 2nd step because there are no decisions to make
    - All operations can be performed solely by application services

<br>

- Another example:

```
public void WithdrawMoney(decimal amount)
{
    if (!_atm.CanDispenseMoney(amount))
        return ;
 
    decimal amountWithCommission = _atm.CalculateAmountWithCommission(amount);
    Result result = _paymentGateway.ChargePayment(amountWithCommission);
 
    if (result.IsFailure)
        return ;
 
    _atm.DispenseMoney(amount);
    _repository.Save(_atm);
}
```

- In this cause our 2nd `if` does represent domain logic
    - It decides whether we will be dispensing cash to the user
- Unlike in the first conditional operator (remember, DispenseMoney would throw an exception if we didn't have this first `if`, so the domain logic is still residing in the ATM entity), it is the application service making this decision
    - It is possible to take cash from the ATM even if the payment has failed prior to it
    - **The domain entity doesn't hold this invariant for us**
    - It's impossible to introduce such an invariant without violating the entity's isolation because in order to check this precondition, it will have to call the 3rd party service

<br>

- What do we do in this situation?
- This is where domain services can be helpful
- They're helpful where business decisions require additional information from the external world and which cannot be made by entities and value objects because of that

```
public void WithdrawMoney(decimal amount)
{
    Atm atm = _repository.Get();
    _atmService.WithdrawMoney(atm, amount);
    _repository.Save(_atm);
}

public sealed class AtmService // Domain service
{
    public void WithdrawMoney(Atm atm, decimal amount)
    {
        if (!atm.CanDispenseMoney(amount))
            return ;
 
        decimal amountWithCommission = atm.CalculateAmountWithCommission(amount);
        Result result = _paymentGateway.ChargePayment(amountWithCommission);
 
        if (result.IsFailure)
            return;
 
        atm.DispenseMoney(amount);
    }
}
```

- The domain service here is a middle ground between impurity and the amount of complexity/business logic held
- We can't make this service completely isolated because it has to work with th epayment gateway in order to do its work
- We don't attribute too much domain logic to it, only the knowledge regarding how to exchange cash for credit
We put just enough logic into the domain service to work properly
    - It doesn't know about any repositories, for example, because that's not required for this business decision

<br>

- Advantages:
    - All domain logic kept within domain boundaries
    - Code in domain service is more testable than in the application service
    - Fewer external dependencies

<br>

- It's mostly fine to keep a little bit of logic that doesn't fit into an entity into an application service
    - Don't always need to introduce a separate domain service
- If the application service becomes too complex or rules are being duplicated, it's probably time for a domain service

## Event Storming

- https://github.com/ddd-crew/eventstorming-glossary-cheat-sheet

## Event Storming Video

- https://learning.oreilly.com/videos/event-storming
- Directly map real domain into application
- If our application is structured just like the real world domain, it's easy to know where to go when you need to make a change
    - Scope of change in application will be same as scope of change in real world domain

### Bounded Contexts

- Model business structure or flow
    - **A miroservice being a bounded context is incorrect** (according to this video anyways)
        - A microservice is really an entity
- Within different boundaries, we have lots of objects (entities) that do work
- Entities within contexts talk to each other
- Entities should not directly talk to entities in other contexts (this would lead to a big ball of mud)
    - You do this by delegating one entity to communicate with other context (aggregate root)

![](./images/117.png)

- Using something like a `Product` in any context is fundamentally against DDD

### Orchestration

![](./images/118.png)

- If `Shopping-Cart Service` can only talk to `Billing Service` but can't talk to `Warehouse Service`, what happens?
    - You've billed your customer but you can't ship it b/c you can't talk to `Warehouse Service`
- `Shopping-Cart Service` is tightly coupled to `Warehouse Service` and `Email Service`

<br>

#### Solution is Choreography

- Want something like pubsub
- We talk via events, and those system get the events and react to the events

![](./images/119.png)

- When DDD originally came out, microservices didn't exist, so Eric Evans suggest this same time of async communication (domain events) within your monolith

### Entities (Subcontexts)

- How do we organize and recognize events and entities that participate in a system
    - CRC cards
        - Good way to keep entities organized

![](./images/120.png)

- SRP - all things that a class does are all focused on the same objective

![](./images/121.png)

### User Stories

- Need to happen before event storming
- A short narrative
    - Has beginning, end, charaters
    - A couple of sentences
- We want to delay doing things until we can't delay anymore
    - World changes so quickly that if we make decisions to early, that odds of those being the wrong decisions is high
- Describes a user performing a domain process
    - Describes customer's work, the process they're doing to get something done
    - Should have valuable outcome for that user
    - **Stories describe your user's work, not yours**
        - Fixing the database is not a story
            - In order to do something, the databased needs to be fixed is a story
- **It describes a full vertical slice through entire system**
- A placeholder for a conversatoin that happens just before (and during) development
    - Do not "flush out" the details until you're ready to implement
    - If you have to write it down to remember, you're doing it too early
    - You do this constantly as you're working
        - Doesn't only happen at the beginning of a 2 week iteration
        - Product Owner has to be able to respond within a couple of minutes for this to work
- **Delay until the last responsible moment**

#### Invest Criteria

- More information: https://agileforall.com/new-to-agile-invest-in-good-user-stories/
    - Don't know when a story is done - Ask *How will I know I've done that?* - https://agileforall.com/when-in-doubt-ask-how-will-i-know-ive-done-that-2/

- Used when defining stories

<br>

- I: Independent
    - If you have a set of stories, you should be able to implement them in any order
- N: Negotiable
    - A story is an invitation to conversation
    - Story captures the essence of what is desired
- V: Valuable to end user
- E: Estimable
    - Estimable being worthy of great respect
    - Or `end-to-end` - story should describe entire domain process from beginning to end
    - Essential - essential to business/end user
- S: Small
    - Something you can do in a day or two
- T: Testable
    - Automated acceptance tests (BDD)

<br>

- Keep users in mind to get stories right
    - Checkout page of website
        - User wants to leave site as quickly as possible
            - Make this as easy as possible - like Amazon with 1 click buy

#### Epic

- A broad set of capabilities that the business is willing to bet will provide sufficient value that's worth doing a bit of experimental development
- An epic is NOT a bag of stories
- Epics are planning tools for the business
    - Set strategic direction to create value


#### Story Format

![](./images/122.png)

- Bad user story example below

![](./images/123.png)

- With a big story, think about how you can break it down
    - And then how can you break it down ever further, etc
- Want stories to be as small as possible
    - No more than a couple days to implement
- Well sized story has a single acceptance tests

<br>

- Do not write stories for each layer that needs to be changed

<br>

- Don't split stories horizontally across layers

![](./images/124.png)

<br>

- **Best way to split stories is to isolate workflows**


#### Activity Diagram

![](./images/125.png)

- You want to take this diagram, that shows many different workflows, and take specific workflows and make stories from those

![](./images/126.png)

#### More info on how to split a user story

- https://3p72t53zzqr23puj171gfblg-wpengine.netdna-ssl.com/wp-content/uploads/2020/12/Story-Splitting-Flowchart.pdf

### Event Storming

- By Alberto Brandolini
- Way to DDD
- "Business people and developers must work together throughout the project"
- Use stories as a guide to what to model

<br>

- **Event**
    - Something thaat happened in the business that your customers (domain experts) care about
        - *Order submitted*
        - *Payment received*
        - *Nightly reconciliation completed*
    - Lay out events in a timeline

![](./images/127.png)

- Can also use electronically
- Blue notes are things done when event is received
- Orange notes are events
- Red notes are questions
    - Not finished until red is gone
- Policies are also listed
    - *I will sent this event because of this rule*

![](./images/128.png)

<br>

![](./images/129.png)

- `Warehouse` receives the `order placed` event and, as a result, the `items are picked`
- Diagram can expand

![](./images/130.png)

- The *policy* here gives rules that we have to follow to send an event

![](./images/131.png)

- As understanding grows you can get above diagram
    - `Shipping` is the context in which `warehouse` exists
    - `Items` and `Destination` are in payload of the `Order placed` event
    - Getting more implementationy

<br>

- Once you have all entities in `Shipping` context, you can group them together and then you have the `Shipping` bounded context
- **This is the entire architecture, and the entire thing is event driven**

#### Live Event Storming Example

- Events in a book store

![](./images/132.png)

- What events stem from that first event?

![](./images/133.png)

- Obvious events come first
- Then you discover events that you hadn't thought about initially

![](./images/134.png)

- Now we can work backwards from `order accepted`

![](./images/135.png)
    - As we look at these events, are there ones that can be grouped together and still have value
    - You can put things into a cart without buying anything, so that's a valuable work stream

<br>

- Now we can move onto activities that happen as a result of events

![](./images/136.png)

- Starting to this about activities will also flesh out new activites
    - In the above example, shouldn't a `create label...` activity result in a `label created` event?

![](./images/137.png)

- Activities can result in more than one event
    - In our case, when you `create label and notify UPS` (there's an "and" here b/c that's how it works with UPS)

![](./images/138.png)
    - Notice that `label created` and `tracking info received` are vertically aligned
        - This means that they are both created as a result of the `create label and notify UPS` activity

<br>

- Now we can move on to aggregates/entities

![](./images/139.png)

- **The shipping clerk (in warehouse context) creates and notifies UPS when order shipped event is received**

![](./images/140.png)

- Note that *customer liason* is in the *warehouse* context, but that may change (which is okay)

![](./images/141.png)

- Copy all yellow cards
    - Make CRC cards (infinity map) that identify entity and context and responsibilites

<br>

- Pick one story, do event storming as part of iteration (shouldn't take more than 1/2 hour for single story) and then code it
- **Event storming** is done on a per story basis
- Sometimes it's helper to do a bigger event storming session to figure out where the boundaries even are
- If you're making microservices out of this:
    - salesperson is a microservice
    - shipping clerk is a microservice
    - customer liason is a microservice
    - comptroller is a microservice
    - warehouse is a microservice
        - This microservice serves an an entry point for working with other entities in the warehouse context (shipping clerk, customer liason, comptroller)
    
<br>

## Library (example) DDD application

- https://github.com/ddd-by-examples/library