---
title: "Spring: Base knowledges"
description: ""
keywords: ""
lang: "en"
permalink: "java-spring-base"
aliases:
  - "java-spring-base"
---

# Spring: Base knowledges

## Overview

The Spring Framework is an application framework and inversion of control container for the Java platform.

The Spring Framework provides a comprehensive programming and configuration model for modern Java-based enterprise applications - on any kind of deployment platform. A key element of Spring is infrastructural support at the application level: Spring focuses on the "plumbing" of enterprise applications so that teams can focus on application-level business logic, without unnecessary ties to specific deployment environments.

Official site: [https://spring.io/projects/spring-boot](https://spring.io/projects/spring-boot)

Spring architecture based on: Inversion of Control, Dependency Injection (IoC, DI, DIP)

**Inversion of control** (IoC) is a design pattern in which custom-written portions of a computer program receive the flow of control from a generic framework. The term "inversion" is historical: a software architecture with this design "inverts" control as compared to procedural programming. In procedural programming, a program's custom code calls reusable libraries to take care of generic tasks, but with inversion of control, it is the framework that calls the custom code.

Inversion of control (IoC) is a design pattern in which custom-written portions of a computer program receive the flow of control from a generic framework. The term "inversion" is historical: a software architecture with this design "inverts" control as compared to procedural programming. [https://en.wikipedia.org/wiki/Inversion\_of\_control](https://en.wikipedia.org/wiki/Inversion_of_control)

The main idea of ioc is that the program no longer creates and manages objects on its own, but transfers this responsibility to the container, which itself takes care of creating and managing objects within the program.

This principle allows for a more flexible application architecture, since objects are more loosely coupled to each other and can be easily replaced or modified without making changes to the main program code.Dependency Inversion Principle (DIP)?

[https://www.tutorialsteacher.com/ioc/dependency-inversion-principle](https://www.tutorialsteacher.com/ioc/dependency-inversion-principle)

DIP is one of the SOLID object-oriented principle invented by Robert Martin (a.k.a. Uncle Bob)
DIP Definition

1. High-level modules should not depend on low-level modules. Both should depend on the abstraction.
2. Abstractions should not depend on details. Details should depend on abstractions.

Dependency Injection (DI) is a design pattern which implements the IoC principle to invert the creation of dependent objects.
IoC Container

The IoC container is a framework used to manage automatic dependency injection throughout the application, so that we as programmers do not need to put more time and effort into it.

## IoC explanation

To put it simply, the main problem that can be solved is reducing the number of links that the programmer is forced to create in order to transfer an object from one part of the program to another. We are, of course, talking about those objects that are not purely local. The objects we are talking about are, as a rule, created at the start of the program, and their use may be needed by other objects that are located quite far away in the extensive network of program objects.

Let's look at this with the following example. One typical object of this kind is the CachManager caching manager. It must be created at the very beginning of loading the program and then it may be needed in various blocks of the program. For example, you have a block where certain business data is processed. It is implemented as a separate class BusinessService and a separate object. There are also other similar classes and objects FirstChildBusinessService, SecondChildBusinessService, created inside BusinessService.

How can I give them all the ability to use the CachManager object? The easiest way is to pass CachManager as parameters when creating the BusinessService or by calling the set method. Then pass it along the chain to FirstChildBusinessService and SecondChildBusinessService. It is easy to see that with a large number of global objects, the creation and subsequent support of such a branched structure becomes very complex.

How can this problem be solved in simple ways? Perhaps the easiest way is to use a static variable. It however has a number of disadvantages.

```java
public class Main {
    CachManager cachManager;
    AnotherManager anotherManager;
    public static void main(String[] args) {
        Main main = new Main();
        main.doWork();
    }
    public Main(){
        cachManager = new CachManager();
        anotherManager = new AnotherManager();
    }
    public void doWork(){
        BusnessService busnessService = new BusnessService(cachManager, anotherManager);
        busnessService.doSomeBusnessWork();
    }
}
class CachManager {
    public void doSomeWork(){}
}
class AnotherManager {
    public void doAnotherWork(){}
}
class BusnessService {
    private CachManager cachManager;
    private AnotherManager anotherManager;
    private FirstChildBusnessService firstChildBusnessService;
    private SecondChildBusnessService secondChildBusnessService;
    public BusnessService(CachManager cachManager, AnotherManager anotherManager){
        this.cachManager = cachManager;
        this.anotherManager = anotherManager;
        firstChildBusnessService = new FirstChildBusnessService(cachManager, anotherManager);
        secondChildBusnessService = new SecondChildBusnessService(cachManager, anotherManager);
    }
    public void doSomeBusnessWork(){
        firstChildBusnessService.doSomeBusnessWork();
        secondChildBusnessService.doSomeBusnessWork();
    }
}
class FirstChildBusnessService {
    private CachManager cachManager;
    private AnotherManager anotherManager;
    public FirstChildBusnessService(CachManager cachManager, AnotherManager anotherManager) {
        this.cachManager = cachManager;
        this.anotherManager = anotherManager;
    }
    public void doSomeBusnessWork(){
        cachManager.doSomeWork();
        anotherManager.doAnotherWork();
    }
}
class SecondChildBusnessService{
    private CachManager cachManager;
    private AnotherManager anotherManager;
    public SecondChildBusnessService(CachManager cachManager, AnotherManager anotherManager){
        this.cachManager = cachManager;
        this.anotherManager = anotherManager;
    }
    public void doSomeBusnessWork(){
        cachManager.doSomeWork();
        anotherManager.doAnotherWork();
    }
}
```

Another approach is using Singleton pattern [https://www.digitalocean.com/community/tutorials/java-singleton-design-pattern-best-practices-examples](https://www.digitalocean.com/community/tutorials/java-singleton-design-pattern-best-practices-examples)

```java
public class SingletonExample {
    private static SingletonExample instance;
    private SingletonExample() {
    }
    public static synchronized SingletonExample getInstance() {
        if (instance == null) {
            instance = new SingletonExample();
        }
        return instance;
    }
}
```

Example of same task using Spring

```java
@SpringBootApplication
public class DemoApplication implements ApplicationRunner {
	@Autowired
	BusnessService busnessService;
	public static void main(String[] args) {
		SpringApplication.run(DemoApplication.class, args);
	}
	@Override
	public void run(ApplicationArguments args) throws Exception {
		busnessService.doSomeBusnessWork();
	}
}
@Service
public class BusnessService {
    @Autowired
    private FirstChildBusnessService firstChildBusnessService;
    @Autowired
    private SecondChildBusnessService secondChildBusnessService;

    public void doSomeBusnessWork() {
        firstChildBusnessService.doSomeBusnessWork();
        secondChildBusnessService.doSomeBusnessWork();
    }
}
@Service
public class FirstChildBusnessService {
    @Autowired
    private CachManager cachManager;
    @Autowired
    private AnotherManager anotherManager;

    public FirstChildBusnessService() {
    }
    public void doSomeBusnessWork() {
        cachManager.doSomeWork();
        anotherManager.doAnotherWork();
    }
}
@Service
public class SecondChildBusnessService{
    @Autowired
    private CachManager cachManager;
    @Autowired
    private AnotherManager anotherManager;
    public SecondChildBusnessService(){
    }
    public void doSomeBusnessWork(){
        cachManager.doSomeWork();
        anotherManager.doAnotherWork();
    }
}
@Component
public class CachManager {
    public void doSomeWork() {
    }
}
@Component
public class AnotherManager {
    public void doAnotherWork() {
    }
}
```

## Another Spring features

The Spring Framework includes several modules that provide a range of services:

* Aspect-oriented programming: enables implementing cross-cutting concerns.
* Authentication and authorization
* Convention over configuration: a rapid application development solution for Spring-based enterprise applications is offered in the Spring Roo module.
* Data access: working with relational database management systems on the Java platform
* Messaging: declarative registration of message listener objects for transparent message-consumption from message queues via Java Message Service (JMS)
* Model--view--controller: an HTTP- and servlet-based framework providing hooks for extension and customization for web applications and RESTful (representational state transfer) Web services.
* Remote access framework: declarative remote procedure call (RPC)-style
* Transaction management: unifies several transaction management APIs and coordinates transactions for Java objects
* Testing: support classes for writing unit tests and integration tests.
* WebFlux support
* Web Socket support
* XML support

## Initial Spring project creation

Варианты создания нового проекта:

* Online конструктор: [https://start.spring.io/](https://start.spring.io/)
* IntelliJ IDEA Ultimate (File-New-Project...-Spring Initializer).
* Spring Boot CLI

Рекомендации по струкруре директорий и т.п. [https://docs.spring.io/spring-boot/docs/current/reference/html/using-boot-structuring-your-code.html](https://docs.spring.io/spring-boot/docs/current/reference/html/using-boot-structuring-your-code.html)

## Spring Starters {\#using.build-systems.starters}

Starters are a set of convenient dependency descriptors that you can include in your application. You get a one-stop shop for all the Spring and related technologies that you need without having to hunt through sample code and copy-paste loads of dependency descriptors. For example, if you want to get started using Spring and JPA for database access, include the spring-boot-starter-data-jpa dependency in your project. The starters contain a lot of the dependencies that you need to get a project up and running quickly and with a consistent, supported set of managed transitive dependencies.  
[Creating Your Own Starter](https://docs.spring.io/spring-boot/docs/current/reference/html/features.html#features.developing-auto-configuration.custom-starter)

List of starters [https://docs.spring.io/spring-boot/docs/current/reference/html/using.html](https://docs.spring.io/spring-boot/docs/current/reference/html/using.html)

## Auto-configuration {\#using.auto-configuration}

Spring Boot auto-configuration attempts to automatically configure your Spring application based on the jar dependencies that you have added. For example, if HSQLDB is on your classpath, and you have not manually configured any database connection beans, then Spring Boot auto-configures an in-memory database.  
You need to opt-in to auto-configuration by adding the @EnableAutoConfiguration or @SpringBootApplication annotations to one of your @Configuration classes.

Disabling Specific Auto-configuration Classes - If you find that specific auto-configuration classes that you do not want are being applied, you can use the exclude attribute of

@SpringBootApplication to disable them @SpringBootApplication(exclude = { DataSourceAutoConfiguration.class }) {#id41}

## References

[https://spring.io/docs/reference](https://spring.io/docs/reference)

3\.3.x - [https://docs.spring.io/spring-boot/docs/3.3.x/reference/html/](https://docs.spring.io/spring-boot/docs/3.3.x/reference/html/)

Spring Boot Reference Guide [https://docs.spring.io/spring-boot/docs/current/reference/html/index.html](https://docs.spring.io/spring-boot/docs/current/reference/html/index.html)

Petclinic demo project [https://github.com/spring-petclinic](https://github.com/spring-petclinic) [https://github.com/spring-projects/spring-petclinic](https://github.com/spring-projects/spring-petclinic) [https://www.thymeleaf.org/doc/articles/petclinic.html](https://www.thymeleaf.org/doc/articles/petclinic.html) [https://hub.docker.com/r/jbrisbin/spring-petclinic/](https://hub.docker.com/r/jbrisbin/spring-petclinic/) [https://learn.microsoft.com/en-us/azure/spring-apps/quickstart-sample-app-introduction?tabs=basic-standard-plan\&pivots=programming-language-java](https://learn.microsoft.com/en-us/azure/spring-apps/quickstart-sample-app-introduction?tabs=basic-standard-plan&pivots=programming-language-java) [https://gitlab.com/sylvere\_zorer/spring-petclinic-microservices](https://gitlab.com/sylvere_zorer/spring-petclinic-microservices)

Examples [https://github.com/spring-projects/spring-boot/tree/master/spring-boot-samples](https://github.com/spring-projects/spring-boot/tree/master/spring-boot-samples) [https://github.com/codecentric/springboot-sample-app](https://github.com/codecentric/springboot-sample-app) {#id13} [https://github.com/in28minutes/spring-boot-examples](https://github.com/in28minutes/spring-boot-examples)

[https://github.com/Java-Techie-jt/springboot-rabbitmq-example](https://github.com/Java-Techie-jt/springboot-rabbitmq-example) springboot-rabbitmq-example [https://www.youtube.com/watch?v=o4qCdBR4gUM](https://www.youtube.com/watch?v=o4qCdBR4gUM) Spring Boot RabbitMQ | Publisher \& Subscriber Example | AMQP | JavaTechie
