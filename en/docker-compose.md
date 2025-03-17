---
title: "Docker Compose"
description: "Using docker compose"
keywords: "docker, compose"
lang: "en"
permalink: "docker-compose"
aliases:
  - "docker-compose"
---

# Docker Compose

## Overview

Docker Compose is a tool for defining and running multi-container Docker applications. It uses YAML files to configure the application's services and performs the creation and start-up process of all the containers with a single command. The docker-compose CLI utility allows users to run commands on multiple containers at once; for example, building images, scaling containers, running containers that were stopped, and more. Commands related to image manipulation, or user-interactive options, are not relevant in Docker Compose because they address one container. The docker-compose.yml file is used to define an application's services and includes various configuration options. For example, the build option defines configuration options such as the Dockerfile path, the command option allows one to override default Docker commands, and more. The first public beta version of Docker Compose (version 0.0.1) was released on December 21, 2013. The first production-ready version (1.0) was made available on October 16, 2014. [https://en.wikipedia.org/wiki/Docker\_(software](<https://en.wikipedia.org/wiki/Docker_(software>))

## Commands

Typically, you want docker-compose up. Use up to start or restart all the services defined in a docker-compose.yml. In the default "attached" mode, you see all the logs from all the containers. In "detached" mode (-d), Compose exits after starting the containers, but the containers continue to run in the background.

```bash
docker-compose up
```

```bash
docker-compose up -d
```

```bash
docker compose up -d
```

\--build - Build images before starting containers. To rebuild image you must use \`docker-compose build\` or \`docker-compose up --build\`

```bash
docker-compose down
```

Restart (!!!If you make changes to your docker-compose.yml configuration these changes are not reflected after running this command.)

```bash
docker-compose  restart
```

Custom file name:

```bash
docker-compose --file docker-compose.local-tests.yml up
```

```bash
docker-compose --file stack.yml restart
```

List of services

```bash
docker-compose ps
```

View logs

```bash
docker-compose logs -f
```

## Volumes

[https://docs.docker.com/storage/volumes/](https://docs.docker.com/storage/volumes/)

## Environment variables {\#title}

[https://docs.docker.com/compose/environment-variables/](https://docs.docker.com/compose/environment-variables/)

The order of precedence (highest to lowest) is as follows:

1. Set using [docker compose run -e in the CLI](https://docs.docker.com/compose/environment-variables/set-environment-variables/#set-environment-variables-with-docker-compose-run---env)
2. Substituted from your [shell](https://docs.docker.com/compose/environment-variables/set-environment-variables/#substitute-from-the-shell)
3. Set using the [environment attribute in the Compose file](https://docs.docker.com/compose/environment-variables/set-environment-variables/#use-the-environment-attribute)
4. Use of the [--env-file argument](https://docs.docker.com/compose/environment-variables/set-environment-variables/#substitute-with---env-file) in the CLI
5. Use of the [env\_file attribute](https://docs.docker.com/compose/environment-variables/set-environment-variables/#use-the-env_file-attribute) in the Compose file
6. Set using an [.env file](https://docs.docker.com/compose/environment-variables/set-environment-variables/#substitute-with-an-env-file) placed at base of your project directory
7. Set in a container image in the [ENV directive](https://docs.docker.com/engine/reference/builder/#env). Having any ARG or ENV setting in a Dockerfile evaluates only if there is no Docker Compose entry for environment, env\_file or run --env.

## Parametrise compose file

```yaml

version: '3.8'
services:
  hiki-ms-app:
    image: hiki-ms-app:latest
    volumes:
      - /mnt/disk2/sites:/mnt/sites
    ports:
      - 8080-8081:8080
    deploy:
      mode: replicated
      replicas: 1
    environment:
      SPRING_PROFILES_ACTIVE: htest
      SERVER_PORT: 8080
      MYSQL_PASSWORD: $ENV_MYSQL_PASSWORD
      MYSQL_USER: $ENV_MYSQL_USER		
```

Define a `.env` file in the same directory as `docker-compose.yml`  
` `  
`ENV_MYSQL_PASSWORD=mypassword`  
`ENV_MYSQL_USER=myuser`

[https://stackoverflow.com/questions/43544328/pass-argument-to-docker-compose](https://stackoverflow.com/questions/43544328/pass-argument-to-docker-compose) Pass argument to docker compose

[https://docs.docker.com/compose/environment-variables/env-file/](https://docs.docker.com/compose/environment-variables/env-file/) Syntax for environment files in Docker Compose

[https://docs.docker.com/compose/environment-variables/set-environment-variables/#substitute-with-an-env-file](https://docs.docker.com/compose/environment-variables/set-environment-variables/#substitute-with-an-env-file)

## Compose Deploy Specification (replicas, etc.)

[https://docs.docker.com/compose/compose-file/deploy/#replicas](https://docs.docker.com/compose/compose-file/deploy/#replicas)

## Manage sensitive data (Secrets)

(Docker Swarm Mode)

[https://docs.docker.com/compose/use-secrets/](https://docs.docker.com/compose/use-secrets/)

[https://spacelift.io/blog/docker-secrets](https://spacelift.io/blog/docker-secrets)

[https://stackoverflow.com/questions/42139605/how-do-you-manage-secret-values-with-docker-compose-v3-1](https://stackoverflow.com/questions/42139605/how-do-you-manage-secret-values-with-docker-compose-v3-1)

[https://blog.gitguardian.com/how-to-handle-secrets-in-docker/](https://blog.gitguardian.com/how-to-handle-secrets-in-docker/)

```yaml

version: '3.8'
services:
  hiki-ms-app:
    build:
      context: .
      dockerfile: Dockerfile
    image: hiki-ms-app:latest
    volumes:
      - /mnt/disk2/sites/hiking:/mnt/sites/hiking
    ports:
      - 8080:8080
    environment:
      - MYSQL_PASSWORD=/run/secrets/mysql_password
    secrets:
      - mysql_password
secrets:
  mysql_password:
    file: ./devsecrets/mysql_password
```

Note: [https://github.com/kwonghung-YIP/spring-boot-docker-secret](https://github.com/kwonghung-YIP/spring-boot-docker-secret)

#### Vault

Vault: provides secrets management, identity-based access, encrypting application data and auditing of secrets for applications, systems, and users [https://www.hashicorp.com/products/vault](https://www.hashicorp.com/products/vault)

## References

These samples focus specifically on Docker Compose:

* [Quickstart: Compose and ELK](https://github.com/docker/awesome-compose/tree/master/elasticsearch-logstash-kibana/logstash/README.md) - Shows how to use Docker Compose to set up and run ELK - Elasticsearch-Logstash-Kibana.

* [Quickstart: Compose and Django](https://github.com/docker/awesome-compose/tree/master/official-documentation-samples/django/README.md) - Shows how to use Docker Compose to set up and run a simple Django/PostgreSQL app.

* [Quickstart: Compose and Rails](https://github.com/docker/awesome-compose/tree/master/official-documentation-samples/rails/README.md) - Shows how to use Docker Compose to set up and run a Rails/PostgreSQL app.

* [Quickstart: Compose and WordPress](https://github.com/docker/awesome-compose/tree/master/official-documentation-samples/wordpress/README.md) - Shows how to use Docker Compose to set up and run WordPress in an isolated environment with Docker containers.

Awesome Compose samples [](https://docs.docker.com/compose/samples-for-compose/#awesome-compose-samples)

The Awesome Compose samples provide a starting point on how to integrate different frameworks and technologies using Docker Compose. All samples are available in the [Awesome-compose GitHub repo](https://github.com/docker/awesome-compose) and are ready to run with docker compose up.
