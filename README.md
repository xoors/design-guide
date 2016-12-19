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

+ All communications between client and server are done through one centralized service gateway. This is to make sure security enforcements, session management and common logic are managed in one common place.
+ Microservices consists of business and data logics, Client Apps should purely handle user interface (UI) and user experience (UX) logic.
+ Microservices should be independent and have no awareness of their surrounding. The actions requested to microservices is done by interaction through its defined unique keys.
+ Reduce cross-dependency between client apps, service gateway and microservices. The structure should allow the setup of multi small independent teams to manage microservices and client apps, and on the same time to ensure a single control of security and common logic in one centralized small service gateway team.

### Microservices

The characteristics of microservices are:

+ A small lightweight software of a specialized business logic implementation
+ Loosely coupled, it can be independently developed, deployed, and scaled
+ Communicate over network via 'technology agnostic' protocols
+ Stateless

Make use of 'Domain Driven Design', which consists of:

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

Client Apps consists of user interface (UI) and experience (UX) logics, these are executed at the client device or browser. We recommends to use 'Responsive Web Design' primarily because we believe web technology will continue to advance further at faster pace, and the trend will lead to technology investments to evolve mostly around web technology. The speed and performance of browser engines will continue to improve, and devices as well as the speed of internet connection will greatly increased as well. There are some best practices for developing high performance web application, refer to [Performance Best Practices](#performance-best-practices)

#### UI Components


#### UI Containers


#### UI State

With the UI logics are managed at the client device or browser, the requirements to manage application state has increasingly become more complicated. This state can include server responses and cached data, as well as locally created data that has not yet persisted to the server.

## Performance Best Practices

In order to develop a high performance web application, there are some best practices to follow.

+ Choose JavaScript and CSS framework which have been optimized and tested to work well across devices. For e.g. [Bootstrap](http://getbootstrap.com/) is a popular CSS framework for developing responsive web design.
+ Optimize all UI artifacts, e.g. reduce image size. Reduce image quality to the optimum quality as needed to display to the users.
+ Use image sprite to reduce client requests to the server.
+ Use compression, e.g. image compression, page compression.
+ Implement adaptive JavaScript logic to decide a specific image size to send to small size devices.
+ Use CSS or SVG for icons, logos, buttons, or small size images.
+ Make sure all client logics and contents are cacheable on CDN (Content Delivery Network). Set appropriate cache settings and expiration time.
+ Remove unused JS and CSS components. Avoid from blindly using common superset framework. Common framework tends to be packaged with all supported components which all of them may not be used in your application.
+ Use 'rem' instead of 'px' to reduce hardcode logic and redundant code in CSS.
+ Adopt 'Client MVC' design, do not use server side to process UI / UX logic. For e.g. using JSP code to produce HTML output is not advisable.
+ Clean segregation between UI / UX, Content, and Data logic.
+ Implement 'Event Driven Design'. A request to and response from server should be specific to the event triggered from the client, for e.g.: Pagination logic, clicking on the next page should be responded only with data as the output. Changing language preference should be responded only with contents specific to the active page.
+ On mobile app, UI / UX artifacts should be wrapped on the app. Use wrapper framework like Cordova / PhoneGap.
+ ...

## Team Structure
