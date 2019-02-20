#Deploy wordpress with docker

- - -

[TOC]


- - -

This repository introduces how to deploy wordpress with docker, actually, with docker-compose. With docker, you can deploy easily without build LAMP enviroment, besides, it is also easy to update related components.

## Installing

- - -

### Installing docker-ce
To install docker, you can reference [docker offical site](https://docs.docker.com/install/), which introduces how to install docker-ce in detail, including different kinds of OS.
> - Linux
>   - [Centos](https://docs.docker.com/install/linux/docker-ce/centos/)
>   - [Debian](https://docs.docker.com/install/linux/docker-ce/debian/)
>   - [Fedora](https://docs.docker.com/install/linux/docker-ce/fedora/)
>   - [Ubuntu](https://docs.docker.com/install/linux/docker-ce/ubuntu/)
>   - [Binaries](https://docs.docker.com/install/linux/docker-ce/binaries/)
>   - [Optional Linux post-installation steps](https://docs.docker.com/install/linux/linux-postinstall/)
> - [MacOS](https://docs.docker.com/docker-for-mac/install/)
> - [Windows](https://docs.docker.com/docker-for-windows/install/)

### Download the repository
Change directory to a place where you want to put source code and execute:
```bash
cd ~
git clone https://github.com/kefins/docker_wpress.git wpress
```

## Deploying
On downloading source code, you can start deploy wordpress witch just one command
```bash
kefins@localhost:~$ cd wpress
kefins@localhost:~/wpress $ docker-compose up -d
Creating network "wpress_backup_frontend" with driver "bridge"
Creating network "wpress_backup_backend" with driver "bridge"
Creating db ... done
Creating wpress ... done
Creating nginxD ... done
```
After executing the command, you can check status of docker containers.
```bash
kefins@localhost:~/wpress $ docker ps
CONTAINER ID        IMAGE                        COMMAND                  CREATED             STATUS              PORTS                                      NAMES
9bd40fd78887        nginx:latest                 "nginx -g 'daemon of…"   5 minutes ago       Up 5 minutes        0.0.0.0:80->80/tcp, 0.0.0.0:443->443/tcp   nginxD
fee4affcd2c2        wordpress:5.0.3-php7.2-fpm   "docker-entrypoint.s…"   5 minutes ago       Up 5 minutes        0.0.0.0:9000->9000/tcp                     wpress
5a7c34636314        mariadb                      "docker-entrypoint.s…"   5 minutes ago       Up 5 minutes        0.0.0.0:3306->3306/tcp                     db
```

From the result of command ==docker ps==, you can find it runs three docker containers,
1. nginx
2. mariadb
3. nginx

- - -

## Config WordPress
Now you can input == xx.xx.xx.xx:8080 == in you browser to config wordpress, and enjoy...

