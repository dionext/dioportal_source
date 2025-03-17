---
title: "Nginx"
description: ""
keywords: ""
lang: "en"
permalink: "nginx"
aliases:
  - "nginx"
---

# Nginx

## Overview

[https://www.nginx.com/](https://www.nginx.com/)

Nginx is a web server that can also be used as a reverse proxy, load balancer, mail proxy and HTTP cache. The software was created by Russian developer Igor Sysoev and publicly released in 2004. Nginx is free and open-source software, released under the terms of the 2-clause BSD license. A large fraction of web servers use Nginx, often as a load balancer. A company of the same name was founded in 2011 to provide support and NGINX Plus paid software. [https://en.wikipedia.org/wiki/Nginx](https://en.wikipedia.org/wiki/Nginx)

There are various architectures for constructing web servers for transmitting data via the HTTP protocol. Among them, architectures using Nginx as an external (caching, front-end) server occupy a worthy place in terms of performance. Nginx is often used in conjunction with an internal (back-end) server to process dynamic data, which is then sent to Nginx as static data without the participation of the internal server.

## Installing

[https://docs.nginx.com/nginx/admin-guide/installing-nginx/installing-nginx-open-source/](https://docs.nginx.com/nginx/admin-guide/installing-nginx/installing-nginx-open-source/)

On Docker

```bash
docker run --name mynginx1 -p 80:80 -d nginx
```

More examples

```bash
docker run -d -p 80:80 --restart always --name nginx-prod -v /mnt/devops/nginx/config/nginx.conf:/etc/nginx/nginx.conf:ro -v /mnt/devops/nginx/html:/etc/nginx/html:ro nginx
```

```bash
docker run -d -p 80:80 --restart always --name nginx-prod -v /mnt/devops/nginx/config/nginx.conf:/etc/nginx/nginx.conf:ro -v /mnt/pve_sdb1_storage/sites/hiking/output:/etc/nginx/html:ro nginx
```

Example with docker-compose

```yaml
version: '3.8'
services:
  nginx: 
    image: nginx:1.25.3
    container_name: nginx-prod
    restart: always
    volumes:
      - /mnt/devops/nginx/certs:/etc/nginx/certs
      - /mnt/devops/nginx/config/nginx.conf:/etc/nginx/nginx.conf:ro
      - /mnt/disk2/sites:/etc/nginx/html:ro
    ports:
      - 80:80
      - 443:443
    #command: "/bin/sh -c 'while :; do sleep 6h & wait $${!}; nginx -s reload; done & nginx -g \"daemon off;\"'"
    networks:
      - nginx_network
networks:
  nginx_network:
    name: mainnetwork
    external: true
```

### Windows version

[https://nginx.org/ru/docs/windows.html](https://nginx.org/ru/docs/windows.html)

* start nginx
* nginx -s stop fast shutdown
* nginx -s quit graceful termination
* nginx -s reload change configuration, start new worker processes with new configuration, gracefully terminate old worker processes
* nginx -s reopen reopens log files

Paths in the configuration file must be specified in UNIX style using forward slashes.

Example:

        server {
            listen       80;
            server_name  localhost;
    		default_type text/html; 
            location / {
    			root   H:/doc/sites/hiking/output;
                index  index.html index.htm;
    			default_type text/html; 
    		
    		}
            error_page   500 502 503 504  /50x.html;
            location = /50x.html {
                root   html;
            }
        }

## Starting, stopping, reload

After changing configs, Nginx can re-read them without rebooting

```bash
sudo service nginx reload
```

For changes to the configuration file to take effect, it must be reloaded. You can either restart the nginx process or send the reload signal to upgrade the configuration without interrupting the processing of current requests.

```
nginx -s <SIGNAL>
```

where \<SIGNAL\> can be one of the following:

* quit -- Shut down gracefully (the SIGQUIT signal)
* reload -- Reload the configuration file (the SIGHUP signal)
* reopen -- Reopen log files (the SIGUSR1 signal)
* stop -- Shut down immediately (or fast shutdown, the SIGTERM singal)

The kill utility can also be used to send a signal directly to the master process. The process ID of the master process is written, by default, to the nginx.pid file, which is located in the /usr/local/nginx/logs or /var/run directory.
Send Nginx a reload signal inside the Docker container:

```bash
docker container exec <container> nginx -s reload
```

Check the correctness of the settings syntax in Nginx:

```bash
docker container exec <container> nginx -t
```

viewing logs

```bash
docker logs nginx-prod
```

## Configuration

Example

    #########################
    # dionext.com
    #########################
    
        #primary
        server{
            listen 80;
            server_name dionext.com www.dionext.com;
            location = / {
                return 301 http://$host/index.htm;
    
            }
            location /images {
                root   html/dionext/output;
            }
            location / {
                proxy_pass http://hiki-ms-app-80:8080/dionext/;
                proxy_set_header Host $host;
                proxy_set_header X-Real-IP $remote_addr;
                proxy_set_header X-Forwarded-For $remote_addr;
                proxy_connect_timeout 120;
                proxy_send_timeout 120;
                proxy_read_timeout 180;
               
                index  index.html index.htm;
            }
        }
        # secondary
        server{
            listen 80;
            server_name dev.dionext.com;
            location = / {
                return 301 http://$host/index.htm;
    
            }
            location /images {
                root   html/dionext/output;
            }
            location / {
                proxy_pass http://hiki-ms-app-81:8081/dionext/;
                proxy_set_header Host $host;
                proxy_set_header X-Real-IP $remote_addr;
                proxy_set_header X-Forwarded-For $remote_addr;
                proxy_connect_timeout 120;
                proxy_send_timeout 120;
                proxy_read_timeout 180;
               
                index  index.html index.htm;
            }
        }

## Load balancing

Load balancing is the process of distributing a set of tasks over a set of resources (computing units), with the aim of making their overall processing more efficient. Load balancing can optimize the response time and avoid unevenly overloading some compute nodes while other compute nodes are left idle. Load balancing is the subject of research in the field of parallel computers. Two main approaches exist: static algorithms, which do not take into account the state of the different machines, and dynamic algorithms, which are usually more general and more efficient but require exchanges of information between the different computing units, at the risk of a loss of efficiency. [https://en.wikipedia.org/wiki/Load\_balancing\_(computing](<https://en.wikipedia.org/wiki/Load_balancing_(computing>))

[https://docs.nginx.com/nginx/admin-guide/load-balancer/http-load-balancer/](https://docs.nginx.com/nginx/admin-guide/load-balancer/http-load-balancer/)

Load-Balancing Method

* Round Robin -- Requests are distributed evenly across the servers, with server weights taken into consideration. This method is used by default (there is no directive for enabling it)
* Least Connections -- A request is sent to the server with the least number of active connections, again with server weights taken into consideration
* IP Hash -- The server to which a request is sent is determined from the client IP address. In this case, either the first three octets of the IPv4 address or the whole IPv6 address are used to calculate the hash value. The method guarantees that requests from the same address get to the same server unless it is not available.
* Generic Hash -- The server to which a request is sent is determined from a user‑defined key which can be a text string, variable, or a combination. For example, the key may be a paired source IP address and port, or a URI as in this example
* Least Time (NGINX Plus only) -- For each request, NGINX Plus selects the server with the lowest average latency and the lowest number of active connections, where the lowest average latency is calculated based on which of the following parameters to the least\_time directive is included
* Random -- Each request will be passed to a randomly selected server. If the two parameter is specified, first, NGINX randomly selects two servers taking into account server weights, and then chooses one of these servers using the specified method

```
upstream backend {
    server backend1.example.com weight=5;
    server backend2.example.com;
    server 192.0.0.1 backup;
}
```

In the example, backend1.example.com has weight 5; the other two servers have the default weight (1), but the one with IP address 192.0.0.1 is marked as a backup server and does not receive requests unless both of the other servers are unavailable. With this configuration of weights, out of every 6 requests, 5 are sent to backend1.example.com and 1 to backend2.example.com.

Passive Health Checks{#passive-health-checks}

For passive health checks, NGINX and NGINX Plus monitor transactions as they happen, and try to resume failed connections. If the transaction still cannot be resumed, NGINX Open Source and NGINX Plus mark the server as unavailable and temporarily stop sending requests to it until it is marked active again.

The conditions under which an upstream server is marked unavailable are defined for each upstream server with parameters to the [server](https://nginx.org/en/docs/http/ngx_http_upstream_module.html#server) directive in the upstream block:

* fail\_timeout -- Sets the time during which a number of failed attempts must happen for the server to be marked unavailable, and also the time for which the server is marked unavailable (default is 10 seconds).
* max\_fails -- Sets the number of failed attempts that must occur during the fail\_timeout period for the server to be marked unavailable (default is 1 attempt).

## References

[https://stackoverflow.com/questions/3657614/how-to-rewrite-location-in-nginx-depending-on-the-client-browsers-languagev](https://stackoverflow.com/questions/3657614/how-to-rewrite-location-in-nginx-depending-on-the-client-browsers-languagev)

[https://habr.com/ru/company/ruvpn/blog/183060/](https://habr.com/ru/company/ruvpn/blog/183060/)

[http://server-tuning.info/nginx/](http://server-tuning.info/nginx/)

[http://www.michurin.net/tools/vds-nginx.html](http://www.michurin.net/tools/vds-nginx.html)

[https://nginx.org/ru/docs/windows.html](https://nginx.org/ru/docs/windows.html)
