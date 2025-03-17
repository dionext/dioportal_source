---
title: "Spring: Configuration"
description: ""
keywords: ""
lang: "en"
permalink: "java-spring-configuration"
aliases:
  - "java-spring-configuration"
---

# Spring: {\#id1}Configuration

## Properties Configuration

Properties play an important role in almost all applications and can come from various sources: file properties, JVM system properties, operating system environment, JNDI, etc. Properties are represented by a set of PropertySource objects and the values are ultimately obtained from the same sources as System.getProperties () and System.getenv()

SpringApplication loads properties from application.properties files in the following locations and adds them to the Spring Environment:

* The /config subdirectory of the current directory
* The current directory
* The /config package in the classpath
* The classpath root

The list is ordered by priority (properties defined in locations higher in the list override properties defined in locations lower).

You can also use YAML files ('.yml') as an alternative to '.properties'. If you don't like application.properties as the configuration file name, you can switch to a different file name by specifying the spring.config.name environment property. You can also reference an explicit location using the spring.config.location environment property (which is a comma-separated list of directory locations or file paths).

[https://docs.spring.io/spring-boot/docs/1.5.22.RELEASE/reference/html/boot-features-external-config.html](https://docs.spring.io/spring-boot/docs/1.5.22.RELEASE/reference/html/boot-features-external-config.html)

[https://docs.spring.io/spring-boot/docs/current/reference/htmlsingle/#features.external-config](https://docs.spring.io/spring-boot/docs/current/reference/htmlsingle/#features.external-config)

Spring Boot uses a very particular PropertySource order that is designed to allow sensible overriding of values. Properties are considered in the following order:

1. [Devtools global settings properties](https://docs.spring.io/spring-boot/docs/1.5.22.RELEASE/reference/html/using-boot-devtools.html#using-boot-devtools-globalsettings "20.4 Global settings") on your home directory (~/.spring-boot-devtools.properties when devtools is active).
2. [@TestPropertySource](https://docs.spring.io/spring/docs/4.3.25.RELEASE/javadoc-api/org/springframework/test/context/TestPropertySource.html) annotations on your tests.
3. [@SpringBootTest#properties](https://docs.spring.io/spring-boot/docs/1.5.22.RELEASE/api/org/springframework/boot/test/context/SpringBootTest.html) annotation attribute on your tests.
4. Command line arguments.
5. Properties from SPRING\_APPLICATION\_JSON (inline JSON embedded in an environment variable or system property)
6. ServletConfig init parameters.
7. ServletContext init parameters.
8. JNDI attributes from java:comp/env.
9. Java System properties (System.getProperties()).
10. OS environment variables.
11. A RandomValuePropertySource that only has properties in random.\*.
12. [Profile-specific application properties](https://docs.spring.io/spring-boot/docs/1.5.22.RELEASE/reference/html/boot-features-external-config.html#boot-features-external-config-profile-specific-properties "24.4 Profile-specific properties") outside of your packaged jar (application-{profile}.properties and YAML variants)
13. [Profile-specific application properties](https://docs.spring.io/spring-boot/docs/1.5.22.RELEASE/reference/html/boot-features-external-config.html#boot-features-external-config-profile-specific-properties "24.4 Profile-specific properties") packaged inside your jar (application-{profile}.properties and YAML variants)
14. Application properties outside of your packaged jar (application.properties and YAML variants).
15. Application properties packaged inside your jar (application.properties and YAML variants).
16. [@PropertySource](https://docs.spring.io/spring/docs/4.3.25.RELEASE/javadoc-api/org/springframework/context/annotation/PropertySource.html) annotations on your @Configuration classes.
17. Default properties (specified using SpringApplication.setDefaultProperties).

## Spring profiles

[https://www.baeldung.com/spring-profiles](https://www.baeldung.com/spring-profiles)

Activating or Setting a Profile[](https://www.baeldung.com/spring-profiles#1-activating-or-setting-a-profile)

```bash
spring.profiles.active=dev
```

[https://reflectoring.io/spring-boot-profiles/#how-to-activate-profiles](https://reflectoring.io/spring-boot-profiles/#how-to-activate-profiles)

```
export SPRING_PROFILES_ACTIVE=test,prod
```

```
java -Dspring.profiles.active=prod -jar profiles-0.0.1-SNAPSHOT.jar
```

```
 application.setAdditionalProfiles("baz");
application.run(args);
```

```
@SpringBootTest
@ActiveProfiles({"foo", "bar"})
class FooBarProfileTest {
```

A profile is a named group of bean definitions that are registered by the container only when the profile is active. A bean definition profile allows you to register different beans for different environments. For example, you have two application stands, testing, where you test for errors, and production, the actual working application. At the same time, some parameters in your environments will probably differ, such as connecting to a database, etc. Profiles will help you a lot, because you don't have to change anything every time and rebuild for each environment.

## Search for resources and files

[https://howtodoinjava.com/spring-boot2/read-file-from-resources/](https://howtodoinjava.com/spring-boot2/read-file-from-resources/)

[https://www.baeldung.com/spring-load-resource-as-string](https://www.baeldung.com/spring-load-resource-as-string)

```java
@Autowired 
private ResourceLoader resourceLoader;
public void method() { 
	Resource resource = resourceLoader.getResource("classpath:filename.txt"); 
	File file = resource.getFile()); 
//... } 
//OR 
Resource resource = new ClassPathResource("classpath:filename.txt"); 
//OR 
@Value("classpath:filename.txt") 
Resource resource;
```

There are a number of Resource implementations inbuilt in Spring such as

* ClassPathResource: loads a resource from the classpath. We can specify the path to the resource relative to the root of the classpath. It supports resolution as java.io.File if the class path resource resides in the filesystem but not for resources in a JAR. It recognizes the special prefix 'classpath:'on the string path.
* UrlResource: Loads a resource from a URL. We can specify the URL of the resource with prefix 'http:' or 'file:' if it is a file protocol.
* FileSystemResource: Loads a resource from the file system. We can specify the absolute path to the resource on the file system with prefix 'file:'.
* ServletContextResource: Loads a resource from the ServletContext. We can specify the path to the resource relative to the ServletContext. It does not use any prefixes.

```java
Resource classPathResource = resourceLoader.getResource("classpath:file.txt"); 
Resource urlResource = resourceLoader.getResource("http://example.com/file.txt"); 
Resource fileSystemResource = resourceLoader.getResource("file:/path/to/file.txt"); 
Resource servletContextResource = resourceLoader.getResource("/WEB-INF/file.txt");
File file = resource.getFile(); 
String content = new String(Files.readAllBytes(file.toPath()));
```
