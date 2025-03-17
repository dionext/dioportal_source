---
title: "Zero Downtime deployments"
description: ""
keywords: " blue–green, deployments"
lang: "en"
permalink: "devops-zero-downtime"
aliases:
  - "devops-zero-downtime"
---

# Zero Downtime deployments {\#besshovnyy-deployment}

In blue--green deployments, two servers are maintained: a "blue" server and a "green" server. At any given time, only one server is handling requests (e.g., being pointed to by the DNS). For example, public requests may be routed to the blue server, making it the production server and the green server the staging server, which can only be accessed on a private network. Changes are installed on the non-live server, which is then tested through the private network to verify the changes work as expected. Once verified, the non-live server is swapped with the live server, effectively making the deployed changes live

Best simple solution

[https://www.tines.com/blog/simple-zero-downtime-deploys-with-nginx-and-docker-compose](https://www.tines.com/blog/simple-zero-downtime-deploys-with-nginx-and-docker-compose)

Other references

[https://habr.com/ru/articles/516230/](https://habr.com/ru/articles/516230/)

[https://habr.com/ru/companies/akbarsdigital/articles/668478/](https://habr.com/ru/companies/akbarsdigital/articles/668478/)

[https://www.maxcountryman.com/articles/zero-downtime-deployments-with-docker-compose](https://www.maxcountryman.com/articles/zero-downtime-deployments-with-docker-compose)

[https://github.com/Wowu/docker-rollout](https://github.com/Wowu/docker-rollout)

[https://linuxhandbook.com/update-docker-container-zero-downtime/](https://linuxhandbook.com/update-docker-container-zero-downtime/)

#### Communication from different docker-compose stacks

[https://www.baeldung.com/ops/docker-compose-communication](https://www.baeldung.com/ops/docker-compose-communication)

services:  
my\_app:  
image: "web-app:latest"  
container\_name: web-app  
ports:

- "8080:8080"  
  networks:
- my-app

networks:  
my-app:  
name: redis\_network  
external: true
