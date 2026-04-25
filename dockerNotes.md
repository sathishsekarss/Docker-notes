**Table of contents**

1. [What is docker?](#what-is-docker)
2. [what is containers?](#what-is-containers)
3. [Difference between Virtual machienes and Docker containers?](#virtual-machines-and-docker-containers)
3. [Installation of Docker](#installation-of-docker)
4. [Images and Containers](#images-and-containers)
5. [Basic docker file](#basic-docker-file)
6. [Docker hub](#docker-hub)
7. [ Docker attach and detach mode](#docker-attach-and-detach-mode)


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

note:  If there is a elavated permission issue while installation.  Please install using Powershell by Clicking run as administrator.  Installation commands can be found in official docker site. 

## images and containers
**Docker Image**: A Docker image is a read-only template that contains the application and its dependencies. It is used to create Docker containers. Think of it as a blueprint for your application. eg. A Docker image for a Node.js app would include the Node.js runtime and your application code.

**Docker Container**: A Docker container is a running instance of a Docker image. It is an isolated environment where your application runs. Containers are lightweight and share the host OS kernel, making them faster to start and more efficient than virtual machines. eg. When you run a Docker image, it creates a container that executes your application in an isolated environment.  A container can be accessed via ports, and you can have multiple containers running the same image with different configurations in different terminals.

## basic-docker-file

**Use official Node.js image**
FROM node:18-alpine

**Set working directory**
WORKDIR /app

**Copy package files**
COPY package*.json ./

**Install dependencies**
RUN npm install

**Copy app source**
COPY . .

**Expose app port**
EXPOSE 3000

**Start the application**
CMD ["npm", "start"]

1. To run the above configurations first build the docker container,

```
 docker build -t my-app .
 ```

2. Then run the created docker container in using the below command and expose it via a port number
```
docker run -d \
  -p 3000:3000 \
  --name my-app-container \
  my-app
  ```
## docker-hub
A cloud-based registry for finding and sharing container images.

## docker-attach-and-detach-mode
    Docker attach connects your terminal to a running container’s STDIN/STDOUT. ( example using the docker Run CONTAINER_NAME command).

    Docker detach mode Run of leave a container in the background without blocking your terminal. ( example using the docker start CONTAINER_NAME command).

