# **Docker Introduction on Usage**

---

### all information below have been gather from the following urls.

- [docker-instructions-commands](https://www.geeksforgeeks.org/docker-instruction-commands/)
- [introduction-to-docker](introduction-to-docker)

## Difference between Docker Containers and Virtual Machines
### 1. **Docker Containers**
Docker Containers contain binaries, libraries, and configuration files along with the application itself.
They don’t contain a guest OS for each container and rely on the underlying OS kernel, which makes the containers lightweight.
Containers share resources with other containers in the same host OS and provide OS-level process isolation.
### 2. **Virtual Machines**
Virtual Machines (VMs) run on Hypervisors, which allow multiple Virtual Machines to run on a single machine along with its own operating system.
Each VM has its own copy of an operating system along with the application and necessary binaries, which makes it significantly larger and it requires more resources.
They provide Hardware-level process isolation and are slow to boot.

## Important Terminologies in Docker 
### **1. Docker Image**
It is a file, comprised of multiple layers, used to execute code in a Docker container.
They are a set of instructions used to create docker containers.
## 2. **Docker Container**
It is a runtime instance of an image.
Allows developers to package applications with all parts needed such as libraries and other dependencies.
## 3. **Docker file**
It is a text document that contains necessary commands which on execution helps assemble a Docker Image.
Docker image is created using a Docker file.
## 4. **Docker Engine**
The software that hosts the containers is named Docker Engine.
Docker Engine is a client-server based application
The docker engine has 3 main components:
Server: It is responsible for creating and managing Docker images, containers, networks, and volumes on the Docker. It is referred to as a daemon process.
REST API: It specifies how the applications can interact with the Server and instructs it what to do.
Client: The Client is a docker command-line interface (CLI), that allows us to interact with Docker using the docker commands.
## 5. **Docker Hub**
Docker Hub is the official online repository where you can find other Docker Images that are available for use.
It makes it easy to find, manage, and share container images with others.

---

Docker is an open-source project that automates the deployment of applications as movable, independent containers that can run locally or in the cloud. You can divide your applications from your infrastructure with the help of Docker, allowing for quick software delivery and it also allows you to manage your infrastructure in the same ways that you manage your applications.

The number of commands found in docker is very huge in number, but we will be looking at the top commands in docker.

### Docker Commands:
1. docker run: This command is used to run a container from an image.

```$ docker run <name_of_the_container>```

2. docker pull: This command allows you to pull any image which is present at the official registry of docker, Docker hub. By default, it pulls the latest image, but you can also mention the version of the image.

```$ docker pull <image_name>```

3. docker ps: This command (by default) shows us a list of all the running containers. We can use various flags with it.

-a flag:  shows us all the containers, stopped or running.
-l flag: shows us the latest container.
-q flag: shows only the Id of the containers. 

```$ docker ps [options..]```

4. docker stop: This command allows you to stop a container if it has crashed or you want to switch to another one.

```$ docker stop <container_ID>```

5. docker start: Suppose you want to start the stopped container again, you can do it with the help of this command.

```$ docker start <container_ID>```

6. docker rm: To delete a container. By default when we a container is created, it gets an ID as well as an imaginary name such as confident_boyd, heuristic_villani, etc. You can either mention the container name or its ID.

Some important flags:

-f flag: remove the container forcefully.
-v flag: remove the volumes.
-l flag: remove the specific link mentioned.

```$ docker rm {options} <container_name or ID> ```

7. docker images: Lists all the pulled images which are present in our system.

```$ docker images```

8. docker exec: This command allows us to run new commands in a running container. This command only works until the container is running, after the container restarts, this command does not restart.

Some important flags:

-d flag: for running the commands in the background.
-i flag: it will keep STDIN open even when not attached.
-e flag: sets the environment variables 

```$ docker exec {options}```

1. docker ports (port mapping): In order to access the docker container from the outside world, we have to map the port on our host( Our laptop for example), to the port on the container. This is where port mapping comes into play.

```$ docker run -d -p <port_on_host> <port_on_container> Container_name```

So these were the 9 most basic docker commands that every beginner must know. Containerization is a very vast topic but you can start from the very basic commands and by practicing them daily you can master them.
