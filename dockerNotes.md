**Table of contents**

1. [What is docker?](#what-is-docker)
2. [what is containers?](#what-is-containers)
3. [Difference between Virtual machienes and Docker containers?](#virtual-machines-and-docker-containers)
3. [Installation of Docker](#installation-of-docker)


## what is docker

Docker is a containerization tool used to containeraize application.  Example,  Bundle application with its necessary dependencies.

Docker is used to

1.  Create containers
2.  Run containers
3.  Manage containers

## what is containers

A container is lightweight and isolated environment that has,

1.  Your application
2.  All required libraries and dependencies
3.  Runtime ( like Java, Node, Pythong )

eg.  A container is like a sealed lunch box with everything your app needs.

## virtual machines and docker containers

| Feature        | Virtual Machine        | Docker Container  |
| -------------- | ---------------------- | ----------------- |
| OS             | Full Guest OS per VM   | No guest OS       |
| Size           | Heavy (GBs)            | Lightweight (MBs) |
| Startup time   | Minutes                | Seconds           |
| Performance    | Slower (more overhead) | Near-native speed |
| Isolation      | Strong (OS-level)      | Process-level     |
| Resource usage | High                   | Low               |
| Portability    | Less portable          | Highly portable   |
| Scaling        | Slow                   | Very fast         |

Example:
Spring Boot app

VM approach:
VM + Ubuntu
Install Java
Install app
Takes time & memory

Docker approach:
Docker image with Java + app
Run anywhere instantly
Same behavior in Dev / QA / Prod

## installation-of-docker

For installation of docker refer to the official documentation from the docker site.
