---
title: "Docker Swarm"
description: "Using Docker Swarm"
keywords: "Docker, Swarm"
lang: "en"
permalink: "docker-swarm"
aliases:
  - "docker-swarm"
---

# Docker Swarm

## Overview

Docker Swarm provides native clustering functionality for Docker containers, which turns a group of Docker engines into a single virtual Docker engine. In Docker 1.12 and higher, Swarm mode is integrated with Docker Engine. The docker swarm CLI utility allows users to run Swarm containers, create discovery tokens, list nodes in the cluster, and more. The docker node CLI utility allows users to run various commands to manage nodes in a swarm, for example, listing the nodes in a swarm, updating nodes, and removing nodes from the swarm. Docker manages swarms using the Raft consensus algorithm. According to Raft, for an update to be performed, the majority of Swarm nodes need to agree on the update [https://en.wikipedia.org/wiki/Docker\_(software](<https://en.wikipedia.org/wiki/Docker_(software>))

Docker Swarm (Swarm mode)

Docker Swarm mode is built into the Docker Engine. Do not confuse Docker Swarm mode with [Docker Classic Swarm](https://github.com/docker/classicswarm) which is no longer actively developed.

When running Docker Engine in swarm mode, you can use docker stack deploy to deploy a complete application stack to the swarm. The deploy command accepts a stack description in the form of a [Compose file](https://docs.docker.com/compose/compose-file/compose-file-v3/).

Although the "version" is officially declared optional, when deploying a stack it must be declared explicitly

```
version: "3.8"
```

Note: When specifying the Compose file version to use, make sure to specify both the major and minor numbers. If no minor version is given, 0 is used by default and not the latest minor version. As a result, features added in later versions will not be supported. For example:

## Commands

[https://docs.docker.com/engine/swarm/swarm-mode/](https://docs.docker.com/engine/swarm/swarm-mode/)

```bash
docker swarm init --advertise-addr 192.168.1.99
```

Result:

```bash
Swarm initialized: current node (n19e4ri7bophj51p7celk2za0) is now a manager.
To add a worker to this swarm, run the following command:
docker swarm join 
--token SWMTKN-1-5o6zfqqw9x6zadx8nfbkbngku76ko57wy5fhfzflje4qr5mn9o-4759yfe1rd0qfxc1azar111fu 192.168.1.99:2377

```

```bash
docker swarm join-token worker
```

Information:

```
docker info
```

```
docker node ls
```

DRAIN availability prevents a node from receiving new tasks from the swarm manager. It also means the manager stops tasks running on the node and launches replica tasks on a node with ACTIVE availability.

docker node update --availability drain \<NODE-ID\>  
docker node update --availability active \<NODE-ID\>

```
docker node update --availability drain worker1
```

About nodes [https://docs.docker.com/engine/swarm/how-swarm-mode-works/nodes/](https://docs.docker.com/engine/swarm/how-swarm-mode-works/nodes/)

Run the command on a node to remove it from the swarm.

```bash
docker swarm leave
```

Labels:

```bash
docker node update --label-add DC=east worker_node2
```

Working with services

[https://docs.docker.com/engine/swarm/services/](https://docs.docker.com/engine/swarm/services/)

```
docker service create --replicas 3 --name redis --update-delay 10s redis:3.0.6
```

```
docker service ls 
```

```bash

docker service inspect --pretty <SERVICE-ID>
```

Run docker service ps \<SERVICE-ID\> to see which nodes are running the service

Remove service:

```bash

docker service rm <SERVICE-ID> 
```

Use the --publish flag to publish a port when you create a service. target is used to specify the port inside the container, and published is used to specify the port to bind on the routing mesh. If you leave off the published port, a random high-numbered port is bound for each service task. You need to inspect the task to determine the port.

```
$ docker service create \
  --name <SERVICE-NAME> \
  --publish published=<PUBLISHED-PORT>,target=<CONTAINER-PORT> \
  <IMAGE>
```

Note : The older form of this syntax is a colon-separated string, where the published port is first and the target port is second, such as -p 8080:80 . The new syntax is preferred because it is easier to read and allows more flexibility.

Update service:

```
docker service update --image redis:3.0.7 redis
```

A global service is a service that runs one task on every node. There is no pre-specified number of tasks. Each time you add a node to the swarm, the orchestrator creates a task and the scheduler assigns the task to the new node. Good candidates for global services are monitoring agents, anti-virus scanners or other types of containers that you want to run on every node in the swarm.

Conditions:

```
docker service create \
  --name my-nginx \
  --mode global \
  --constraint node.labels.region==east \
  --constraint node.labels.type!=devel \
  nginx
```

```
 deploy:
  placement: 
   constraints: 
     - node.labels.type == db 
```

## Load balancer {\#configure-an-external-load-balancer}

[https://docs.docker.com/engine/swarm/ingress/#bypass-the-routing-mesh](https://docs.docker.com/engine/swarm/ingress/#bypass-the-routing-mesh)

You can configure an external load balancer for swarm services, either in combination with the routing mesh or without using the routing mesh at all.

## Volumes

Swarm Mode itself does not do anything different with volumes, it runs any volume mount command you provide on the node where the container is running. If your volume mount is local to that node, then your data will be saved locally on that node. There is no built in functionality to move data between nodes automatically. There are some software based distributed storage solutions like GlusterFS, Rook, Ceph, and Longhorn. Many of these are focused on integration with Kubernetes, which won't help in Swarm.
Data volumes

/var/lib/docker/volumes

Data volumes are storage that exist independently of a container.

```
docker service create \
  --mount src=<VOLUME-NAME>,dst=<CONTAINER-PATH> \
  --name myservice \
  <IMAGE>
```

Bind mounts

Bind mounts are file system paths from the host where the scheduler deploys the container for the task. Docker mounts the path into the container. The file system path must exist before the swarm initializes the container for the task.

```
 docker service create \
  --mount type=bind,src=<HOST-PATH>,dst=<CONTAINER-PATH>,readonly \
  --name myservice \
  <IMAGE>
```

```
 
```

## Health Check

Often used Docker swarm health checks

* WGEThealthcheck:  
  test: wget --no-verbose --tries=1 --spider http://localhost || exit 1  
  interval: 60s  
  retries: 5  
  start\_period: 20s  
  timeout: 10s

<!-- -->

* CURL healthcheck:  
  test: curl --fail http://localhost || exit 1  
  interval: 60s  
  retries: 5  
  start\_period: 20s  
  timeout: 10s

[https://dotsandbrackets.com/docker-health-check-ru/](https://dotsandbrackets.com/docker-health-check-ru/)

## References

[https://www.youtube.com/watch?v=GgkreJfdTL8](https://www.youtube.com/watch?v=GgkreJfdTL8) Doсker Swarm (lang: ru)

[https://www.youtube.com/watch?v=XcpqfN8-2R0](https://www.youtube.com/watch?v=XcpqfN8-2R0) DevOps by Rebrain: Docker Swarm \& Gitlab
