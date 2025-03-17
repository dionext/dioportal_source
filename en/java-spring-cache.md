---
title: "Spring: Advanced"
description: ""
keywords: ""
lang: "en"
permalink: "java-spring-cache"
aliases:
  - "java-spring-cache"
---

## Spring: Cache

## Overview

## Cache abstraction

The cache abstraction applies caching to Java methods, thus reducing the number of executions based on the information available in the cache. That is, each time a targeted method is invoked, the abstraction applies a caching behavior that checks whether the method has been already invoked for the given arguments. If it has been invoked, the cached result is returned without having to invoke the actual method. If the method has not been invoked, then it is invoked, and the result is cached and returned to the user so that, the next time the method is invoked, the cached result is returned.

This approach works only for methods that are guaranteed to return the same output (result) for a given input (or arguments) no matter how many times they are invoked.

[https://docs.spring.io/spring-framework/reference/integration/cache.html](https://docs.spring.io/spring-framework/reference/integration/cache.html) Cache Abstraction

Simple Example:

Enabling Caching Annotations

```java
@EnableCaching
public class MainMsAppApplication {
```

```java
    @Cacheable("sitemap")
    public String createSitemap() {
    
```

Note: there is some problems using cacheable method in the same class. See: [https://stackoverflow.com/questions/63958101/springs-cacheable-not-working-when-called-from-the-controller-in-spring-boot](https://stackoverflow.com/questions/63958101/springs-cacheable-not-working-when-called-from-the-controller-in-spring-boot)

Using specified keys:

```java
@Cacheable(cacheNames="books", key="#isbn.rawNumber")
public Book findBook(ISBN isbn, boolean checkWarehouse, boolean includeUsed)
```

Synchronized Caching

```java
@Cacheable(cacheNames="foos", sync=true) 
public Foo executeExpensiveOperation(String id) {...}
```

Clearing cache:

```java

@CacheEvict(cacheNames="books", allEntries=true) 
public void loadBooks(InputStream batch)
```

```java

@CacheRemoveAll (cacheNames="books") 
public void loadBooks(InputStream batch)
```

```
 
```

TTL - The time to live specifies how long a cache entry may remain in the cache independently of access. After the specified time has expired, the value is removed from the cache.

TTI - The time to idle specifies how long the cache entry may exist in the cache without access. For example, if a value is not requested for more than 30 seconds, it is removed from the cache.

## Spring Boot Cache Providers

* JCache (JSR-107)
* EhCache (distributed)
* Hazelcast (distributed)
* Guava (in-memory)
* Infinispan (distributed)
* Couchbase (distributed)
* Redis (distributed)
* Memcached (distributed)
* Caffeine (in-memory)
* Simple (in-memory)

### Simple {\#272f}

It is the default implementation. It configures a ConcurrentHashMap as a cache store if spring boot does not find any cache provider in the classpath.{#c787}

### Caffeine {\#0e04}

Caffeine is a high performance Java based caching library. It also provides an in-memory cache. The spring boot automatically configures the CaffeineCacheManager if Caffeine is found in the classpath.

[https://www.baeldung.com/java-caching-caffeine](https://www.baeldung.com/java-caching-caffeine)

[https://ranawakay.medium.com/spring-boot-and-caffeine-cache-with-microservices-e72d36d68377](https://ranawakay.medium.com/spring-boot-and-caffeine-cache-with-microservices-e72d36d68377)

[https://dev.to/noelopez/spring-cache-with-caffeine-384l](https://dev.to/noelopez/spring-cache-with-caffeine-384l) Spring Cache with Caffeine

### EhCache

[https://www.ehcache.org/documentation/2.7/configuration/cache-size.html](https://www.ehcache.org/documentation/2.7/configuration/cache-size.html)

[https://howtodoinjava.com/spring-boot/spring-boot-ehcache-example/](https://howtodoinjava.com/spring-boot/spring-boot-ehcache-example/) Spring Boot and Ehcache 3 Example

[https://github.com/SimpleProgramming/spring-boot-ehCache-CacheManager](https://github.com/SimpleProgramming/spring-boot-ehCache-CacheManager)
