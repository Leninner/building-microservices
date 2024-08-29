# Chapter 1 - What are Microservices?

- Are independently releasable services that are modeled around a business domain.
- Each service has its own database.
- A change inside a microservice should not affect upstream or downstream services.

## Key concepts

* **Independent Deployability**

  - Each service can be deployed independently of other services.
  - This allows for faster deployment cycles.
  - We have to ensure a "loosely coupled" architecture. Change one service without the need to change others.

* **Modeled around a Business Domain**
  
  - Each service is modeled around a business domain.
  - DDD is a good approach to model microservices.
  - We must to ensure high cohesion of business functionality over technical functionality.

![traditional 3-tiered architecture](1-2.png)

* **Owning their Own State**
  
  - Using a separate database for each service is a key characteristic of microservices.
  - This allows for each service to publish the public and non-very-volatile data to other services and hide the private data that could change more frequently than public data.
  - Is similar to Encapsulation in OOP.

* **Size**

  - A microservice should be as big as your head. If you can't hold the whole service in your head, it's too big.
  - Is a subjective concept, but it's a good rule of thumb. A person who have worked on a service with 100K lines of code could thing that a service with 10K lines of code is a microservice. A person who have worked on a service with 10K lines of code could thing that a service with 1K lines of code is a microservice. And so on.
  - Focus on two main things: How many microservices can you handle? How do you define the boundaries of a microservice?

* **Flexibility**

  - Microservices allow for flexibility in technology stack.
  - Each service can be written in a different language or use different technologies.

## Alignment of Architecture and Organization**

- Its better to align the architecture with the organization.
- Instead of having specialized teams of backend, frontend, QA for each layer, we can have cross-functional teams that own a microservice end-to-end.

![before](1-3.png)

![after](1-4.png)

## The Monolith

Unit of deployment is the entire application. It's a single codebase that is deployed all at once.

### Single-Process Monolith

All the code is running or deployed in a single process.

![single-process monolith](1-6.png)

### Modular Monolith

The single-process monolith is divided into modules, but all the modules are deployed together.

We can have modular monoliths with a single DB with a coupling between modules.

![single db](1-7.png)

Or we can have modular monoliths with multiple DBs to avoid coupling between modules.

![multiple db](1-8.png)

### Distributed Monolith

The monolith is divided into services, but all the services are deployed together.

A service failure can bring down the **entire** application.

### Monoliths and Delivery Contention

Delivery Contention is when two teams are trying to deploy at the same time and they have to wait for each other.

This is a common problem in monoliths, also known as "merge hell".

### Advantages of Monoliths

- Easier to deploy, scale, and test than microservices.
- Reuse of code is easier.

## Enabling Technology

A well choosen technology stack is essential for microservices.

### Log Aggregation and Distributed Tracing

A log aggregation system must be a prerequisite for microservices. Will help us to debug and monitor the entire microservices architecture in a single place.

Different services can help us:

- **Grafana Loki**
- **Humio**

Distributed tracing is also important. It allows us to trace a request through multiple services.

- **Jaeger**
- **Lghtstep**
- **Honeycomb**

![tracing](1-9.png)

### Containers and Kubernetes