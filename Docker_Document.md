# Table of Content
[Intoduction to Docker](#introduction-to-docker)  
[Advantages of Docker](#advantages-of-docker)  
[Prerequisites](#prerequisites)  
[Installation Step](#installation-step)  
[Working of Docker](#working-of-docker)  
[Docker Volume](#docker-volume)  
[Docker Network](#docker-network)  




# Introduction to Docker
Docker is an open platform for developing, shipping, and running applications.

Docker allows you to separate your applications from your infrastructure so you can deliver software quickly. With Docker, you can manage your infrastructure in the same ways you manage your applications.

By taking advantage of Docker’s methodologies for shipping, testing, and deploying code quickly, you can significantly reduce the delay between writing code and running it in production.

# Advantages of Docker

### Portability:
Docker containers encapsulate applications and their dependencies, ensuring consistency across different environments. This portability allows developers to build, test, and deploy applications seamlessly on various platforms, from development to production.

### Isolation:


Containers provide a high degree of isolation, allowing applications to run independently of the host system and other containers. This isolation ensures that changes or updates to one container do not affect others, leading to more reliable and predictable behavior.

### Resource Efficiency:

Docker containers share the host system's kernel, making them lightweight compared to traditional virtual machines. Containers require fewer resources, resulting in faster startup times and improved efficiency in terms of system resources.
Consistency Across 

### Environments:

Docker's containerization ensures consistency between development, testing, and production environments. This reduces the "it works on my machine" problem and streamlines the deployment process, making it easier to manage applications across different stages.

### Rapid Deployment:

Docker containers can be started and stopped quickly, allowing for rapid deployment and scaling of applications. This agility is particularly beneficial for dynamic and rapidly changing workloads, where applications need to scale up or down based on demand.

### Version Control and Rollback:

Docker images can be versioned, providing a mechanism for tracking changes over time. This version control facilitates easy rollback to previous states if issues arise, enabling more robust release management.

### Ecosystem and Docker Hub:

Docker has a vast and active ecosystem, and Docker Hub serves as a centralized repository for sharing and distributing container images. Developers can leverage pre-built images, reducing the need to recreate the entire application stack from scratch.

### Microservices Architecture:

Docker containers are well-suited for microservices architecture, allowing developers to break down applications into smaller, modular components. Each component can be containerized and independently deployed, scaled, and updated.

### DevOps Integration:

Docker aligns well with DevOps practices, promoting collaboration between development and operations teams. Containers can be integrated into continuous integration and continuous deployment (CI/CD) pipelines, automating the application delivery process.

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

### Ubuntu:
Definition: A popular open-source Linux distribution based on Debian. It is widely used for server and desktop environments.


# Installation Step

## Add Docker's official GPG key:
```
sudo apt-get update; sudo apt-get install ca-certificates curl gnupg; sudo install -m 0755 -d /etc/apt/keyrings; curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg; sudo chmod a+r /etc/apt/keyrings/docker.gpg
```

### GPG Key:
GNU Privacy Guard (GPG) key is used for secure communication and data integrity verification. Docker uses GPG keys to verify the authenticity of the Docker packages during installation.


## Add the repository to Apt sources:
```
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt-get update 
```

### Repository:
A central location or server that holds a collection of Docker images, allowing users to share and distribute containerized applications.

### APT (Advanced Package Tool):
A package management system used by Ubuntu and other Debian-based Linux distributions. It is used to install, remove, and manage software packages.


## Install the Docker package

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

### Check Version
```
docker -v
```
## Output 

> Docker version 24.0.7, build afdd53b


### RUN HELLO WORLD
```
docker run hello-world
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
ubuntu        |   latest  | 174c8c134b2a  | 3 weeks ago   | 77.9MB
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

## To go direct in interactive terminal shell use :
```
docker container run -it ubuntu /bin/bash
``` 
* If you want to come out from terminal shell without stopping container use :
```
ctrl + p + q
```
* If you want to exit by stopping container use :
```
ctrl + d
```

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

## To Remove all stopped containers

```
sudo docker container rm $(sudo docker container ls -aq)
```

## Output
>7b93dd8c09d5  
27f9634da99f  
e9570b80aa8d  
745ba55f2582  
6d23d9f65318  
9a546e090059  
b51df07a5d5b  
aa77717f757f  
5ce6d99be9dd  
b1535b31f7ff  
2fab2ad8f10e  
5602482d8805  
Error response from daemon: You cannot remove a running container 1e7542ea8568dcc62f5f80384b9c31fbd70d0d79d0fa6e792e4d8c0fced5c7f0. Stop the container before attempting removal or force remove  
Error response from daemon: You cannot remove a running container f095668f6675622d1b3f9543ff46f02b4b996792ebce93fc476cb78c086bf170. Stop the container before attempting removal or force remove  
Error response from daemon: You cannot remove a running container 9ce8c792da8d9c93fef4199e032b54e348f028e48d8776ce7e33cb2ba847f09c. Stop the container before attempting removal or force remove  
Error response from daemon: You cannot remove a running container bcf0157abab179b3de043ba7f983de9f500b6c1523a8b38ebb3f47cf458fdd8b. Stop the container before attempting removal or force remove

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

## To know the state of the containers running in background (memory usage, cpu, etc.)

```
sudo docker container stats
```

## Port Mapping of a Container
```
#ip_address of container
```
```
#docker 3600 ->xyz:80
```
```
#ip_address of machine:3600 -> ip_address of container:80
```
```
sudo docker container run -d -p 3600:80 --name test1_web (image_name)
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
## To get access of shell of the container if we want to install any particular software in the container

```
sudo docker container exec -it (container_id) /bin/bash
```
then :
```
sudo apt-get update
```
then :
```
sudo apt-get install software_name
```
then :
```
software_name --version
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

## To wait for container to stop
```
sudo docker container wait (container_id) 
```

## To Pause or Unpause the container

```
sudo docker container pause/unpause (container_id)
```

## To delete all stopped/exited containers

```
sudo docker container prune
```

## Output
>WARNING! This will remove all stopped containers.
Are you sure you want to continue? [y/N] y
Deleted Containers:
def7cf675265d5d3009496b8c1cbf430e3824f995c7d8a87e802e31020b6d7e3
ff1f77d64082a8dacfa2b5bc8065cc689814823ca7e1511ecd7afea8e8723d02
bd4da46636cb98fd0855614ad4abf3aaa8586ee49be6fa07fcce2c2ad469e1d5
a5bcb42409185532c0978167937358f8fb2f162fc167dc7317823093581c893d
a4226dc96cedf83708a25d6557f969a16bddeaf1e0166ca8edc085d958fcd19a
38861fea9003e2e201a47c9d31091dc61aec4f19e5244a59f32c7217ff542c7a
3f25d2d430b9f200d657d2142ea85bab941264a2dedec420a9492aa3dd704284
91fc560ef199235178bc4449fadd68e6bb5cb0b95cc9183641cdf15ec1f6ec24
216d72ddab73d2a9520cad3cb37bb650f6fe4917440fedba28f18f9796639c4c
3296c0f59f5c96cf2419b4ae85bfacf489763993a9704671f2fa52549a0a8783
3991ba7a19ca99f99d4b0c500f6221ba5d2a11938886e85422f65332526e1409
013dd5d8f96b26792edf8b80d4a435ab9b10e3017886bf5e5cdebbb1226fe650
21311ccb3fe1ad15668d14e613a02cd104e4f0cffa639cdc4c7d1c3608ecf28e
1e7542ea8568dcc62f5f80384b9c31fbd70d0d79d0fa6e792e4d8c0fced5c7f0
f095668f6675622d1b3f9543ff46f02b4b996792ebce93fc476cb78c086bf170
9ce8c792da8d9c93fef4199e032b54e348f028e48d8776ce7e33cb2ba847f09c
bcf0157abab179b3de043ba7f983de9f500b6c1523a8b38ebb3f47cf458fdd8b




## To know the port mapping of the container
```
sudo docker container port (container_id/container_name)
```

## To create a container but don't start
```
sudo docker container create (image_name) sleep
```

## To know the changes made by you in a container
```
sudo docker container diff (container_id)
```

> In the Output
A - Add a file / Directory  
C - Create file / Directory  
D -  Delete file / Directory  

## To show continously every changes we will make to container in every 2 second

```
sudo watch 'docker container diff (container_id)'
```

## To copy a file to container

```
sudo docker container cp (file_name)/(container_id):/(source_path)
```

## To export container as file
```
sudo docker container export (container_id) >(file_name).tar
```

## To import image from the container file

```
sudo docker image import (container_filename).tar (image_name)
```
## To directly export a container and import as an image

```
sudo docker container commit --author "Name" (container_id) (image_name)
```

## To pull specific version of an image

```
sudo docker pull (image_name):specific_version
```
## To tag the image if we delete the first image it will contain all the files which is already installed in it

```
sudo docker image tag (image_name) (user_name)/(image_new_name)
```
## To push our customise image on docker hub and anyone call the image

```
sudo docker push (dockerhub_username)/(image_name)
```
 ### Docker Hub:
 A cloud-based registry service provided by Docker for sharing container images. It allows developers to store and distribute Docker images publicly or privately.        

## To show the format changes images details

```
sudo docker image ls --format '{{.ID}} , {{.Repository}}'
```

* Any format you want to change Please write in .{{}} , .{{}} , in this format


## To show the history of images

```
sudo docker image history (image_name)
```

* If there is an other tag or specific version of the image we have to declare


## To inspact the image

```
sudo docker image inspect (image_name) |less
```


## To save our image as a tar file which help us to share that image

```
sudo docker image save (image_name) > (image_name).tar
```
## This will help in loading the image

```
sudo docker image load <(file_name)
```
## To build an image

```
sudo docker image build -t (image_name):1 .
```

* . is indicating that docker file is in current working directory


## To remove image
```
sudo docker image rm (Image_name)
```

### For Example : 
```
sudo docker image rm ubuntu nginx hello-world

```
## Output
>Untagged: ubuntu:latest
Untagged: ubuntu@sha256:6042500cf4b44023ea1894effe7890666b0c5c7871ed83a97c36c76ae560bb9b
Deleted: sha256:174c8c134b2a94b5bb0b37d9a2b6ba0663d82d23ebf62bd51f74a2fd457333da
Untagged: nginx:latest
Untagged: nginx@sha256:2bdc49f2f8ae8d8dc50ed00f2ee56d00385c6f8bc8a8b320d0a294d9e3b49026
Deleted: sha256:d453dd892d9357f3559b967478ae9cbc417b52de66b53142f6c16c8a275486b9
Deleted: sha256:efa10324a701d6accf82a523dcaba9aadf21943e214a8879d10c13284bffcd5f
Deleted: sha256:4178f7184379d32ddc77d881dca384ac307dedb0c42f521fe633c5a95f308cd6
Deleted: sha256:454122e697d0fd11338a4e00fd1d20acd2eaf133544321160606c908ca395911
Deleted: sha256:b4ad020cdacfccfc4faf3dcd7984f600391d3972063112dd2b37dfbd30105993
Deleted: sha256:6f226612ab7aafdd91fcc90917ad3d7a667237a78785fe2309faf160559a69a7
Deleted: sha256:9671ab29815f09e9c2552b872e0097732d4b5efb5dfdc91630853d7bf7221f1a
Deleted: sha256:7292cf786aa89399bca4e3edd105d3b2ee0683a46ef1f5ff436c0f9d1d49e765
Untagged: hello-world:latest
Untagged: hello-world@sha256:ac69084025c660510933cca701f615283cdbb3aa0963188770b54c31c8962493
Deleted: sha256:d2c94e258dcb3c5ac2798d32e1249e42ef01cba4841c2234249495f87264ac5a
Deleted: sha256:ac28800ec8bb38d5c35b49d45a6ac4777544941199075dff8c4eb63e093aa81e



## To create Docker file

```
sudo vi Dockerfile
```

### Dockerfile:
A text file that contains instructions for building a Docker image. It specifies a base image, sets up the environment, installs dependencies, and defines the application to run.

## To see the environmental variable

```
env
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
SHELL	Set the default shell of an image.  
STOPSIGNA:  
Specify the system call signal for exiting a container.  
:set number :  
This will set numbers on our commands  
USER :  
Set user and group ID.  
VOLUME:	  
Create volume mounts.  
WORKDIR:  
Change working directory.  


# Docker Volume

A Docker feature that allows data to persist beyond the lifecycle of a container. Volumes are used for storing and sharing data between containers.


* If you want to use docker volume to retreive you old container data then you use docker volume. The data store in             
"Volumes": {  
             "/var/lib/image_name": {}  
},  
  There are few steps how you can access your old container:

## Step 1 - 
## Run a Container
```
sudo docker container run -d --name mysql1 -e MYSQL_ALLOW_EMPTY_PASSWORD=true mysql
```
## Output 

>98eeb0b3707bed3dd7ee833576dfef248c7c9114bfc5b61ef2d18a13a2eb8c20

## Step 2 - 
## To know exists Docker Volume
```
sudo docker volume ls
```

## Step 3 -
## Inspect Docker volume

```
sudo docker volume inspect (volume_name)
```
## For Example
```
sudo docker volume inspect 4364fa6d1b0fee8b6f08a165b13104e54af9ac0664a9faa6427ec2296de2ba2a
```

## Output 
>[
    {
        "CreatedAt": "2024-01-10T22:42:41+05:30",
        "Driver": "local",
        "Labels": {
            "com.docker.volume.anonymous": ""
        },
        "Mountpoint": "/var/lib/docker/volumes/4364fa6d1b0fee8b6f08a165b13104e54af9ac0664a9faa6427ec2296de2ba2a/_data",
        "Name": "4364fa6d1b0fee8b6f08a165b13104e54af9ac0664a9faa6427ec2296de2ba2a",
        "Options": null,
        "Scope": "local"
    }
]

## Step 4 -
## Go in in the volume directory by using :

```
cd /var/lab/docker/volumes/(volume_name)
```

then:

```
ls
```
then:
```
cd (the directory found)
```
then:

```
ls
```
* You will see the stored Data.

## For Example 

```
cd /var/lib/docker/volumes/5e209b16f702f75e7a3244f4e825ada25ee241ce2765ed292a8c57f9b34dd294/_data
```
## Output
> root@rahul-ahlawat:/var/lib/docker/volumes/5e209b16f702f75e7a3244f4e825ada25ee241ce2765ed292a8c57f9b34dd294/_data#


```
ls
```
 auto.cnf      |ca.pem             |ib_buffer_pool|mysql             |public_key.pem  
 --------------|-------------------|--------------|------------------|----------------
 binlog.000001 |client-cert.pem    |ibdata1       |mysql.ibd         |server-cert.pem
 binlog.000002 |client-key.pem     |ibtmp1        |mysql.sock        |server-key.pem
 binlog.index  |'#ib_16384_0.dblwr'|'#innodb_redo'|performance_schema|sys
 ca-key.pem    |'#ib_16384_1.dblwr'|'#innodb_temp'|private_key.pem   |undo_001

## Now We will save our data in database 

## Run Container in which our database is stored (Go in terminal shell)

```
sudo docker container exec -it (container_id) /bin/bash
```
```
database_software_name
```
```
show databases;
```
### Now Create Database

```
create database (database_detail);
```

## For Example
```
sudo docker container exec -it 98ee bash
```
```
mysql
```
## Output
>Welcome to the MySQL monitor.  Commands end with ; or \g.
Your MySQL connection id is 9
Server version: 8.2.0 MySQL Community Server - GPL

Copyright (c) 2000, 2023, Oracle and/or its affiliates.

Oracle is a registered trademark of Oracle Corporation and/or its
affiliates. Other names may be trademarks of their respective
owners.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

```
show databases;
```
## Output
+--------------------+
| Database           |
+--------------------+
| information_schema |
| mysql              |
| performance_schema |
| sys                |
+--------------------+
4 rows in set (0.01 sec)

```
create database rahul;
```
## Output
>Query OK, 1 row affected (0.00 sec)


```
create database ahlawat;
```
## Output
>Query OK, 1 row affected (0.00 sec)

```
create database jaat;
```
## Output
> Query OK, 1 row affected (0.00 sec)


* Now Remove the particular container
* Run another container using the command:

```
sudo docker container run -itd -v 5e209b16f702f75e7a3244f4e825ada25ee241ce2765ed292a8c57f9b34dd294:/var/lib/mysql mysql
```

## Output
> 434e9ebc0c92349b37550130dc483926d9f9c07d6fdabcda8fc32356cc77f45e

then:
```
sudo docker container exec -it (container_id) /bin/bash
```

```
docker container exec -it 434 bash
```
then:

```
mysql
```
### In mysql
```
show databases;
```
## Output 
>+--------------------+
| Database           |
+--------------------+
| ahlawat            |
| information_schema |
| jaat               |
| mysql              |
| performance_schema |
| rahul              |
| sys                |
+--------------------+
7 rows in set (0.00 sec)

## Docker volume name

```
sudo docker container run -d --name xyz_com_database12 -v (volume_name):/var/lib/mysql -e MYSQL_ALLOW_EMPTY_PASSWORD=true mysql
```

### For Example
```
sudo docker container run -d --name xyz_com_database12 -v abc:/var/lib/mysql -e MYSQL_ALLOW_EMPTY_PASSWORD=true mysql
```
## Output
>a46cadf0b0f844fbf5268a23d581b5540e1bf8560a57eff6f380c0a7dffb8463

```
docker volume ls
```
## Output

DRIVER  |VOLUME NAME
--------|-----------
local   |abc

## Create a Docker volume
```
sudo docker volume create (volume_name)
```
## To remove volume 

```
sudo docker rm (volume_name)
```
* One by one remove

```
sudo docker volume prune
```
* All unused volume will be removed

## Docker Volume Bind
A technique in Docker that allows a file or directory on the host machine to be mounted into a container. Changes made in either the container or on the host are reflected in both locations.
### Steps:

```
mkdir bind
```

```
cd bind
```

```
 touch index.html
```
```
docker container run -it -v /home/rahul/bind:/tmp/test ubuntu:latest bash
```

## Docker Network

Docker networking enables a user to link a Docker container to as many networks as he/she requires. Docker Networks are used to provide complete isolation for Docker containers. 
* Note: A user can add containers to more than one network.

## To know the already present network
```
docker network ls
```

## Output

NETWORK ID    |NAME     |DRIVER   |SCOPE
--------------|---------|---------|------
750b0c4f972a  |bridge   |bridge   |local
2a6e1526767d  |host     |host     |local
a9bd3a5dd0ba  |one      |null     |local

## To create new Docker Network

```
sudo docker network create -d bridge (network_name)
```

 ### To creates a network using the bridge network driver and running a container in the created network:



```
sudo docker container run -it --network (network_name)(image_name)
```

## Divers of Docker

* The following network drivers are available by default, and provide core networking functionality:


Driver     |Description
-----------|-----------------------
bridge     |The default network driver.
host  	   |Remove network isolation between the container and the Docker host.
none  	   |Completely isolate a container from the host and other containers.
overlay    |Overlay networks connect multiple Docker daemons together.
ipvlan     |IPvlan networks provide full control over both IPv4 and IPv6 addressing.
macvlan    |Assign a MAC address to a container.


