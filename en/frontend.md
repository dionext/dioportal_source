---
title: "Frontend"
description: ""
keywords: ""
lang: "en"
permalink: "frontend"
aliases:
  - "frontend"
---

# Frontend

## Overview

[https://www.youtube.com/watch?v=CdtyvO9jg8E](https://www.youtube.com/watch?v=CdtyvO9jg8E) A Spring Developers Guide to Navigating the Frontend Landscape by Dan Vega @ Spring I/O 2024

## React

See: [React](frontend-react)

## Next.js

[https://en.wikipedia.org/wiki/Next.js](https://en.wikipedia.org/wiki/Next.js)

Next.js is an open-source web development framework created by the private company Vercel providing React-based web applications with server-side rendering and static rendering. React documentation mentions Next.js among "Recommended Toolchains" advising it to developers when "building a server-rendered website with Node.js".\[6\] Where traditional React apps can only render their content in the client-side browser, Next.js extends this functionality to include applications rendered on the server-side.

[https://nextjs.org/](https://nextjs.org/)

[https://www.youtube.com/watch?v=EbIps-suESk](https://www.youtube.com/watch?v=EbIps-suESk) Spring boot + nextjs starter kit | Auth, Oauth2, Emails, S3 and more. Step by step guide

есть мнение , что Next.js слишком зарекламрован, переусложнен, особенно для статичных сайтов - альтернатива Astro - статический генератор сайтов, ориентированный на производительность. [https://habr.com/ru/articles/746380/](https://habr.com/ru/articles/746380/)

## Astro

[https://astro.build/](https://astro.build/)

Astro is the web framework for building content-driven websites like blogs, marketing, and e-commerce. Astro is best-known for pioneering a new frontend architecture to reduce JavaScript overhead and complexity compared to other frameworks. If you need a website that loads fast and has great SEO, then Astro is for you.

[https://habr.com/ru/articles/746380/](https://habr.com/ru/articles/746380/)

## Vue

[https://en.wikipedia.org/wiki/Vue.js](https://en.wikipedia.org/wiki/Vue.js) Vue.js (commonly referred to as Vue; pronounced "view"\[6\]) is an open-source model--view--viewmodel front end JavaScript framework for building user interfaces and single-page applications.\[12\] It was created by Evan You and is maintained by him and the rest of the active core team members.\[13\]

Nuxt.js

Nuxt is a free and open source JavaScript library based on Vue.js, Nitro, and Vite. Nuxt is inspired by Next.js,\[4\] which is a framework of similar purpose, based on React.js. The framework is advertised as a "Meta-framework for universal applications". The term universal is used here with the meaning that the goal of the framework is to enable users to create web views in JavaScript utilizing the Vue.js single file component system and that can function both as in-browser single page application (SPA) views as well as server-rendered web views which are then (after server rendering) "rehydrated" to full SPA functionality.\[5\]\[6\] Additionally, the framework enables users to have the content, or parts of it, fully pre-rendered on the server and served in the manner of static site generators. The benefits of this approach are, among others, reduced time to interactivity and improved SEO compared to SPAs, due to the fact that full contents of each page are being served by the web server before any client-side JavaScript is executed. Put alternatively, one can maintain both the benefits of traditional server-side rendered HTML pages, and improved interactivity and advanced user interface of SPAs. The core benefit of the Nuxt framework itself is that it makes the configuration and setup of such applications simplified and seamless to the application developer, who can simply develop UI portions of the application as if it were a more common Vue.js single file application.

## Vaadin, Hilla

[https://en.wikipedia.org/wiki/Vaadin](https://en.wikipedia.org/wiki/Vaadin)

Vaadin (Finnish pronunciation: \[ˈʋɑːdin\]) is an open-source web application development platform for Java. Vaadin includes a set of Web Components, a Java web framework, and a set of tools that enable developers to implement modern web graphical user interfaces (GUI) using the Java programming language only (instead of HTML and JavaScript), TypeScript only, or a combination of both.

[https://vaadin.com/blog/comparing-frontend-frameworks-for-spring-boot-react-angular-and-vaadin-jhipster](https://vaadin.com/blog/comparing-frontend-frameworks-for-spring-boot-react-angular-and-vaadin-jhipster) The best frontend frameworks to use with Spring Boot in 2024 (Compare 4 popular frontends for Spring Boot)

* [Vaadin Flow](https://vaadin.com/flow) - Build web apps 100% in Java without writing any HTML or JavaScript using Vaadin Flow.
* [Hilla](https://vaadin.com/hilla) - Hilla ([previously Vaadin Fusion](https://vaadin.com/blog/renaming-fusion)) is the modern web framework for Java. It Integrates a Spring Boot Java backend with a reactive TypeScript frontend.

## JHipster

[https://en.wikipedia.org/wiki/JHipster](https://en.wikipedia.org/wiki/JHipster) JHipster is a free and open-source application generator used to quickly develop modern web applications and Microservices using Angular or React (JavaScript library) and the Spring Framework. JHipster provides tools to generate a project with a Java stack on the server side (using Spring Boot) and a responsive Web front-end on the client side (with Angular/React and Bootstrap). It can also create microservice stack with support for Netflix OSS, Docker and Kubernetes.  
Technology stack{#Technology\_stack}

On the client side:

* [HTML5 Boilerplate](https://en.wikipedia.org/wiki/HTML5_Boilerplate "HTML5 Boilerplate")
* [Twitter Bootstrap](<https://en.wikipedia.org/wiki/Bootstrap_(front-end_framework)> "Bootstrap (front-end framework)")
* [AngularJS](https://en.wikipedia.org/wiki/AngularJS "AngularJS")
* [Angular](<https://en.wikipedia.org/wiki/Angular_(application_platform)> "Angular (application platform)") 2+
* [React](<https://en.wikipedia.org/wiki/React_(JavaScript_library)> "React (JavaScript library)")
* Full internationalization support with Angular Translate
* Optional Compass / Sass support for CSS design
* Optional WebSocket support with Spring Websocket

On the server side:

* Spring Boot
* Spring Security (including Social Logins)
* Spring MVC REST + Jackson
* Monitoring with Metrics
* Optional WebSocket support with Spring Websocket
* Spring Data JPA + Bean Validation
* Database updates with Liquibase
* [Elasticsearch](https://en.wikipedia.org/wiki/Elasticsearch "Elasticsearch") support
* [MongoDB](https://en.wikipedia.org/wiki/MongoDB "MongoDB") support
* [Cassandra](https://en.wikipedia.org/wiki/Apache_Cassandra "Apache Cassandra") support
* [Neo4j](https://en.wikipedia.org/wiki/Neo4j "Neo4j") support

Out-of-the-box auto-configured tooling:

* Yeoman
* Webpack or Gulp.js
* BrowserSync
* Maven or Gradle
* Editor for Datamodeling (visual and textual)

JHipster is a project generator for Spring Boot web projects. It is a guided walk-through for selecting a backend and frontend, and deciding which libraries and configurations you want to use; and then JHipster will generate those into your project. It automates the decision process and generates all the required boilerplate and setup code. However, JHipster is not a full-stack framework and you are still the one who needs to maintain everything going forward.

[https://www.jhipster.tech/](https://www.jhipster.tech/) JHipster is a development platform to quickly generate, develop, and deploy modern web applications \& microservice architectures.

[https://www.youtube.com/watch?v=IfyjKCt6YHE](https://www.youtube.com/watch?v=IfyjKCt6YHE) [https://github.com/mraible/jhipster8-demo](https://github.com/mraible/jhipster8-demo) Get Started with JHipster 8 (official)

Critics [https://jpoint.ru/archive/2024/talks/1a8201bdc17b4a40b586fb61aea5710e/](https://jpoint.ru/archive/2024/talks/1a8201bdc17b4a40b586fb61aea5710e/) JHipster: думали, распаковка, оказалось - вскрытие

## Express.js

[https://en.wikipedia.org/wiki/Express.js](https://en.wikipedia.org/wiki/Express.js) Express.js, or simply Express, is a back end web application framework for building RESTful APIs with Node.js, released as free and open-source software under the MIT License. It is designed for building web applications and APIs.\[2\] It has been called the de facto standard server framework for Node.js.\[3\]

See [https://www.youtube.com/watch?v=ocMOZpuAMw4](https://www.youtube.com/watch?v=ocMOZpuAMw4) Cursor Tutorial for Beginners (AI Code Editor)

## HTMX

See: [HTMX](frontend-htmx)

## Approaches

### LocalFirst

[https://www.inkandswitch.com/local-first/](https://www.inkandswitch.com/local-first/)

[https://njoseph.me/mediawiki/LocalFirst](https://njoseph.me/mediawiki/LocalFirst)

## CSRF

[https://en.wikipedia.org/wiki/Cross-site\_request\_forgery](https://en.wikipedia.org/wiki/Cross-site_request_forgery)

Cross-site request forgery, also known as one-click attack or session riding and abbreviated as CSRF (sometimes pronounced sea-surf\[1\]) or XSRF, is a type of malicious exploit of a website or web application where unauthorized commands are submitted from a user that the web application trusts.\[2\] There are many ways in which a malicious website can transmit such commands; specially-crafted image tags, hidden forms, and JavaScript fetch or XMLHttpRequests, for example, can all work without the user's interaction or even knowledge. Unlike cross-site scripting (XSS), which exploits the trust a user has for a particular site, CSRF exploits the trust that a site has in a user's browser.\[3\] In a CSRF attack, an innocent end user is tricked by an attacker into submitting a web request that they did not intend. This may cause actions to be performed on the website that can include inadvertent client or server data leakage, change of session state, or manipulation of an end user's account. The term "CSRF" is also used as an abbreviation in defences against CSRF attacks, such as techniques that use header data, form data, or cookies, to test for and prevent such attacks.

[https://en.wikipedia.org/wiki/Same-origin\_policy](https://en.wikipedia.org/wiki/Same-origin_policy) In computing, the same-origin policy (SOP) is a concept in the web-app application security model. Under the policy, a web browser permits scripts contained in a first web page to access data in a second web page, but only if both web pages have the same origin. An origin is defined as a combination of URI scheme, host name, and port number. This policy prevents a malicious script on one page from obtaining access to sensitive data on another web page through that page's DOM.

Modern browsers will permit a script to connect to a WebSocket address without applying the same-origin policy. However, they recognize when a WebSocket URI is used, and insert an Origin: header into the request that indicates the origin of the script requesting the connection. To ensure cross-site security, the WebSocket server must compare the header data against an allowlist of origins permitted to receive a reply.

[https://en.wikipedia.org/wiki/Cross-origin\_resource\_sharing](https://en.wikipedia.org/wiki/Cross-origin_resource_sharing)

[https://www.baeldung.com/spring-cors](https://www.baeldung.com/spring-cors) CORS with Spring

[https://spring.io/guides/gs/rest-service-cors](https://spring.io/guides/gs/rest-service-cors) Enabling Cross Origin Requests for a RESTful Web Service

[https://javarush.com/quests/lectures/questspringsecurity.level01.lecture02](https://javarush.com/quests/lectures/questspringsecurity.level01.lecture02) (ru) Cross-Site Request Forgery (CSRF)

## References

[https://www.youtube.com/watch?v=-57r5AARRgY](https://www.youtube.com/watch?v=-57r5AARRgY) Будущее фронтендовых приложений. От запросов, к движкам синхронизации / Андрей Ситник / #22
