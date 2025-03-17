---
title: "Apache Kafka"
description: ""
keywords: ""
lang: "en"
permalink: "kafka"
aliases:
  - "kafka"
---


# Apache Kafka

## Overview

Apache Kafka is a distributed event store and stream-processing platform. It is an open-source system developed by the Apache Software Foundation written in Java and Scala. The project aims to provide a unified, high-throughput, low-latency platform for handling real-time data feeds. Kafka can connect to external systems (for data import/export) via Kafka Connect, and provides the Kafka Streams libraries for stream processing applications. Kafka uses a binary TCP-based protocol that is optimized for efficiency and relies on a "message set" abstraction that naturally groups messages together to reduce the overhead of the network roundtrip. This "leads to larger network packets, larger sequential disk operations, contiguous memory blocks \[...\] which allows Kafka to turn a bursty stream of random message writes into linear writes." [https://en.wikipedia.org/wiki/Apache\_Kafka](https://en.wikipedia.org/wiki/Apache_Kafka)

## Installation

## Sending Messages

[https://docs.spring.io/spring-kafka/reference/kafka/sending-messages.html](https://docs.spring.io/spring-kafka/reference/kafka/sending-messages.html)

## Receiving messages

## Working with headers

Kafka headers represent key-value pairs attached to Kafka messages, offering a means to include supplementary metadata alongside the primary message content.

Send example [https://stackoverflow.com/questions/67218510/how-to-set-message-headers-using-kafkatemplate](https://stackoverflow.com/questions/67218510/how-to-set-message-headers-using-kafkatemplate)

Using custom Kafka headers for advanced message processing [https://www.tinybird.co/blog-posts/using-custom-kafka-headers](https://www.tinybird.co/blog-posts/using-custom-kafka-headers)

View Kafka Headers in Java [https://www.baeldung.com/java-kafka-view-headers](https://www.baeldung.com/java-kafka-view-headers)

## Telemetry

Kafka Tracing with Spring Boot and Open Telemetry [https://piotrminkowski.com/2023/11/15/kafka-tracing-with-spring-boot-and-open-telemetry/](https://piotrminkowski.com/2023/11/15/kafka-tracing-with-spring-boot-and-open-telemetry/)

[http://192.168.1.149:16686/search](http://192.168.1.149:16686/search) Jaeger UI

## References

[https://itnext.io/kafka-cluster-without-zookeeper-ca40d5f22304](https://itnext.io/kafka-cluster-without-zookeeper-ca40d5f22304) Kafka cluster without Zookeeper
