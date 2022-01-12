# Arquitectura Evolutiva

##

##

[#quantumtalent/practica-dev](bear://x-callback-url/open-tag?name=quantumtalent/practica-dev)

**Enterprise architecture must enable:**

* Maintainability
* Flexibility
* Agility

**Definition of agility as**

* the ability of an organization to respond effectively and in good time to changes in the business environment, is customer requirements or in enterprise strategy.

**Properties of Agility and Adaptable**

* Scalability
  * Ability to deal with changing workloads by utilizing available resources and effectively maintaining a service level.
* Modularity
  * Components of the architecture are versioned, replicable a have well defined interfaces
* Compostability
  * Creating a recursive and uniform architecture where new components and capabilities add to the overall platform in a seamless way.
* Governance
  * Building managed, monitored, resilient systems and ensuring that organizational policies are enforced

**Architecture Abstractions**

* User
  * something that interacts with the system
    * Human
    * External Customer
    * Internal Employees
    * Partners

**Component**

* An atomic unit in architecture
* Represent a process or business logic running in a container, serve-less environment or an existing runtime.
* Can be categorized into many subtypes based on the functional capabilities (Domain Driven Design)
* Designed based on a specific scope.
* Can be implemented like a service, function, micro-service, reuse of legacy.

**Component Types**

* Legacy and data services
  * Databases
  * Existing systems
  * Repositories
  * Storage
  * Business Processes
* Micro-services and server-less
  * Core Business Logic
  * Aggregation and service composition
  * Transformation
* Gateways
  * Exposed APIs
* External endpoints
  * Cloud Systems
  * SaaS
* Front end Clients
  * Mobile
  * Reactive
  * Api consumers
* Governance and utilities
  * Automation Tools
  * Monitoring
  * Observability
  * Logs

**Cells**

* A collection of components, grouped from design and implementation into deployment.
* Independently deployable, manageable an observable
* Components inside the cell can communicate with each other using supported transport for intra-cell communication.
* External communication happen through the edge gateway, providing APIs with standard protocols.
* cell can have 1:n components grouped
* Components are reusable and can instantiate in multiple cells.
* Each cell have its own documentation
* Every component of the cell should be versioned, so the cell should have a name and a version identifier.
* Each component into the cell have its own storage

**Cell Categories**

* Internal Cells
  * Legacy and monolith cells
  * Micro-services
  * End-User application (front end)
    * Channels
      * APIs
      * Events (hooks)
      * Streams
* External Cells
  * Endpoints exposed by partners
  * Service provider ecosystem of the organization

**Governance**

* The gateway is the control point of the architecture
* Gateway becomes the only access end point for the cell
* Gateway acts as
  * a policy enforcement point,
  * observability touch point
  * enabler for governance frameworks
* Gateway helps to comply with domain-specific, technology and business standards
* Gateway pattern mandates the entire internal and external communication flow through a set of defined gateway clusters
  * Allows to enforce policies and capture information for observations.

**Security**

* Each cell must has its own security rules, policies and approaches
  * i.e Headers tokens
* Pattern 1:
  * Security Token Service (STS) inside the cell
    * containing security metadata to authorize and authenticate the incoming requests.
    * STS is part of the local control plane, and store required policies and acts as a policy decision point. (PDP)
* Pattern 2
  * Identity Provider Point (IDP)
    * Conventional control plane
    * Outside the cells

**Lifecycle**

* Each cell can have its own lifecycles stages based on the functionality
  * Different pipelines for each cell.

**Agility**

* Level 1: Components inside each cell can iterate individually
* Level 2: each cell iterate independently
* level 3: Architecture iterate as a whole

**How to implementing?**

* Each cell is a K8s metaphor
* Services inside Cell share resources and communicates directly
* Each cell has its own GateWay
* Each cell has its own control layer
