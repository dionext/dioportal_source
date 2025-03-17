---
title: "Database migration"
description: ""
keywords: ""
lang: "en"
permalink: "database-migration"
aliases:
  - "database-migration"
---

# Database migration

## Overview

See [https://documentation.red-gate.com/fd/why-database-migrations-184127574.html](https://documentation.red-gate.com/fd/why-database-migrations-184127574.html)

## Hibernate auto-ddl

spring.jpa.hibernate.ddl-auto=update

You can set spring.jpa.hibernate.ddl-auto explicitly and the standard Hibernate property values are none, validate, update, create, and create-drop. Spring Boot chooses a default value for you based on whether it thinks your database is embedded. It defaults to create-drop if no schema manager has been detected or none in all other cases. An embedded database is detected by looking at the Connection type. hsqldb, h2, and derby are embedded, and others are not. Be careful when switching from in-memory to a 'real' database that you do not make assumptions about the existence of the tables and data in the new platform. You either have to set ddl-auto explicitly or use one of the other mechanisms to initialize the database.

In addition, a file named import.sql in the root of the classpath is executed on startup if Hibernate creates the schema from scratch (that is, if the ddl-auto property is set to create or create-drop). This can be useful for demos and for testing if you are careful but is probably not something you want to be on the classpath in production. It is a Hibernate feature (and has nothing to do with Spring).

Spring Boot can automatically create the schema (DDL scripts) of your DataSource and initialize it (DML scripts). It loads SQL from the standard root classpath locations: schema.sql and data.sql, respectively. In addition, Spring Boot processes the schema-${platform}.sql and data-${platform}.sql files (if present), where platform is the value of spring.datasource.platform. This allows you to switch to database-specific scripts if necessary. For example, you might choose to set it to the vendor name of the database (hsqldb, h2, oracle, mysql, postgresql, and so on).

Spring Boot automatically creates the schema of an embedded DataSource. This behavior can be customized by using the spring.datasource.initialization-mode property (and it can also be always or never).

By default, Spring Boot enables the fail-fast feature of the Spring JDBC initializer, so, if the scripts cause exceptions, the application fails to start. You can tune that behavior by setting spring.datasource.continue-on-error.

|---|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|   |
|   | In a JPA-based app, you can choose to let Hibernate create the schema or use schema.sql, but you cannot do both. Make sure to disable spring.jpa.hibernate.ddl-auto if you use schema.sql. |

## Flyway

[https://www.baeldung.com/database-migrations-with-flyway](https://www.baeldung.com/database-migrations-with-flyway) Database Migrations with Flyway

```
<!-- for database migration -->
<dependency>
    <groupId>org.flywaydb</groupId>
    <artifactId>flyway-maven-plugin</artifactId>
    <version>9.22.3</version><!-- do not use higher version until bug will be resolved  -->
</dependency>
<!-- for database migration mysql -->
<dependency>
    <groupId>org.flywaydb</groupId>
    <artifactId>flyway-mysql</artifactId>
    <version>9.22.3</version><!-- do not use higher version until bug will be resolved  -->
</dependency>
```

```
 
```

Property:

spring:

flyway:

baseline-on-migrate: true

The migrations are scripts in the form V\<VERSION\>\_\_\<NAME\>.sql (with \<VERSION\> an underscore-separated version, such as '1' or '2\_1'). By default, they live in a folder called classpath:db/migration, but you can modify that location by setting spring.flyway.locations. You can also add a special {vendor} placeholder to use vendor-specific scripts. Assume the following:

```
spring.flyway.locations=db/migration/{vendor}
```

Rather than using db/migration, the preceding configuration sets the folder to use according to the type of the database (such as db/migration/mysql for MySQL).

Tips: How to use Flyway when working with feature branches [https://stackoverflow.com/questions/9497035/how-to-use-flyway-when-working-with-feature-branches](https://stackoverflow.com/questions/9497035/how-to-use-flyway-when-working-with-feature-branches) (For example, using a pattern such as yyyyMMddHHmmssSSS the migrations above now look like... 1.0.0.20130704144750766\_\_add\_customers\_table.sql )

Tips: Spring Boot: Hibernate and Flyway boot order [https://stackoverflow.com/questions/37097876/spring-boot-hibernate-and-flyway-boot-order](https://stackoverflow.com/questions/37097876/spring-boot-hibernate-and-flyway-boot-order)

Java migration example

```java
package db.migration;  

public class V2__JavaMigration extends BaseJavaMigration { 
  @Override 
  public void migrate(Context context) throws Exception {
    try (PreparedStatement statement = Context 
         .getConnection() 
         .prepareStatement("INSERT INTO test_user (name) VALUES ('Obelix')")) { 
      statement.execute(); 
    } 
  } 
} 
```

## Liquibase

## Liquibase vs Flyway - comparation

[https://habr.com/ru/companies/spring\_aio/articles/827976/](https://habr.com/ru/companies/spring_aio/articles/827976/) (ru lang)
