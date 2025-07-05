https://www.youtube.com/watch?v=0UG2x2iWerk
https://www.youtube.com/watch?v=bi0cKgmRuiA 

There are 3 stages to create containerized images - 

1) docker file - blue print to create docker images
2) docker images - we build these images, containers are created storing them. these are set of instructions on how a container is suppose to run.
3) containers -  when these docker images are made to run containers are created. These containers cn be stopeed, started as per requirement. these containers it contains all the dependencies like python libraries , python distribution or base image coming from docker hub, python script etc.

Need to activate/enable virtualization before running docker images and wsl if we are running docker on windows system.
1) wsl --install
2) wsl --update
3) enabing wsl feature - dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart 
4) enabling feature for Virtual Machine Platform - dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
5) go to cmd in admin mode, right click in top bar if cmd window and select properties and then uncheck use legacy option 
6) to check docker machine status - wsl -l -v 
7) to start docker docker machine - docker machine init
7) list all images created for docker check - docker images  ls
Install python. Create your own project/repo and within that then your evnvironment.Activate your environment
Create you own environment 
   # import base image to get python distribution available. So we import base image from docker hub
   FROM python:3.8

Check if Docker is installed and running on your system:
   docker --version

   docker  build --help



8)  image  build 
   Builds an image from the Dockerfile in the current directory (.).
   Build your own image from a Dockerfile:docker build -t <image-name> .
   Tags the image as myapp:latest.
   docker build -t myapp:latest .
   
9)  Uses MyDockerfile instead of the default Dockerfile.
   docker build -t myapp:latest -f MyDockerfile .

10) pull an image from docker hub
    Pull an image from Docker Hub:docker pull <image-name>
   
    docker pull roshanpatil/ai-chatbot:latest

10) Passes a build-time variable MY_VAR to the Dockerfile.
    docker build -t myapp:latest --build-arg MY_VAR=value .

11) Pass Build Arguments
   docker build -t myapp:latest --build-arg MY_VAR=value .
   Passes a build-time variable MY_VAR to the Dockerfile.





No, containers do not "contain" the Docker image itself. Instead, they are instantiated from the image. Here’s how it works:

Relationship Between Docker Images and Containers
Docker Image:

A blueprint or template for the container.
Immutable and contains everything needed to run an application (e.g., code, libraries, dependencies, etc.).
Read-only and can be reused to create multiple containers.
Docker Container:

A runtime instance of a Docker image.
The writable layer allows the container to modify files, save data, or make other changes during its lifecycle without altering the original image.
Lifecycle of a Container
Image -> Container:
When a container is created from an image, the image is used as the base, and a writable layer is added on top of it.

When you create a container, Docker takes the specified image and launches it as a container.
Example:

12) running an image to create and start container
   docker run ubuntu
   Run a Container Use the docker run command to create and start a container:docker run [OPTIONS] <image-name>
   Common Options for docker run
   Interactive Mode: To run the container interactively:docker run -it <image-name> /bin/bash
   Detached Mode: To run the container in the background:docker run -d <image-name>
   Name Your Container: Assign a name to the container:docker run --name <container-name> <image-name>
   Port Mapping: Map container ports to your host:docker run -p <host-port>:<container-port> <image-name>
13) listing all containers -  docker conatianer ls
Changes in the Container:

   Any modifications made inside the container (e.g., installing software or modifying files) are stored in the writable layer specific to that container.
   These changes do not affect the original image.

   Container Independence:
   Each container runs independently, even if created from the same image.
   Multiple containers can be created from a single image, each with its own writable layer and isolated environment.

13) torun an existing container - docker start <container_id_or_name>
13) docker compose up
is used to start all the services defined in a docker-compose.yml file. It ensures that containers are created, started, and linked together as per the configuration.

14) docker compose up -d
Runs containers in the background.

15) docker compose up --build 
    Rebuilds images before starting containers


14) docker compose up --force-recreate
    Forces recreation of containers.
























-------------------------------------------------------------------------------------------



To list images

--------------

podman images
 
Pod/Container Creation (From VSCode at PWD)

----------------------

pip install podman-compose==1.0.6

podman-compose up
 
Container details (VSCode / Powershell)

-----------------

podman ps -a
 
To restart the container incase stopped/exited (VSCode / Powershell)

------------------------

podman start <container id>
 
 
To work with fastapi application (Browser / Postman)

--------------------------------

http://127.0.0.1:8000
http://localhost:8000
 
Swagger UI (Browser)
-------------
http://127.0.0.1:8000/docs
http://localhost:8000/docs
The source for the Linux kernel used in Windows Subsystem for Linux 2 (WSL2) - microsoft/WSL2-Linux-Kernel
 


  


