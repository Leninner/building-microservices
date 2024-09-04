# How to Model Microservices

## What makes a good microservice boundary?

Microservices are another form of modular decomposition. We need three things that are vital to the success of microservices:

### 1. Information Hiding

Describes a desire to `hide as many details as possible` behind a microservice. You have benefits from this approach, such as:

- **Improved development time**: You can develop different microservices in parallel reducing the impact of adding more developers to a project.
- **Comprehensibility**: You can look at a microservice in isolation and understood in isolation. Using `ubiquitous language`, you can understand what the microservice does.
- **Flexibility**: You can change a microservice without affecting other microservices.

Keeping a module's public interface small and well-defined is a good practice. It allows you to change the implementation without affecting the consumers of the module or if you change it, the change might be done in a safe way.

### 2. Cohesion

Means in a succinct definition: The code that changes together, stays together. It is a measure of how closely related and focused the responsibilities of a module are. A module with high cohesion is more focused and easier to understand.

You would like the functionality grouped in such way that we can make changes in as few places as possible. This is vital because it reduces the risk of making a mistake when changing the code and improve the isolation deployment of the module.

In a microservice arquitecture, you are aiming for strong cohesion.

### 3. Coupling

When services are loosely coupled, a change to one service should not require a change to another.

You should aim to avoid having multiple and different types of calls from one service to another. Moreover, you should avoid having chatty communication between services. This is because the more services communicate, the more coupling you have.

## The Interplay of Coupling and Cohesion
