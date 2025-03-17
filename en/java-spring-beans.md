---
title: "Spring: Beans, Components, Services"
description: ""
keywords: ""
lang: "en"
permalink: "java-spring-beans"
aliases:
  - "java-spring-beans"
---

# Spring: Beans, Components, Services

## Component declaration

Simple annotation

```java
@Component
public class PageInfo
{
}
```

Annotation with specified scope

```java
@Component
@RequestScope
public class PageInfo
{
}
```

## Bean declaration

To declare a Bean object, it is enough to specify the @Bean annotation to the method that returns the bean type both in classes with the @Configuration annotation and in classes with the @Component annotation (or its descendants).

```java
@Configuration 
public class LessonsConfiguration 
{ 
	@Bean
	GreetingService greetingService() {
		return new GreetingServiceImpl(); 
	} 
}
```

Named beans

```java
@Bean(name = "gServiceName")
@Bean(name = {"gServiceName", "gServiceAnotherNamed"})
```

## Bean scopes

[https://docs.spring.io/spring-framework/reference/core/beans/factory-scopes.html](https://docs.spring.io/spring-framework/reference/core/beans/factory-scopes.html)

|                                                              Scope                                                               |                                                                                                                        Description                                                                                                                         |
|----------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [singleton](https://docs.spring.io/spring-framework/reference/core/beans/factory-scopes.html#beans-factory-scopes-singleton)     | (Default) Scopes a single bean definition to a single object instance for each Spring IoC container.                                                                                                                                                       |
| [prototype](https://docs.spring.io/spring-framework/reference/core/beans/factory-scopes.html#beans-factory-scopes-prototype)     | Scopes a single bean definition to any number of object instances.                                                                                                                                                                                         |
| [request](https://docs.spring.io/spring-framework/reference/core/beans/factory-scopes.html#beans-factory-scopes-request)         | Scopes a single bean definition to the lifecycle of a single HTTP request. That is, each HTTP request has its own instance of a bean created off the back of a single bean definition. Only valid in the context of a web-aware Spring ApplicationContext. |
| [session](https://docs.spring.io/spring-framework/reference/core/beans/factory-scopes.html#beans-factory-scopes-session)         | Scopes a single bean definition to the lifecycle of an HTTP Session. Only valid in the context of a web-aware Spring ApplicationContext.                                                                                                                   |
| [application](https://docs.spring.io/spring-framework/reference/core/beans/factory-scopes.html#beans-factory-scopes-application) | Scopes a single bean definition to the lifecycle of a ServletContext. Only valid in the context of a web-aware Spring ApplicationContext.                                                                                                                  |
| [websocket](https://docs.spring.io/spring-framework/reference/web/websocket/stomp/scope.html)                                    | Scopes a single bean definition to the lifecycle of a WebSocket. Only valid in the context of a web-aware Spring ApplicationContext.                                                                                                                       |

{#beans-factory-scopes-tbl}

### @Bean vs @Component

@Component is a class level annotation whereas @Bean is a method level annotation and name of the method serves as the bean name

We cannot create a bean of a class using @Component, if the class is outside spring container whereas we can create a bean of a class using @Bean even if the class is present outside the spring container. By using the @Bean annotation, you can wrap a third-party class (it may not have @Component and it may not use Spring), as a Spring bean.

[https://stackoverflow.com/questions/10604298/spring-component-versus-bean](https://stackoverflow.com/questions/10604298/spring-component-versus-bean)

### @Configuration

@Configuration is a class-level annotation indicating that an object is a source of bean definitions. @Configuration classes declare beans through @Bean-annotated methods. Calls to @Bean methods on @Configuration classes can also be used to define inter-bean dependencies.

### @ComponentScan

**Official documentation states: We generally recommend that you locate your main application class in a root package above other classes.**

So that your configuration can know about such components and you can use them, there is a special annotation for your configuration class @ComponentScan. By default, this configuration scans for classes with the @Component annotation and its descendants in the package in which it is located, as well as in subpackages.

However, if you want the scan to be for specific directories, then this can be configured by simply adding the basePackages parameter to the @ComponentScan annotation, indicating one or more packages. It will look something like this: @ComponentScan(basePackages = "lessons.services")

@ComponentScan without arguments tells Spring to scan the current package and all of its sub-packages.

You can use aproach as in example: ( [https://stackoverflow.com/questions/55750957/why-is-this-componentscan-not-working-in-my-spring-boot-application](https://stackoverflow.com/questions/55750957/why-is-this-componentscan-not-working-in-my-spring-boot-application) )

```
@ComponentScan
@ComponentScan(basePackages = {"com.dionext"})
@EnableJpaRepositories(basePackages = "com.dionext")
@EntityScan(basePackages = "com.dionext")
public class ExFrontendDemoApplication {
```

### @Component @Repository, @Service и @Controller

[https://stackoverflow.com/questions/6827752/whats-the-difference-between-component-repository-service-annotations-in](https://stackoverflow.com/questions/6827752/whats-the-difference-between-component-repository-service-annotations-in)

| Annotation  |                       Meaning                       |
|-------------|-----------------------------------------------------|
| @Component  | generic stereotype for any Spring-managed component |
| @Repository | stereotype for persistence layer                    |
| @Service    | stereotype for service layer                        |
| @Controller | stereotype for presentation layer (spring-mvc)      |

In addition to pointing out, that this is an Annotation based Configuration, @Repository's job is to catch platform specific exceptions and re-throw them as one of Spring's unified unchecked exception.

The dispatcher scans the classes annotated with @Controller and detects methods annotated with @RequestMapping annotations within them. We can use @RequestMapping on/in only those methods whose classes are annotated with @Controller

### Pre and Post Events

Use annotation: @PostConstruct and @PreDestroy

### Bean access {\#scopes}

Example

```java

public class SomeClass { 
	
	private ApplicationContext context; 

	@Autowired 
	public void setContext(ApplicationContext context) { this.context = context; } 
	
	public void someMethod(){
		GreetingService greetingService = context.getBean(GreetingService.class); 
	}
}
```

[https://www.baeldung.com/spring-get-current-applicationcontext](https://www.baeldung.com/spring-get-current-applicationcontext)

### Autowiring

[https://docs.spring.io/spring-framework/reference/core/beans/dependencies/factory-collaborators.html#beans-constructor-injection](https://docs.spring.io/spring-framework/reference/core/beans/dependencies/factory-collaborators.html#beans-constructor-injection)

Recommended:

Constructor-based Dependency Injection

```java
public class SimpleMovieLister {

	// the SimpleMovieLister has a dependency on a MovieFinder
	private final MovieFinder movieFinder;

	// a constructor so that the Spring container can inject a MovieFinder
	public SimpleMovieLister(MovieFinder movieFinder) {
		this.movieFinder = movieFinder;
	}

	// business logic that actually uses the injected MovieFinder is omitted...
}
```

Setter-based Dependency Injection

```java

public class SimpleMovieLister {

	// the SimpleMovieLister has a dependency on the MovieFinder
	private MovieFinder movieFinder;

	// a setter method so that the Spring container can inject a MovieFinder
	public void setMovieFinder(MovieFinder movieFinder) {
		this.movieFinder = movieFinder;
	}

	// business logic that actually uses the injected MovieFinder is omitted...
}
```
