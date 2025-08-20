# Docker notes
Learning Docker in an easy way

Docker is a popular platform that allows developers to develop, ship, and run applications in containers. Containers are lightweight, isolated environments that package applications and all their dependencies, ensuring consistent behavior across different environments. Docker simplifies the process of creating, deploying, and managing applications by providing a consistent runtime environment regardless of the host system's configuration.

**Key components of Docker include:**

> Docker Engine: The core component responsible for running and managing containers on the host system. It includes a server (daemon) and a REST API that allows users to interact with the Docker environment.

> Docker Image: A read-only template containing all the necessary files, libraries, and dependencies required to run an application. Images act as the building blocks for containers.

> Docker Container: An instance of a Docker image. Containers run in isolation from the host system and other containers but share the host OS's kernel. They are lightweight and can be quickly started, stopped, and moved across different environments.

> Docker Hub: A cloud-based registry provided by Docker where users can find and share Docker images publicly or privately. It's a central repository for Docker images.

![Docker Image](https://github.com/PriyathamVarma/docker/blob/main/Images/docker-1.png)

Using Docker, developers can package their applications and all their dependencies into a container, which can then be easily deployed and executed on any system running Docker, regardless of its underlying infrastructure. This eliminates the "it works on my machine" problem and streamlines the deployment process.

Docker is widely used in various industries, including software development, DevOps, cloud computing, and microservices architecture, as it promotes consistency, scalability, and flexibility in managing applications and services.

## Contents

| S.No | Title | Content |
|-|-|-|
| 01 | [Docker Containers](https://github.com/PriyathamVarma/docker/tree/main/creating_containers_1) | About containers and its commands | 
| 02 | [Docker Networks](https://github.com/PriyathamVarma/docker/tree/main/container_networks) | About Docker networks and basics | 
| 03 | [Docker Images](https://github.com/PriyathamVarma/docker/tree/main/docker_images) | About Docker Images and its commands | 
| 04 | [Docker File](https://github.com/PriyathamVarma/docker/tree/main/docker_file) | About docker files and how to build them | 
| 05 | [Docker Volumes](https://github.com/PriyathamVarma/docker/tree/main/container_volumes) | About docker volumes | 

Useful Resources:

1. [Play with Docker - web-based](https://labs.play-with-docker.com/)
2. [Docker download for desktop](https://www.docker.com/products/docker-desktop/)

