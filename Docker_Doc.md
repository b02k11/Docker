# Table of Content
[Intoduction to Docker](#introduction-to-docker)  
[Advantages of Docker](#advantages-of-docker)  
[Prerequisites](#prerequisites)  
[Step by step Installation](#step-by-step-installation)  
[Working of Docker](#working-of-docker)   

# Introduction to Docker
Docker is a popular platform for developing, shipping, and running applications. It utilizes containerization technology to package applications and their dependencies into standardized units called containers.  
Docker allows you to separate your applications from your infrastructure so you can deliver software quickly. With Docker, you can manage your infrastructure in the same ways you manage your applications.

By taking advantage of Docker’s methodologies for shipping, testing, and deploying code quickly, you can significantly reduce the delay between writing code and running it in production.

# Key Concepts
**1. Containers**  
Containers are lightweight, standalone, and executable software packages that encapsulate an application and all its dependencies, including libraries, frameworks, and runtime environments. Docker containers ensure consistency across different environments, making it easier to deploy applications consistently.

**2. Images**  
Docker images are read-only templates used to create containers. They contain the application code, runtime environment, system libraries, and other dependencies required to run the application. Images are built using Dockerfiles, which specify the steps needed to create the image.

**3. Docker Engine**  
Docker Engine is the core component of Docker that enables container management. It consists of a daemon process (dockerd) that runs in the background and a REST API that allows communication with the daemon. Docker Engine is responsible for building, running, and distributing containers.

**4. Docker Hub**  
Docker Hub is a cloud-based registry service provided by Docker that allows users to store and share Docker images. It hosts a vast collection of public images that users can pull and use in their projects. Docker Hub also enables users to publish their own images for others to use.

**5. Docker Compose**  
Docker Compose is a tool for defining and running multi-container Docker applications. It uses a YAML file to configure the services, networks, and volumes required by the application. Docker Compose simplifies the process of managing complex applications composed of multiple interconnected containers.

# Advantages of Docker

### Portability:
Docker containers are platform-independent and can run on any system that supports Docker. This portability eliminates the "it works on my machine" problem and ensures consistent behavior across different environments, from development to production.


### Isolation:

Containers provide a high level of isolation between applications, preventing conflicts between dependencies and ensuring that changes to one application do not affect others. This isolation enhances security and stability in multi-tenant environments.

### Resource Efficiency:

Docker's lightweight containers consume fewer resources compared to virtual machines, making more efficient use of server hardware. Containers start up quickly, allowing for rapid development cycles and faster time-to-market for applications.

### Environments:

Docker's containerization ensures consistency between development, testing, and production environments. This reduces the "it works on my machine" problem and streamlines the deployment process, making it easier to manage applications across different stages.

### Rapid Deployment:

Docker containers can be started and stopped quickly, allowing for rapid deployment and scaling of applications. This agility is particularly beneficial for dynamic and rapidly changing workloads, where applications need to scale up or down based on demand.

### Ecosystem and Docker Hub:

Docker has a vast and active ecosystem, and Docker Hub serves as a centralized repository for sharing and distributing container images. Developers can leverage pre-built images, reducing the need to recreate the entire application stack from scratch.  

### Security:

Docker provides built-in security features, such as namespace isolation and resource constraints. Containers are isolated from each other and from the host system, reducing the risk of security vulnerabilities.

### Resource Utilization:

Docker optimizes resource utilization by allowing multiple containers to run on a single host, each with its own set of resources. This efficient use of resources contributes to cost savings and better overall system performance.

# Prerequisites

## OS Requirement
* Ubuntu Mantic 23.10
* Ubuntu Lunar 23.04
* Ubuntu Jammy 22.04 (LTS)
* Ubuntu Focal 20.04 (LTS)

## OS Details

PRETTY_NAME="Ubuntu 22.04.3 LTS"  
NAME="Ubuntu"  
VERSION_ID="22.04"  
VERSION="22.04.3 LTS (Jammy Jellyfish)"  
VERSION_CODENAME=jammy  
ID=ubuntu  
ID_LIKE=debian  
UBUNTU_CODENAME=jammy

# Step by step Installation  
## Uninstall old versions  
Before you can install Docker Engine, you need to uninstall any conflicting packages.
The unofficial packages to uninstall are:

docker.io
docker-compose
docker-compose-v2
docker-doc
podman-docker  

Run the following command to uninstall all conflicting packages:
```
for pkg in docker.io docker-doc docker-compose docker-compose-v2 podman-docker containerd runc; do sudo apt-get remove $pkg; done
```

## Installation methods  


## Set up Docker's apt repository.
```
# Add Docker's official GPG key:
sudo apt-get update
sudo apt-get install ca-certificates curl
sudo install -m 0755 -d /etc/apt/keyrings
sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
sudo chmod a+r /etc/apt/keyrings/docker.asc

# Add the repository to Apt sources:
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu \
  $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt-get update
```
## Install the Docker packages.
```
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```
## Output

> Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
docker-buildx-plugin is already the newest version (0.11.2-1~ubuntu.22.04~jammy).
The following packages were automatically installed and are no longer required:
  bridge-utils dctrl-tools dkms libdouble-conversion3 libgsoap-2.8.117 liblzf1 libmd4c0 libpcre2-16-0
  libqt5core5a libqt5dbus5 libqt5gui5 libqt5network5 libqt5opengl5 libqt5printsupport5 libqt5svg5
  libqt5widgets5 libqt5x11extras5 libsdl1.2debian libxcb-xinerama0 libxcb-xinput0 qt5-gtk-platformtheme
  qttranslations5-l10n ubuntu-fan virtualbox-dkms wmdocker
Use 'sudo apt autoremove' to remove them.
Suggested packages:
  aufs-tools cgroupfs-mount | cgroup-lite
The following NEW packages will be installed:
  containerd.io docker-ce docker-ce-cli docker-compose-plugin
0 upgraded, 4 newly installed, 0 to remove and 4 not upgraded.
Need to get 11.9 MB/77.3 MB of archives.
After this operation, 312 MB of additional disk space will be used.
Do you want to continue? [Y/n] Y
Get:1 https://download.docker.com/linux/ubuntu jammy/stable amd64 docker-compose-plugin amd64 2.21.0-1~ubuntu.22.04~jammy [11.9 MB]
Fetched 11.9 MB in 4s (2,789 kB/s)                
Selecting previously unselected package containerd.io.
(Reading database ... 261004 files and directories currently installed.)
Preparing to unpack .../containerd.io_1.6.26-1_amd64.deb ...
Unpacking containerd.io (1.6.26-1) ...
Selecting previously unselected package docker-ce-cli.
Preparing to unpack .../docker-ce-cli_5%3a24.0.7-1~ubuntu.22.04~jammy_amd64.deb ...
Unpacking docker-ce-cli (5:24.0.7-1~ubuntu.22.04~jammy) ...
Selecting previously unselected package docker-ce.
Preparing to unpack .../docker-ce_5%3a24.0.7-1~ubuntu.22.04~jammy_amd64.deb ...
Unpacking docker-ce (5:24.0.7-1~ubuntu.22.04~jammy) ...
Selecting previously unselected package docker-compose-plugin.
Preparing to unpack .../docker-compose-plugin_2.21.0-1~ubuntu.22.04~jammy_amd64.deb ...
Unpacking docker-compose-plugin (2.21.0-1~ubuntu.22.04~jammy) ...
Setting up containerd.io (1.6.26-1) ...
Setting up docker-compose-plugin (2.21.0-1~ubuntu.22.04~jammy) ...
Setting up docker-ce-cli (5:24.0.7-1~ubuntu.22.04~jammy) ...
Setting up docker-ce (5:24.0.7-1~ubuntu.22.04~jammy) ...
Processing triggers for man-db (2.10.2-1) ...

## Verify Installation  
Verify that the Docker Engine installation is successful by running the hello-world image.  
```
sudo docker run hello-world
```

## Output

> Unable to find image 'hello-world:latest' locally
latest: Pulling from library/hello-world
c1ec31eb5944: Pull complete 
Digest: sha256:ac69084025c660510933cca701f615283cdbb3aa0963188770b54c31c8962493
Status: Downloaded newer image for hello-world:latest

> Hello from Docker!
> This message shows that your installation appears to be working correctly.

> To generate this message, Docker took the following steps:
 >1. The Docker client contacted the Docker daemon.
 >2. The Docker daemon pulled the "hello-world" image from the Docker Hub.
    (amd64)
 >3. The Docker daemon created a new container from that image which runs the executable that produces the output you are currently reading.
 >4. The Docker daemon streamed that output to the Docker client, which sent it to your terminal.

>To try something more ambitious, you can run an Ubuntu container with:
 $ docker run -it ubuntu bash

> Share images, automate workflows, and more with a free Docker ID:
 https://hub.docker.com/


> For more examples and ideas, visit:
 https://docs.docker.com/get-started/

### Check Version
```
docker -v
```
## Output 

> Docker version 24.0.7, build afdd53b


 # Working Of Docker

## Pull an Image
```
sudo docker pull (image_name)
```
### For Example 
```
docker pull ubuntu
```

## Output
> Using default tag: latest
latest: Pulling from library/ubuntu
Digest: sha256:6042500cf4b44023ea1894effe7890666b0c5c7871ed83a97c36c76ae560bb9b
Status: Image is up to date for ubuntu:latest
docker.io/library/ubuntu:latest

### Image:
Definition: A lightweight, standalone, and executable package that includes everything needed to run a piece of software, including the code, runtime, libraries, and system tools.

### Pulling an Image:
Definition: Downloading a Docker image from a registry or repository to the local machine.

## To know the exists image

```
sudo docker image ls
```

## Output

REPOSITORY    |   TAG     | IMAGE ID      | CREATED       | SIZE
--------------|-----------|---------------|---------------|--------
nginx         |   latest  | d453dd892d93  | 2 months ago  | 187MB
hello-world   |   latest  | d2c94e258dcb  | 8 months ago  | 13.3kB

### Container: 
A lightweight, standalone, and executable software package that includes everything needed to run a piece of software, including the code, runtime, libraries, and system tools.

## To RUN the container {For specific time period in detetch mode}

```
sudo docker container run -d (image_name) sleep (seconds)
```

## To know the exist running containers

```
sudo docker container ls
```
```
sudo docker ps
```

## Output

CONTAINER ID|IMAGE |COMMAND    |CREATED        |STATUS        |  PORTS  |NAMES
------------|------|-----------|---------------|--------------|---------|---------
2fab2ad8f10e|ubuntu|"/bin/bash"|29 seconds ago |Up 28 seconds |         |clever_chebyshev

## To RUN the container 
```
sudo docker container run (image_name)
```
* This command can run the container but also exit immediatly

## To know the all exist containers (Stopped/Exited Container)

```
sudo docker container ls -a
```
```
sudo docker ps -a
```
## To RUN container in bash shell and go in interactive terminal
```
sudo docker container run -itd ubuntu /bin/bash
```
### Then :
```
docker exec -it CONTAINER_ID /bin/bash
```

* The command is used to run a detached (-d) Docker container based on the Ubuntu image with an interactive (-it) session, starting the /bin/bash shell as the main process. It is also used when we want to installs any particular software in our container.


## To Remove the stopped/exited container
```
sudo docker container rm (container name/id) 
```

## To Start container 
```
sudo docker container start (container_id)
```

## For Example 
```
sudo docker container start 2fab2ad8f10e
```
## Output
> 2fab2ad8f10e

CONTAINER ID|IMAGE |COMMAND    |CREATED     |STATUS           |PORTS |NAMES
------------|------|-----------|------------|-----------------|------|---------
2fab2ad8f10e|ubuntu|"/bin/bash"|18 hours ago|Up About a minute|      |clever_chebyshev

## To stop container
```
sudo docker container stop (container_id)
```
 
 ## For Example
 ```
 sudo docker container stop 2fab2ad8f10e
 ```
## Output

>2fab2ad8f10e

 CONTAINER ID|IMAGE |COMMAND    |CREATED     |STATUS                      |PORTS |NAMES
-------------|------|-----------|------------|----------------------------|------|-----------------
2fab2ad8f10e |ubuntu|"/bin/bash"|18 hours ago|Exited (137) 17 seconds ago |      |clever_chebyshev

## To Inspect Container

```
sudo docker container inspect (container_id)
```

 ### If we want to know the logs of container we have to run the few commands before :
 ```
 Sudo docker container run -d (container_name)
 ```
 then :
 ```
 sudo docker container inspect (container_id)
 ```
 * When we inspect the container we have to copy the container IP address and paste in the Browser

then:
 ```
sudo docker container logs (container_id)
```

## To know the ongoing proccess in container (running container)

```
sudo docker container top (container_id)
```

### Port mapping 
Port mapping in Docker involves specifying how ports on the host system should be mapped to ports exposed by a container. This mapping allows external traffic to reach specific services running inside the container. Port mapping is particularly crucial when you have multiple containers running on a host, and you need to avoid port conflicts.

### To know ip address of your machine use :
```
hostname -I
```
### To know IP address of your container use :
```
sudo docker container inspect container_id 
```

## To change name of any Container 
```
sudo docker container rename (container_id) (new_name)
```

## To restart Container
```
sudo docker container restart (container_id)
```

## To show the ongoing process in background at the terminal
```
sudo docker container attach (container_id)
```

## This will kill / Stop the container
```
sudo docker container kill (container_id)
```

 ### Docker Hub:
Docker Hub is a cloud-based registry service provided by Docker that allows users to store and share Docker images. It hosts a vast collection of public images that users can pull and use in their projects. Docker Hub also enables users to publish their own images for others to use.  

## To create Docker file

```
sudo vi Dockerfile
```

### Dockerfile:
A text file that contains instructions for building a Docker image. It specifies a base image, sets up the environment, installs dependencies, and defines the application to run.

Example of Dockerfile  
```
  FROM node:latest
  LABEL description="A demo Dockerfile for build Docsify."
  WORKDIR /docs
  RUN npm install -g docsify-cli@latest
  EXPOSE 3000/tcp
  ENTRYPOINT docsify serve .
```

# FEW DOCKER FILE COMMANDS
ADD	:  
Add local or remote files and directories.  
ARG :  
Use build-time variables.  
CMD :  
Specify default commands.  
COPY :	  
Copy files and directories.  
ENTRYPOINT	  
Specify default executable.  
ENV :	  
Set environment variables.  
EXPOSE :	  
Describe which ports your application is listening on.  
FROM :	  
Create a new build stage from a base image.  
HEALTHCHECK :   
Check a container's health on startup.  
LABEL :  
Add metadata to an image.  
MAINTAINER :  
Specify the author of an image.  
ONBUILD :  
Specify instructions for when the image is used in a build.  
RUN:  
Execute build commands.  
