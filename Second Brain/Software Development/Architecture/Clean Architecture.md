![[Pasted image 20231012190734.png]]

# External Interfaces

- Use whatever framework is most appropriate (they are going to be isolated here anyway)
## Frameworks and Drivers

Software areas that reside inside this layer are

- User Interface
- Database
- External Interfaces (eg: Native platform API)
- Web (eg: Network Request)
- Devices (eg: Printers and Scanners)

# Interfaces / Adapters

- Retrieve and store data from and to a number of sources (database, network devices, file system, 3rd parties, and so on.)
- Define interfaces for the data that they need in order to apply some logic. One or more data providers will implement the interface, but the use case doesn’t know where the data is coming from
- Implement the interfaces defined by the use case
- There are ways to interact with the application, and typically involve a delivery mechanism (for example, REST APIs, scheduled jobs, GUI, other systems)
- Trigger a use case and convert the result to the appropriate format for the delivery mechanism
- the controller for a MVC

This layer holds

- `Presenters` (UI Logic, States)
- `Controllers` (UI Logic, States)(Interface that holds methods needed by the application which is implemented by Web, Devices or External Interfaces)
- `Gateways` (Interface that holds every CRUD operation performed by the application, implemented by DB)

# Use Cases

- Represent your business actions: it’s what you can do with the application. Expect one use case for each business action
- Pure business logic, plain code (except maybe some utils libraries)
- The use case doesn’t know who triggered it and how the results are going to be presented (for example, could be on a web page, or — returned as JSON, or simply logged, and so on.)
- Throws business exceptions
## Application Business Rules

Rules which are not Core-business-rules but essential for this particular application come under this. This layer holds `Use Cases`**.** As the name suggests, it should provide every use case of the application. i.e. it holds each and every functionality provided by the application.

Also, this is the layer that determines which `Controller` / `Gateway` to be called for the particular use case. Sometimes we need controllers from different modules.

This is where different modules are coordinated. For instance, we want to apply a discount for the user who purchased for x amount within a month.

Here we need to get the amount the user has spent on this month from the `purchase module` and then with the result we need to apply the discount for the user in the `checkout module`**.** Here `applyDiscountUseCase` calls the purchase module’s controller for the data and then applies the discount in the checkout module.

# Entities

- Represent your domain object
- Apply only logic that is applicable in general to the whole entity (e.g., validating the format of a hostname)
- Plain objects: no frameworks, no annotations
## Enterprise Business Rules

This is the layer that holds core-business rules or domain-specific business rules. Also, this layer is the least prone to change.

Change in any outer layer doesn’t affect this layer. Since `Business Rules` won’t change often, the change in this layer is very rare. This layer holds Entities.

An entity can either be a core data structure necessary for the business rules or an object with methods that hold business logic in it.

For example: calculating `Interest` module in the banking application is the core business logic that should be inside this layer.