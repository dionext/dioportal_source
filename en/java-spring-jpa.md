---
title: "Spring: JPA, Hibernate, Working with databases"
description: "Working with databases"
keywords: "JPA, Hibernate"
lang: "en"
permalink: "java-spring-jpa"
aliases:
  - "java-spring-jpa"
---

# Spring: {\#id4}JPA, Hibernate, Working with databases

## JDBC

[https://www.baeldung.com/spring-jdbc-jdbctemplate](https://www.baeldung.com/spring-jdbc-jdbctemplate) Spring JDBC

## Database first

[https://stackoverflow.com/questions/36995670/how-can-i-generate-entities-classes-from-database-using-spring-boot-and-intellij](https://stackoverflow.com/questions/36995670/how-can-i-generate-entities-classes-from-database-using-spring-boot-and-intellij)

In Eclipse: [https://www.eclipse.org/webtools/dali/docs/3.2/user\_guide/tasks006.htm](https://www.eclipse.org/webtools/dali/docs/3.2/user_guide/tasks006.htm) [https://www.eclipse.org/webtools/dali/docs/3.2/user\_guide/task\_create\_new\_project.htm#CIHHEJCJ](https://www.eclipse.org/webtools/dali/docs/3.2/user_guide/task_create_new_project.htm#CIHHEJCJ)

## Query methods

[https://docs.spring.io/spring-data/jpa/reference/jpa/query-methods.html](https://docs.spring.io/spring-data/jpa/reference/jpa/query-methods.html)

When you search entity by using list of column values as predicate, you must have to use "In" clause at the end of Column name. You can use inerrable

```java
List<Entity> findAllByEntityColumnIn(Iterable<Long> EntityColumns); 
```

## @Entity @Repository

```java
package bookmarks;

import com.fasterxml.jackson.annotation.JsonIgnore;

import javax.persistence.Entity;
import javax.persistence.GeneratedValue;
import javax.persistence.Id;
import javax.persistence.OneToMany;
import java.util.HashSet;
import java.util.Set;


@Entity
public class Account {

    @OneToMany(mappedBy = "account")
    private Set bookmarks = new HashSet<>();

    @Id
    @GeneratedValue
    private Long id;

    public Set getBookmarks() {
        return bookmarks;
    }

    public Long getId() {
        return id;
    }

    public String getPassword() {
        return password;
    }

    public String getUsername() {
        return username;
    }

    @JsonIgnore
    public String password;
    public String username;

    public Account(String name, String password) {
        this.username = name;
        this.password = password;
    }

    Account() { // jpa only
    }
}
```

### Primary key

@Id  
@GeneratedValue(strategy = GenerationType.AUTO)  
private Long id;

This can use four generation types: AUTO, IDENTITY, SEQUENCE, and TABLE. If we don't explicitly specify a value, the generation type defaults to AUTO.

### Column types

Tips: for money good choice is BigDecimal

Tips: using @Lob is not recommended - see [https://github.com/spring-projects/spring-data-jpa/issues/3139](https://github.com/spring-projects/spring-data-jpa/issues/3139)

## Jpa naming convention

[https://www.jpa-buddy.com/blog/hibernate-naming-strategies-jpa-specification-vs-springboot-opinionation/](https://www.jpa-buddy.com/blog/hibernate-naming-strategies-jpa-specification-vs-springboot-opinionation/)

## Connection pool

Configuring a Hikari Connection Pool with Spring Boot [https://www.baeldung.com/spring-boot-hikari](https://www.baeldung.com/spring-boot-hikari)

## Database migration

See:[Database migration](database-migration)
