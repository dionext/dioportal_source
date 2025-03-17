---
title: "Spring: Advanced"
description: ""
keywords: ""
lang: "en"
permalink: "java-spring-advanced"
aliases:
  - "java-spring-advanced"
---

## Spring: Advanced

## I18n

[https://www.baeldung.com/spring-boot-internationalization](https://www.baeldung.com/spring-boot-internationalization)

[https://lokalise.com/blog/spring-boot-internationalization/](https://lokalise.com/blog/spring-boot-internationalization/)

[https://simplelocalize.io/blog/posts/spring-boot-simple-internationalization/#localized-texts](https://simplelocalize.io/blog/posts/spring-boot-simple-internationalization/#localized-texts)

[https://stackoverflow.com/questions/3221632/locales-as-part-of-the-url-in-spring-mvc](https://stackoverflow.com/questions/3221632/locales-as-part-of-the-url-in-spring-mvc)

[https://phrase.com/blog/posts/database-stored-messages-for-i18n-in-spring-boot/](https://phrase.com/blog/posts/database-stored-messages-for-i18n-in-spring-boot/)

[https://stackoverflow.com/questions/59410685/load-messages-files-in-messagesouce-from-imported-jar](https://stackoverflow.com/questions/59410685/load-messages-files-in-messagesouce-from-imported-jar) проблема библиотек

\<h1 th:text="#{greeting}"\>\</h1\>

### Quick Thymeleaf for i18n guide: {\#quick-thymeleaf-guide}

* th:attr="lang=${lang}" - sets the language of the document
* th:utext="#{title(${userName})}" - gets a message with title key and inserts the value of the userName variable
* th:text="#{message}" - gets a message with message key
* th:href="${url}" - inserts a value of the url variable
* You can use th:utext instead of th:text to avoid escaping HTML characters.
* You can use th:attr to set the lang attribute on the html tag.

```
Locale.setDefault(Locale.ENGLISH);
```

## Monitoring

@Timed Annotation Using Metrics and AspectJ [https://www.baeldung.com/timed-metrics-aspectj](https://www.baeldung.com/timed-metrics-aspectj)

[https://docs.spring.io/spring-boot/docs/2.1.9.RELEASE/reference/html/production-ready-metrics.html#production-ready-metrics-export-prometheus](https://docs.spring.io/spring-boot/docs/2.1.9.RELEASE/reference/html/production-ready-metrics.html#production-ready-metrics-export-prometheus)

## Docker compose support

[https://docs.spring.io/spring-boot/how-to/docker-compose.html](https://docs.spring.io/spring-boot/how-to/docker-compose.html)

[https://spring.io/blog/2023/06/21/docker-compose-support-in-spring-boot-3-1](https://spring.io/blog/2023/06/21/docker-compose-support-in-spring-boot-3-1)

[https://www.baeldung.com/docker-compose-support-spring-boot](https://www.baeldung.com/docker-compose-support-spring-boot)

With Spring Boot 3.1, this gets a lot easier for you. You can continue to use random host ports but you don't have to specify configuration properties and you don't have to duplicate usernames, passwords, and so on in multiple places. You also don't have to remember to run docker compose up before starting the application.

Spring Boot 3.1 will detect that there's a Docker Compose file present, and will run docker compose up for you before connecting to the services. If the services are already running, it will detect that, too, and will use them. It will also run docker compose stop when the application shuts down - gone are the days of lingering Docker containers eating your precious memory.

The images started by Docker Compose are automatically detected and used to create ConnectionDetails beans pointing to the services. That means you don't have to put properties in your configuration, you don't have to remember how to construct PostgreSQL JDBC URLs, and so on.

With Spring Boot 3.1, all you need to do is to provide the compose.yaml file and let Spring Boot figure out the rest. It just works!

[https://docs.spring.io/spring-ai/reference/api/docker-compose.html](https://docs.spring.io/spring-ai/reference/api/docker-compose.html) Docker compose support fo Spring AI

## Bootify

[https://bootify.io/](https://bootify.io/) With Bootify you can create your custom database model with REST API and frontend online, explore the generated code and download your runnable Spring Boot application.

[https://www.baeldung.com/spring-boot-prototyping-bootify](https://www.baeldung.com/spring-boot-prototyping-bootify) Rapid Spring Boot Prototyping with Bootify

## Some incompatible cases

[https://youtrack.jetbrains.com/issue/IDEA-332869/Incompatible-Lombok-version-leads-to-error-NoSuchFieldError-com.sun.tools.javac.tree.JCTree-qualid-during-project-compilation](https://youtrack.jetbrains.com/issue/IDEA-332869/Incompatible-Lombok-version-leads-to-error-NoSuchFieldError-com.sun.tools.javac.tree.JCTree-qualid-during-project-compilation)

Upgrade Lombok to the compatible version. JDK21 - Lombok 1.18.30 JDK22 - Lombok 1.18.32
