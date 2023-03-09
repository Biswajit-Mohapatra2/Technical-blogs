---
title: "Microservices Interview
Questions"
datePublished: Thu Jan 19 2023 08:33:06 GMT+0000 (Coordinated Universal Time)
cuid: cld2u5cpo000108k1dny6bs3p
slug: microservices-interview-questions
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1674110861051/38261734-714b-449a-a1dc-a4f3d5b40b5e.jpeg
tags: microservices, hashnode, blogswithcc, kunalkushwaha, wemakedevs

---

---

## Microservices Interview Questions for Freshers

### 1\. What do you mean by Microservice?

Microservices, also known as Microservices Architecture, is an SDLC approach in which large applications are built as a collection of small functional modules. It is one of the most widely adopted architectural concepts within so ware development. In addition to helping in easy maintenance, this architecture also makes development faster. Additionally, microservices are also a big asset for the latest methods of software development such as DevOps and Agile. Furthermore, it helps deliver large, complex applications promptly, frequently, and reliably.

Applications are modeled as collections of services, which are:

* Maintainable and testable
    
* Loosely coupled
    
* Independently deployable
    
* Designed or organized around business capabilities
    
* Managed by a small team
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1674111897333/1aa20ac4-4d28-4f57-8fcf-8bf063d4ffcd.png align="center")

### 2\. Write the main features of Microservices.

Some of the main features of Microservices include:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1674112036184/91aea1ee-daf2-4f09-aa0c-968a614368e7.png align="center")

* **Decoupling:** Within a system, services are largely decoupled. The application as a whole can therefore be easily constructed, altered, and scalable
    
* **Componentization:** Microservices are viewed as independent components that can easily be exchanged or upgraded
    
* **Business Capabilities:** Microservices are relatively simple and only focus on one service
    
* **Team autonomy**: Each developer works independently of each other, allowing for a faster project timeline
    
* **Continuous Delivery:** Enables frequent software releases through systematic
    
    automation of software development, testing, and approval.
    
* **Responsibility:** Microservices are not focused on applications as projects. Rather, they see applications as products they are responsible for.
    
* **Decentralized Governance**: Choosing the right tool according to the job is the goal. Developers can choose the best tools to solve their problems.
    
* **Agility:** Microservices facilitate agile development. It is possible to create new features quickly and discard them again at any time.
    

### 3\. Write the main components of Microservices.

Some of the main components of microservices include:

* Containers, Clustering, and Orchestration
    
* Iac\[Infrastructure as Code Conception\]
    
* Cloud Infrastructure
    
* API Gateway
    
* Enterprise Service Bus
    
* Service Delivery
    

### 4\. What are the benefits and drawbacks of Microservices?

**Benefits:-**

* Self-contained, and independent deployment module.
    
* Independently managed services.
    
* To improve performance, the demand service can be deployed on multiple servers.
    
* It is easier to test and has fewer dependencies.
    
* A greater degree of scalability and agility.
    
* Simplicity in debugging & maintenance.
    
* Better communication between developers and business users.
    
* Development teams of a smaller size.
    

**Drawbacks:-**

* Due to the complexity of the architecture, testing and monitoring are more difficult.
    
* Lacks the proper corporate culture for it to work.
    
* Pre-planning is essential.
    
* Complex development. Requires a cultural shift.
    
* Expensive compared to monoliths.
    
* Security implications.
    
* Maintaining the network is more difficult.
    

### 5\. Name three common tools mostly used for microservices.

* Wiremock
    
* Docker
    
* Hystrix
    

### 6\. Explain the working of Microservice Architecture.

Microservice architectures consist of the following components:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1674112947896/6105fe66-512b-48a6-b946-cd6a43fc2e55.png align="center")

* **Clients:** Different users send requests from various devices.
    
* **Identity Provider:** Validate a user's or client's identity and issue security tokens.
    
* **API Gateway**: Handles the requests from clients.
    
* **Static Content:** Contains all of the system's content.
    
* **Management:** Services are balanced on nodes and failures are identified.
    
* **Service Discovery:** A guide to discovering the routes of communication between microservices.
    
* **Content Delivery Network:** Includes distributed network of proxy servers and their data centers.
    
* **Remote Service:** Provides remote access to data or information that resides on networked computers and devices.
    

### 7\. Write the difference between Monolithic, SOA and Microservices Architecture.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1674113245786/eb2baf02-1803-4a1f-b32f-e47a41c52bd5.png align="center")

* **Monolithic Architecture:** It is "like a big container" where all the software components of an application are bundled together tightly. It is usually built as one large system and is one code base.
    
* **SOA (Service-Oriented Architecture):** It is a group of services interacting or communicating with each other. Depending on the nature of the communication, it can be a simple data exchange or it could involve several services coordinating some activity.
    
* **Microservice Architecture:** It involves structuring an application in the form of a cluster of small, autonomous services modeled around a business domain. The functional modules can be deployed independently, are scalable, are aimed at achieving specific business goals, and communicate with each other over standard protocols.
    

### 8\. Explain spring cloud and spring boot.

**Spring Cloud:** In Microservices, the Spring cloud is a system that integrates with external systems. This is a short-lived framework designed to build applications quickly. It contributes significantly to microservice architecture due to its association with finite amounts of data processing.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1674113527401/87d477d8-815a-4d04-8af5-5703d04ff0dc.png align="center")

**Spring Boot:** Spring Boot is an open-sourced, Java-based framework that provides its developers with a platform on which they can create stand-alone, production-grade Spring applications. In addition to reducing development time and increasing productivity, it is easily understood.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1674113671711/fab52fe5-5820-42e8-b98b-0bad42690c79.png align="center")

### 9\. What is the role of the actuator in spring boot?

A spring boot actuator is a project that provides restful web services to access the current state of an application that is running in production. In addition, you can monitor and manage application usage in a production environment without having to code or configure any of the applications.

### 10\. Explain how you can override the default properties of Spring boot projects.

By specifying properties in the [application.properties](http://application.properties) file, it is possible to override the default properties of a spring boot project.

**Example:**

In Spring MVC applications, you need to specify a suffix and prefix. You can do this by adding the properties listed below in the [application.properties](http://application.properties) file.

* For suffix – spring.mvc.view.suffix: .jsp
    
* For prefix – spring.mvc.view.prefix: /WEB-INF/
    

### 11\. What issues are generally solved by spring clouds?

* **Complicated issues caused by distributed systems:** This includes network issues, latency problems, bandwidth problems, and security issues.
    
* **Service Discovery issues:** Service discovery allows processes and services to communicate and locate each other within a cluster.
    
* **Redundancy issues**: Distributed systems can often have redundancy issues.
    
* **Load balancing issues:** Optimize the distribution of workloads among multiple computing resources, including computer clusters, central processing units, and network links.
    
* **Reduces performance issues:** Reduces performance issues caused by various operational overheads.
    

### 12\. What do you mean by Cohesion and Coupling?

**Coupling:** It is defined as a relationship between software modules A and B, and how much one module depends on or interacts with another one. Couplings fall into three major categories. Modules can be highly coupled (highly dependent), loosely coupled, and uncoupled from each other. The best kind of coupling is loose coupling, which is achieved through interfaces.

**Cohesion:** It is defined as a relationship between two or more parts/elements of a module that serves the same purpose. Generally, a module with high cohesion can perform a specific function efficiently without needing communication with any other modules. High cohesion enhances the functionality of the module.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1674114318875/20a79452-7bfe-4292-a36b-1079e61422b8.png align="center")

### 13\. What do you mean by Bounded Context?

A Bounded Context is a central pattern in DDD (Domain-Driven Design), which deals with collaboration across large models and teams. DDD breaks large models down into multiple contexts to make them more manageable. Additionally, it explains their relationship explicitly. The concept promotes an object-oriented approach to developing services bound to a data model and is also responsible for ensuring the integrity and mutability of said data model.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1674114439562/923c2d86-c107-47f9-a27e-9de86e08869d.png align="center")

### 14\. What are the challenges that one has to face while using Microservices?

The challenges that one has to face while using microservices can be both **functional and technical.**

**Functional Challenges**:

* Require heavy infrastructure setup.
    
* Need Heavy investment.
    
* Require excessive planning to handle or manage operations overhead.
    

**Technical Challenges:**

* Microservices are always interdependent. Therefore, they must communicate with each other.
    
* It is a heavily involved model because it is a distributed system.
    
* You need to be prepared for operations overhead if you are using Microservice architecture.
    
* To support heterogeneously distributed microservices, you need skilled professionals.
    
* It is difficult to automate because of the number of smaller components. For that reason, each component must be built, deployed, and monitored separately.
    
* It is difficult to manage configurations across different environments for all components.
    
* Challenges associated with deployment, debugging, and testing.
    

### 15\. Explain PACT in microservices.

PACT is defined as an open-source tool that allows service providers and consumers to test interactions in isolation against contracts that have been made to increase the reliability of microservice integration. It also offers support for numerous languages, such as Ruby, Java, Scala, .NET, JavaScript, and Swift/Objective-C.

### 16\. Explain how independent microservices communicate with each other.

Communication between microservices can take place through:

* HTTP/REST with JSON or binary protocol for request-response
    
* Websockets for streaming.
    
* A broker or server program that uses advanced routing algorithms.
    

RabbitMQ, Nats, Kafka, etc., can be used as message brokers, each is built to handle a particular message semantic. You can also use Backend as a Service like Space Cloud to automate your entire backend.

### 17\. What do you mean by client certificates?

The client certificate is a type of digital certificate that generally allows client systems to authenticate their requests to remote servers. In many mutual authentication designs, it plays a key role in providing strong assurance of the requestor's identity.

### 18\. Explain CDC.

As the name implies, CDC (Consumer-Driven Contract) ensures service communication compatibility by establishing an agreement between consumers and service providers regarding the format of the data exchanged between them. An agreement like this is called a contract. It is a pattern used to develop Microservices so that they can be efficiently used by external systems.

### 19\. Name some famous companies that use Microservice architecture.

Microservices architecture has replaced monolithic architecture for most large-scale websites like:

* Twitter
    
* Netflix
    
* Amazon, etc.
    

---

## Microservices Interview Questions for Experienced

### 1\. Explain continuous monitoring.

Continuous monitoring involves identifying compliance and risk issues in a company's financial and operational environment. It consists of people, processes, and working systems that support efficient and effective operations.

### 2\. What do you mean by Domain-driven design?

DDD (Domain-Driven-Design) is an architectural style that is based on Object-Oriented Analysis Design approaches and principles. In this approach, the business domain is modeled carefully in software, without regard to how the system works. By interconnecting related components of the software system into a continuously evolving system, it facilitates the development of complex systems. There are three fundamental principles:

* Concentrate on the core domain and domain logic.
    
* Analyze domain models to find complex designs.
    
* Engage in regular collaboration with domain experts to improve the application model and address emerging domain issues.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1674115470987/dd2d7754-d214-4faf-9665-134b34bc522a.png align="center")

### 3\. Explain OAuth.

Generally speaking, OAuth (Open Authorization Protocol) enables users to authenticate themselves with third-party service providers. With this protocol, you can access client applications on HTTP for third-party providers such as GitHub, Facebook, etc. Using it, you can also share resources on one site with another site without requiring their credentials.

### 4\. What do you mean by Distributed Transaction?

Distributed transactions are an outdated approach in today's microservice architecture that leaves the developer with severe scalability issues. Transactions are distributed to several services that are called to complete the transaction in sequence. With so many moving parts, it is very complex and prone to failure.

### 5\. Explain Idempotence and its usage.

The term **'idempotence'** refers to the repeated performance of a task despite the same outcome. In other words, it is a situation in which a task is performed repeatedly with the result remaining the same.

**Usage**: When the remote service or data source receives instructions more than once, Idempotence ensures that it will process each request once.

### 6\. What do you mean by end-to-end microservices testing?

Usually, end-to-end (E2E) microservice testing is an uncoordinated, high-cost technique that is used to ensure that all components work together for a complete user journey. Usually, it is done through the user interface, mimicking how it appears to the user. It also ensures all processes in the workflow are working properly.

### 7\. Explain the way to implement service discovery in a microservices architecture.

There are many ways to set up service discovery, but Netflix's Eureka is the most efficient. This is a hassle-free procedure that doesn't add much weight to the application. It also supports a wide range of web applications. Several annotations are provided by Spring Cloud to make its use as simple as possible and to hide complex concepts.

### 8\. What are Reactive Extensions in Microservices?

A reactive extension, also known as Rx, is a design approach that calls multiple services and then generates a single response by combining the results. The calls can either be blocking or not blocking, synchronous or asynchronous. A popular tool in distributed systems, Rx works exactly opposite to legacy flows.

### 9\. Explain the type of tests mostly used in Microservices.

As multiple microservices are working together, microservice testing becomes quite complex when working with microservices. Consequently, tests are categorized according to their level:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1674116000547/5d295394-b812-487f-9e20-ec52a86d25dd.png align="center")

* **Botton-level tests:** The bottom-level tests are those that deal with technology, such as unit tests and performance tests. This is a completely automated process.
    
* **Middle-level tests:** In the middle, we have exploratory tests such as stress tests and usability tests.
    
* **Top-level tests:** In the top-level testing, we have a limited number of acceptance tests. The acceptance tests help stakeholders understand and verify the so ware
    
    features.
    

### 10\. Explain Container in Microservices.

**Containers** are useful technologies for allocating and sharing resources. It is considered the most effective and easiest method for managing microservice-based applications to develop and deploy them individually. Using Docker, you may also encapsulate a microservice along with its dependencies in a container image, which can then be used to roll on-demand instances of the microservice without any additional work.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1674116212088/b799a08e-4287-4022-93a6-91dd85f64939.png align="center")

### 11\. What is the main role of docker in microservices?

[Docker](https://aws.amazon.com/docker/) generally provides a container environment, in which any application can be hosted. This is accomplished by tightly packaging both the application and the dependencies required to support it. These packaged products are referred to as Containers, and since Docker is used to doing that, they are called Docker containers. Docker, in essence, allows you to containerize your microservices and manage these microservices more easily.

---

# Conclusion:

Microservices architecture is a method of developing a large-scale application as a collection of small autonomous services developed for a business domain. Since its debut in 2011, microservices have become a popular technology, especially among organizations building forward-thinking applications. This list of Microservices interview questions was carefully constructed to assist the development community in their interviews.

Hope these Microservices Architect Interview Questions would be helpful for your interview.