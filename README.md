# Design Guide

This is a DRAFT design guide outlining opinions on software development best practices, standards, design patterns, frameworks, and the setup of development team structure & formation. The focus of this design guide is primarily intended for developing modern web and mobile application.

This document is meant to be a living document. The software development standards, design patterns, frameworks, and best practices are continuously changing, and as they do and have been validated, this document will be updated accordingly.

## Software Design

The aims of the software design are to:

+ Define a list of the recommended technologies best practices, frameworks, and design patterns to be used as the development standard.
+ Set a path for adopting and/or migrating to the recommended technologies, frameworks and design patterns.
+ Ensure consistency and future extendability of the design.
+ Achieve high maintainability of the code.
+ Achieve high usage coverage & compatibility across various of client devices.

At the high-level, the design consists of 3 main layers:

+ Microservices
+ Service Gateway
+ Client Apps

--- Image diagram ---

The principles of these layers are:

+ All communications between client and server are done through one centralized service gateway. This is to make sure security enforcements, session management and common logic are managed in one place.
+ Microservices consists of business and data logics, Client Apps should purely handle user interface (UI) and user experience (UX) logic.
+ Microservices should be independent and have no awareness of their surrounding. The actions requested to microservices is done by interaction through its defined unique keys.
+ Reduce cross-dependency between client apps, service gateway and microservices. The structure should allow the setup of multi small independent teams to manage microservices and client apps, and on the same time to ensure a single control of security and common logic in one centralized small service gateway team.

### Microservices

The key principles of microservices are:

+ A small lightweight software of a specialized business logic implementation
+ Loosely coupled, it can be independently developed, deployed, and scaled
+ Communicate over network via technology-agnostic protocols
+ Stateless

Make use of 'Domain Driven Design' which consists of:

+ Service layer
+ Persistent / Data layer

### Service Gateway

The responsibilities of Service Gateway are:

+ Authentication
+ Authorization
+ Session management
+ Security enforcement


#### Authentication



#### Authorization



### Client Apps

Client Apps consists of User Interface and Experience logics, these are executed at the client device or browser.

#### UI Components


#### UI Containers


#### UI State

With the UI logics are managed at the client device or browser, the requirements to manage application state has increasingly become more complicated. This state can include server responses and cached data, as well as locally created data that has not yet persisted to the server.

## Performance Best Practices

## Team Structure
