---
title: "Microservices"
description: "Advantages and disadvantages of microservice architecture and monolit"
keywords: "Microservices, monolith, SPOF"
lang: "en"
permalink: "architecture-microservices"
aliases:
  - "architecture-microservices"
---

# Microservices

## Microservices vs monolith

Knowing the advantages and disadvantages of microservice architecture and monolith is relevant not only for those developers who are thinking about migrating from monolithic architecture to microservice architecture, but also for those who have already switched to microservice architecture. After all, when implementing each new task, the developer must inevitably make a choice: whether to include the implementation of this task in one of the existing microservices or create a new microservice to solve this task.

Advantages of microservice architecture:

* Microservice architecture will allow you to create separate teams, each of which develops its own microservices. These teams can develop solutions in parallel without interfering with each other.
* Each microservice can be deployed independently. If one of the teams has finished developing its functionality, it can launch it in production. At the same time, the business will already receive some benefits while other teams are finishing their part of the functionality.
* Scalability. Each of the services can be run in many instances. If you have difficulties in only one highly loaded place, then you can multiply this place and scale horizontally.
* Each of the microservices individually is a much simpler solution than a common monolithic system. As a last resort, if a particular microservice no longer meets specific business requirements, it can be discarded and rewritten.
* Expanding the ability to use different technologies and different programming languages in one solution.

Disadvantages of microservice architecture:

* Time and resource-consuming
* Complicated deployment. All together, microservices will be more difficult to develop than a monolith. For example, if you decide to change the approach to deploying a solution, then you will have to change it for each of the microservices.
* Complex testing. In a monolith, you have everything connected: you have compiled and ensured that one part of the subsystem, at least at the contract level, communicates with another part of the subsystem. In a microservices architecture, you have to verify through integration tests that contracts are respected.
* Complicated maintenance. Each of the services needs to be monitored independently: a service may hit a memory limit, communication with another service may be interrupted and not automatically restored, there may be memory leaks, deadlocks, etc. The process of maintaining your solution becomes much more complicated
* Integrity of contracts and data. Each microservice works with its own storage, the data is not integrated with each other: there is no foreign key, and, accordingly, it is much more difficult to maintain data integrity. Since each of the services can be developed independently (an advantage), it can also be changed independently your contract. It's good if we notice this during integration testing. It's worse if we notice this in production.

## SPOF

A single point of failure (SPOF) is a part of a system that, if it fails, will stop the entire system from working. SPOFs are undesirable in any system with a goal of high availability or reliability, be it a business practice, software application, or other industrial system. [https://en.wikipedia.org/wiki/Single\_point\_of\_failure](https://en.wikipedia.org/wiki/Single_point_of_failure)

## References

[https://www.openlegacy.com/blog/monolithic-application](https://www.openlegacy.com/blog/monolithic-application)

[https://dou.ua/lenta/articles/microservices-net-core/](https://dou.ua/lenta/articles/microservices-net-core/)
