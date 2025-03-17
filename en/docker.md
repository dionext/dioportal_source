---
title: "Docker"
description: "Using Docker"
keywords: "Docker"
lang: "en"
permalink: "docker"
aliases:
  - "docker"
---

# Docker

## Overview

Docker is a set of platform as a service (PaaS) products that use OS-level virtualization to deliver software in packages called containers. The service has both free and premium tiers. The software that hosts the containers is called Docker Engine. It was first released in 2013 and is developed by Docker, Inc. Docker is a tool that is used to automate the deployment of applications in lightweight containers so that applications can work efficiently in different environments in isolation. [https://en.wikipedia.org/wiki/Docker\_(software](<https://en.wikipedia.org/wiki/Docker_(software>))

## Installation

### For Windows (Docker Desktop)

#### Docker Dev Environments

[https://docs.docker.com/desktop/dev-environments/](https://docs.docker.com/desktop/dev-environments/)

Dev Environments - like a docker-compose

Requirements:

* Git. Make sure add Git to your PATH if you're a Windows user.
* Visual Studio Code
* Visual Studio Code Remote Containers Extension (Dev Containers)

Install the [Dev Environments browser extension](https://github.com/docker/dev-envs-extension) for [Chrome](https://chrome.google.com/webstore/detail/docker-dev-environments/gnagpachnalcofcblcgdbofnfakdbeka) or [Firefox](https://addons.mozilla.org/en-US/firefox/addon/docker-dev-environments/) Allows you to quickly jump from a Git repository, branch or PR to a local development environment with the tools you need to test and run your workload - using Dev Environments - by adding a button to Github, Bitbucket and Gitlab, in your browser. Requires: - Docker Desktop version 4.12 or higher

compose-dev.yaml (If you have an existing project with a .docker/ folder this is automatically migrated the next time you launch. )

Examples: [https://github.com/docker/awesome-compose](https://github.com/docker/awesome-compose)

### Linux

Debian [https://docs.docker.com/install/linux/docker-ce/debian/#install-docker-ce](https://docs.docker.com/install/linux/docker-ce/debian/#install-docker-ce)

Ubuntu [https://docs.docker.com/install/linux/docker-ce/ubuntu/](https://docs.docker.com/install/linux/docker-ce/ubuntu/)

## Commands

[https://medium.com/statuscode/dockercheatsheet-9730ce03630d](https://medium.com/statuscode/dockercheatsheet-9730ce03630d)

Full information:

```bash
docker info
```

Version:

```bash
docker --version 
```

Images list

```bash
docker image ls
```

Containers (working) list

```bash
docker ps
```

All containers

```bash
docker ps -a
```

Information about container

```bash
docker inspect NAME|ID
```

### Run container

```bash
docker run  nginx
docker run --detach --publish 80:80 --name webserver nginx
docker container run -d --name web -p 8080:8080 jboss/wildfly
```

Start stopped conainer

```bash
docker start nginx
```

Stop container

```bash
docker stop nginx
```

Show log

```bash
docker container logs mariadb
```

Restart container

```bash
docker restart nginx
```

Remove container

```bash
docker container rm nginx
```

### Update to latest version

(Example: portainer application)

```
docker stop portainer 
```

```
docker rm portainer 
```

```
docker pull portainer/portainer-ce:latest 
```

```
docker run -d -p 8000:8000 -p 9443:9443 --name=portainer --restart=always -v /var/run/docker.sock:/var/run/docker.sock -v portainer_data:/data portainer/portainer-ce:latest
```

## Configuration

[https://docs.docker.com/config/containers/logging/json-file/](https://docs.docker.com/config/containers/logging/json-file/) Logging - reduce file size [https://stackoverflow.com/questions/31829587/docker-container-logs-taking-all-my-disk-space](https://stackoverflow.com/questions/31829587/docker-container-logs-taking-all-my-disk-space)

```yaml

    logging:
      driver: "json-file" #default 
      options:
        max-size: "10m" #Defaults to -1 (unlimited)
        max-file: "1" #Defaults to 1
```

To set the default log limits for all newly created containers, you can add the following in /etc/docker/daemon.json:

nano /etc/docker/daemon.json

( [https://stackoverflow.com/questions/43689271/wheres-dockers-daemon-json-missing](https://stackoverflow.com/questions/43689271/wheres-dockers-daemon-json-missing) )

    {
      "log-driver": "json-file",
      "log-opts": {"max-size": "10m", "max-file": "3"}
    }

Then reload docker with

sudo service docker restart

## Clearing

Directory /var/lib/docker/containers/container\_ID -- when using the standard logging driver, this is where event logs are saved in JSON format. Too detailed logs, as well as logs that no one reads or otherwise processes, often cause disk overflow.

The directory /var/lib/docker/overlay2 -- contains the read-write layers of containers (overlay2 is the preferred driver in most Linux distributions) . If a container stores data in its file system, then this is the directory where it will be placed.

Using the following command, you can remove all installed containers in one fell swoop and clear your disk of all read-write files created by them  
`docker container prune`

This will remove all volumes not used by at least one container [https://docs.docker.com/reference/cli/docker/volume/prune/](https://docs.docker.com/reference/cli/docker/volume/prune/)

docker volume prune --all

Full clearing

```bash
docker system prune
```

[https://stackoverflow.com/questions/46672001/is-it-safe-to-clean-docker-overlay2](https://stackoverflow.com/questions/46672001/is-it-safe-to-clean-docker-overlay2)

Docker uses /var/lib/docker to store images, containers, and local named volumes. Removing this may result in data loss and possible engine stoppage. The overlay2 subdirectory specifically contains different filesystem levels for images and containers.  
To clean up unused containers and images, see docker system prune. There are also options for deleting volumes and even tagged images, but these are not enabled by default due to the possibility of data loss:

```bash

docker system prune -a && docker volume prune 
```

```
 
```

Below is the command to clear all the log files stored on the host machine:

```
$ truncate -s 0 /var/lib/docker/containers/*/*-json.log 
```

```
 
```

```
 
```

## Dockerfile for spring boot application

[https://www.baeldung.com/java-dockerize-app](https://www.baeldung.com/java-dockerize-app)

    FROM bellsoft/liberica-openjdk-alpine-musl:21.0.2
    COPY ./target/hiki-ms-app-0.0.1-SNAPSHOT.jar .
    CMD ["java","-jar","hiki-ms-app-0.0.1-SNAPSHOT.jar"]

Comparation of different images

|---------------------------------------------------|-------|
| FROM bellsoft/liberica-openjdk-alpine-musl:21.0.2 | 187MB |
| FROM amazoncorretto:21.0.2                        | 568MB |
| FROM amazoncorretto:21.0.2-alpine                 | 393MB |

Future tips:

* Don't Put Fat Jars in Docker Images [https://phauer.com/2019/no-fat-jar-in-docker-image/](https://phauer.com/2019/no-fat-jar-in-docker-image/)
* Spring Boot Docker Best Practices [https://mydeveloperplanet.com/2022/12/14/spring-boot-docker-best-practices/](https://mydeveloperplanet.com/2022/12/14/spring-boot-docker-best-practices/)

## Docker compose

See [Docker compose](docker-compose)

## Docker Swarm

See [Docker Swarm](docker-swarm)

## UI

### Portainer (CE - community edition)

{#id28}Deployment Single

[https://docs.portainer.io/start/install-ce/server/docker/linux](https://docs.portainer.io/start/install-ce/server/docker/linux)

{#id102}Deployment Deploymet Swarm

[https://docs.portainer.io/start/install-ce/server/swarm/linux](https://docs.portainer.io/start/install-ce/server/swarm/linux)

Restrictions:  
Docker is running as root. Portainer with rootless Docker has some limitations, and requires additional configuration.
You are running a single manager node in your swarm. If you have more than one, please [read this knowledge base article](https://portal.portainer.io/knowledge/how-can-i-ensure-portainers-configuration-is-retained)

curl -L https://downloads.portainer.io/ce2-18/portainer-agent-stack.yml -o portainer-agent-stack.yml  
docker stack deploy -c portainer-agent-stack.yml portainer

[https://localhost:9443](https://localhost:9443)

Upgrade: [https://docs.portainer.io/start/upgrade/swarm](https://docs.portainer.io/start/upgrade/swarm)

## References

[https://labs.play-with-docker.com](https://labs.play-with-docker.com/) Play with Docker (PWD) is a project hacked by Marcos Liljedhal and Jonathan Leibiusky and sponsored by Docker Inc. PWD is a Docker playground which allows users to run Docker commands in a matter of seconds. It gives the experience of having a free Alpine Linux Virtual Machine in browser, where you can build and run Docker containers and even create clusters in Docker Swarm Mode. Under the hood Docker-in-Docker (DinD) is used to give the effect of multiple VMs/PCs. In addition to the playground, PWD also includes a training site composed of a large set of Docker labs and quizzes from beginner to advanced level available at training.play-with-docker.com.

[https://github.com/docker/awesome-compose](https://github.com/docker/awesome-compose) Examples
