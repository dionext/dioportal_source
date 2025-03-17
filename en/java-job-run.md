---
title: "Running Job in Java"
description: ""
keywords: ""
lang: "en"
permalink: "java-job-run"
aliases:
  - "java-job-run"
---

# Running Job in Java

## Simple Threads

@Async

Note: Creating a local instance of the GitHubLookupService class does NOT allow the findUser method to run asynchronously. It must be created inside a @Configuration class or picked up by @ComponentScan.

## Spring Batch

[https://spring.io/projects/spring-batch](https://spring.io/projects/spring-batch)  
A lightweight, comprehensive batch framework designed to enable the development of robust batch applications vital for the daily operations of enterprise systems. Spring Batch provides reusable functions that are essential in processing large volumes of records, including logging/tracing, transaction management, job processing statistics, job restart, skip, and resource management. It also provides more advanced technical services and features that will enable extremely high-volume and high performance batch jobs through optimization and partitioning techniques. Simple as well as complex, high-volume batch jobs can leverage the framework in a highly scalable manner to process significant volumes of information.

## Quartz Scheduler

[https://www.quartz-scheduler.org/](https://www.quartz-scheduler.org/)

Quartz is a richly featured, open source job scheduling library that can be integrated within virtually any Java application - from the smallest stand-alone application to the largest e-commerce system. Quartz can be used to create simple or complex schedules for executing tens, hundreds, or even tens-of-thousands of jobs; jobs whose tasks are defined as standard Java components that may execute virtually anything you may program them to do. The Quartz Scheduler includes many enterprise-class features, such as support for JTA transactions and clustering.

## DB Scheduler

Another good alternative to Quartz is db-scheduler. The library was originally designed to be a simpler alternative to Quartz. This design reduces the number of required tables to one (compared to Quartz's 11 tables!) and provides a much simpler API.

## JobRunr

[https://www.jobrunr.io/](https://www.jobrunr.io/)

Comparison with others

[https://www.jobrunr.io/en/blog/2024-10-31-task-schedulers-java-modern-alternatives-to-quartz/](https://www.jobrunr.io/en/blog/2024-10-31-task-schedulers-java-modern-alternatives-to-quartz/) Task schedulers in Java: modern alternatives to Quartz Scheduler

[https://www.jobrunr.io/en/blog/2023-02-20-moving-from-quartz-scheduler-to-jobrunr/](https://www.jobrunr.io/en/blog/2023-02-20-moving-from-quartz-scheduler-to-jobrunr/) How to move from Quartz to JobRunr

### Tips

Important: the jobrunr-spring-boot-starter is deprecated since JobRunr v6, please use jobrunr-spring-boot-2-starter or jobrunr-spring-boot-3-starter instead!

### References

[https://www.baeldung.com/java-jobrunr-spring](https://www.baeldung.com/java-jobrunr-spring) Background Jobs in Spring with JobRunr
