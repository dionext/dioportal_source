---
title: "Spring: WEB and REST"
description: ""
keywords: ""
lang: "en"
permalink: "java-spring-web"
aliases:
  - "java-spring-web"
---

## Spring controller mapping rules

Some example patterns:

* "/resources/ima?e.png" - match one character in a path segment

* "/resources/\*.png" - match zero or more characters in a path segment

* "/resources/\*\*" - match multiple path segments

* "/projects/{project}/versions" - match a path segment and capture it as a variable

* "/projects/{project:\[a-z\]+}/versions" - match and capture a variable with a regex

When multiple patterns match a URL, the best match must be selected. This is done with one of the following depending on whether use of parsed PathPattern is enabled for use or not:

* [PathPattern.SPECIFICITY\_COMPARATOR](https://docs.spring.io/spring-framework/docs/6.1.3/javadoc-api/org/springframework/web/util/pattern/PathPattern.html#SPECIFICITY_COMPARATOR)

* [AntPathMatcher.getPatternComparator(String path)](https://docs.spring.io/spring-framework/docs/6.1.3/javadoc-api/org/springframework/util/AntPathMatcher.html#getPatternComparator-java.lang.String-)

Both help to sort patterns with more specific ones on top. A pattern is more specific if it has a lower count of URI variables (counted as 1), single wildcards (counted as 1), and double wildcards (counted as 2). Given an equal score, the longer pattern is chosen. Given the same score and length, the pattern with more URI variables than wildcards is chosen.  
The default mapping pattern (/\*\*) is excluded from scoring and always sorted last. Also, prefix patterns (such as /public/\*\*) are considered less specific than other pattern that do not have double wildcards.  
For the full details, follow the above links to the pattern Comparators.
Starting in 5.3, by default Spring MVC no longer performs .\* suffix pattern matching where a controller mapped to /person is also implicitly mapped to /person.\*. As a consequence path extensions are no longer used to interpret the requested content type for the response - for example, /person.pdf, /person.xml, and so on.

See also: [REST URL pattern best practice](integration-technologies)

## Static content

Static content support, that is, the ability to add static content, such as HTML, JavaScript, CSS, media elements, etc., to the /static (default) or /public, /resources, or /META-INF/resources directory, which should located on the classpath or in the current directory. Spring Boot picks them up and produces them when requested.

## Spring Data Rest, HATEOAS, HAL

[https://docs.spring.io/spring-data/rest/docs/current/reference/html/#reference](https://docs.spring.io/spring-data/rest/docs/current/reference/html/#reference)

[https://www.youtube.com/watch?v=h\_e1picwRBg](https://www.youtube.com/watch?v=h_e1picwRBg)

[https://chrome.google.com/webstore/detail/json-formatter/bcjindcccaagfpapjjmafapmmgkkhgoa?hl=ru](https://chrome.google.com/webstore/detail/json-formatter/bcjindcccaagfpapjjmafapmmgkkhgoa?hl=ru) Плугин к хрому JSON formater

[https://www.baeldung.com/spring-rest-hal](https://www.baeldung.com/spring-rest-hal)

## JSON serializers and deserializers.

To better control serialization/deserialization to/from JSON format, Spring Boot provides the ability to create your own serializers/deserializers by extending the JsonSerializer and/or JsonDeserializer types and annotating the generated class with @JsonComponent so that it can be registered for use. Another feature of Spring Boot is Jackson support; By default, Spring Boot serializes date fields in the format 2018-05-01T23:31:38.141+0000, but this default behavior can be changed by changing the property value spring.jackson.dateformat=yyyy-MM-dd (any date format pattern can be used ); the previous value causes output like 2018-05-01 to be generated.

## Validation

Annotation by @Valid. This annotation checks the correctness of incoming data and is used in method parameters. To run the check, the data that needs to be checked must be provided with one of the annotations - @NotNull, @NotBlank, etc. In this case, in the ToDo class, the fields for identifier and description are provided with the specified annotations. If errors are found during validation, they are collected in the Errors class (in this case, the hibernate validator supplied with the spring-webmvc module JARs is registered and used as a global validator; but you can create your own custom validator and override the Spring parameters Boot by default). Next, you can examine what you found and add the necessary logic to send an error message

@NotNull - The annotated element must not be null. Accepts any type.  
@Null - The annotated element must be null. Accepts any type.  
@NotBlank and @NotEmpty@NotBlank - The annotated element must not be null and must contain at least one non-whitespace character. Accepts CharSequence.  
@NotEmpty - The annotated element must not be null or empty. Supported types:

* CharSequence
* Collection
* Map
* Array

@NotBlank applies only to strings and checks that the string is not empty or composed entirely of spaces.  
@NotNull applies to a CharSequence, Collection, Map, or Array and checks that the object is not null. But at the same time it may be empty.  
@NotEmpty is applied to a CharSequence, Collection, Map or Array and checks that it is not null and has a size greater than 0.  
The annotation @Size(min=6) will skip a line consisting of 6 spaces and/or line breaks, but @NotBlank will not.  
@SizeThe size of the annotated element must be between the specified bounds, including the bounds themselves. null elements are considered valid.

[https://stackoverflow.com/questions/22948257/thymeleaf-not-displaying-spring-form-error-messages](https://stackoverflow.com/questions/22948257/thymeleaf-not-displaying-spring-form-error-messages)

## Error handling

Spring Boot uses the /error path to create a page that displays all global errors. This behavior can be changed by creating your own custom pages for this purpose. You need to create custom HTML pages in the src/main/resources/public/error/ directory, such as 500.html or 404.html pages. In the case of a RESTful application, Spring Boot responds in JSON format. Spring Boot also supports error handling using Spring MVC when @ControllerAdvice or @ExceptionHandler annotations are applied. You can register custom ErrorPage objects by implementing the ErrorPageRegistrar interface and declaring it as a Spring bean @ExceptionHandler annotation. Spring MVC automatically declares built-in exception resolvers and adds support in this annotation. In this case, a method with the @ExceptionHandler annotation is declared inside the controller class (it can also be used inside the @ControllerAdvice interceptor) and all exceptions are sent to the Spring Boot Web method: rest client application

Error responses should include a general HTTP status code, a message to the developer, a message to the end user (if necessary), an internal error code (corresponding to a specific internal identifier), links where developers can find additional information. For example:

    {
      "status" : 400,
      "developerMessage" : "Verbose, plain language description of the problem. Provide developers
       suggestions about how to solve their problems here",
      "userMessage" : "This is a message that can be passed along to end-users, if needed.",
      "errorCode" : "444444",
      "moreInfo" : "http://www.example.gov/developer/path/to/help/for/444444,
       http://drupal.org/node/444444",
    }

Use three simple, common response codes to indicate (1) success, (2) failure due to a client-side issue, (3) failure due to a server-side issue:  
200 - OK Error 400, invalid request internal server error 500

## Thymeleaf Templates

Template engine support. Spring Boot supports FreeMarker, Groovy Templates, Thymeleaf and Mustache. When you include the spring-bootstarter-\<template engine\> dependency, Spring Boot autoconfiguration is required to activate it and add all the necessary view resolvers and file handlers. By default, Spring Boot looks for them in the src/main/resources/templates/path directory

If you want short-hand syntax you can use following:

```
[(${variable})]
```

Escaped short-hand syntax is

```
[[${variable}]]
```

but if you change inner square brackets \[ with regular ( ones HTML is not escaped.

Example within tags:

```
<div>
    [(${variable})]
</div>
```

Staring with Thymeleaf 3.0 the html friendly tag would be:

```
<div class="mailbox-read-message" data-th-utext="*{body}">
```

```
<h1 th:text="${greeting}">Hello!</h1> 
```

In addition to substituting values into attributes, it is possible to substitute values directly into the text using two pairs of square brackets: \[\[...\]\]. The only condition is that in one of the parent elements you need to specify the th:inline attribute, which can take text, javascript and none as a value. For example:

    <body th:inline="text">
    	<h1>Hello [[${user.name}]]!</h1>
    </body> 

### References

### [https://www.youtube.com/watch?v=tVQ8w0Rk\_II 34. Thymeleaf. Spring WEB и Spring Boot 3 (Java Enterprise - полный курс) JavaGuru](https://www.youtube.com/watch?v=tVQ8w0Rk_II)

### [https://www.youtube.com/watch?v=eqzgTo-YMaU 35. Filtering, Pagination, Validation. Spring Boot 3 (Java Enterprise - полный курс)](https://www.youtube.com/watch?v=eqzgTo-YMaU)

## JTE Template Engine

[https://jte.gg/](https://jte.gg/)

jte (Java Template Engine) is a secure and lightweight template engine for Java and Kotlin. jte is designed to introduce as few new keywords as possible and builds upon existing language features, making it straightforward to reason about what a template does. The IntelliJ plugin offers full completion and refactoring support for Java parts and jte keywords.
[https://www.youtube.com/watch?v=KoWgHSWA1cc](https://www.youtube.com/watch?v=KoWgHSWA1cc) JTE: Spring Boot's New Templating Engine - Quick Start Guide  
[https://cbidici.com/posts/migrated-my-blog-application-from-thymeleaf-to-jte/18](https://cbidici.com/posts/migrated-my-blog-application-from-thymeleaf-to-jte/18) Migrated My Blog Application from Thymeleaf to JTE

## Other Template Engines

[https://www.baeldung.com/spring-template-engines](https://www.baeldung.com/spring-template-engines)
