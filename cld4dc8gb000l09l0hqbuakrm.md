# Docker Interview Questions

---

**Introduction to Docker:**

Docker is a very popular and powerful open-source containerization platform that is used for building, deploying, and running applications. Docker allows you to decouple the application/software from the underlying infrastructure.

## Docker Basic Interview Questions

### 1\. What is a Container?

A container is a standard unit of software bundled with dependencies so that applications can be deployed fast and reliably b/w different computing platforms.

* Docker can be visualized as a big ship (docker) carrying huge boxes of products (containers).
    
* A Docker container doesn’t require the installation of a separate operating system. Docker just relies or makes use of the kernel’s resources and its functionality to allocate them for the CPU and memory it relies on the kernel’s functionality and uses resource isolation for CPU and memory, and separate namespaces to isolate the application’s view of the OS (operating system).
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1674209272648/51141cb8-9cb9-42cf-8267-61e57ec31768.png align="center")

### 2\. Why Learn Docker?

Application development is a lot more than just writing code! They involve a lot of behind-the-scenes things like the usage of multiple frameworks and architectures for every stage of its lifecycle which makes the process more complex and challenging. Using the nature of containerization helps developers to simplify and efficiently accelerate the application workflow along with giving them the liberty to develop using their own choice of technology and development environments.

* All these aspects form the core part of DevOps which becomes all the more important for any developer to know these to improve productivity and fasten the development along with keeping in mind the factors of application scalability and more efficient resource management.
    
* Imagine containers as a very lightweight pre-installed box with all the packages, dependencies, and software required by your application, just deploy to production with minimal configuration changes.
    
* Lots of companies like PayPal, Spotify, Uber, etc use Docker to simplify operations and to bring the infrastructure and security closer to make more secure applications.
    
* Being portable, Containers can be deployed on multiple platforms like bare instances, virtual machines, Kubernetes platform etc. as per requirements of scale or desired platform.
    

### 3\. Can you tell me something about the docker container?

* <mark>In simplest terms, docker containers consist of applications and all their dependencies.</mark>
    
* They share the kernel and system resources with other containers and run as isolated systems in the host operating system.
    
* <mark>The main aim of docker containers is to get rid of the infrastructure dependency while deploying and running applications.</mark> This means that any containerized application can run on any platform irrespective of the infrastructure being used beneath.
    
* Technically, they are just the runtime instances of docker images.
    

### 4\. What are docker images?

<mark>They are executable packages(bundled with application code &amp; dependencies, software packages, etc.) to create containers.</mark> Docker images can be deployed to any docker environment and the containers can be spun up there to run the application.

### 5\. What is a DockerFile?

<mark>It is a text file that has all commands which need to be run to build a given image.</mark>

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1674197149760/fb3db320-8d6c-4c14-b304-6451a2da6a92.png align="center")

### 6\. Can you tell what is the functionality of a hypervisor?

<mark>A hypervisor is a software that makes virtualization happen which is sometimes referred to as the Virtual Machine Monitor.</mark> This divides the resources of the host system and allocates them to each guest environment installed.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1674197288936/9df9f367-7e42-4470-a833-2146b64fdb31.png align="center")

This means that multiple OS can be installed on a single host system. **Hypervisors are of 2 types:**

* **Native Hypervisor:** This type is also called a Bare-metal Hypervisor and runs directly on the underlying host system which also ensures direct access to the host hardware which is why it does not require base OS.
    
* **Hosted Hypervisor:** This type makes use of the underlying host operating system which has the existing OS installed.
    

### 7\. What can you tell about Docker Compose?

<mark>It is a YAML file consisting of all the details regarding various services, networks, and volumes that are needed for setting up the Docker-based application. So, docker-compose is used for creating multiple containers, hosting them and establishing communication between them.</mark> For communication amongst the containers, ports are exposed by every container.

### 8\. Can you tell me something about the docker namespace?

<mark>A namespace is a Linux feature that ensures OS resources partition in a mutually exclusive manner. This forms the core concept behind containerization as namespaces introduce a layer of isolation amongst the containers</mark>. In docker, the namespaces ensure that the containers are portable and they don't affect the underlying host. Examples of namespace types that are currently being supported by Docker – are PID, Mount, User, Network, and IPC.

### 9\. What is the docker command that lists the status of all docker containers?

To get the status of all the containers, we run the below command: docker ps -a

### 10\. What is a docker image registry?

* A Docker image registry, in simple terms, is an area where docker images are stored. Instead of converting the applications to containers every time, a developer can directly use the images stored in the registry.
    
* This image registry can either be public or private and Docker hub is the most popular and famous public registry available.
    

### 11\. How many Docker components are there?

There are three docker components, they are - Docker Client, Docker Host, and Docker Registry.

* **Docker Client:** <mark>This component performs “build” and “run” operations to open communication with the docker host</mark>.
    
* **Docker Host:** <mark>This component has the main docker daemon and hosts containers and their associated images. The daemon establishes a connection with the docker registry</mark>.
    
* **Docker Registry:** <mark>This component stores the docker images. There can be a public registry or a private one. The most famous public registries are Docker Hub and Docker Cloud.</mark>
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1674205694242/55f2a03a-3df4-4839-80af-21e7eb6fc171.png align="center")

### 12\. What is a Docker Hub?

* It is a public cloud-based registry provided by Docker for storing public images of the containers along with the provision of finding and sharing them.
    
* The images can be pushed to Docker Hub through the **docker push** command.
    

### 13\. What command can you run to export a docker image as an archive?

This can be done using the docker save command and the syntax is: **<mark>docker save -o &lt;exported_name&gt;.tar</mark>**

### 14\. What command can be run to import a pre-exported Docker image into another Docker host?

This can be done using the docker load command and the syntax is **<mark>docker load -i &lt;export_image_name&gt;.tar</mark>**

### 15\. What command is used to check for the version of the docker client and server?

* The command used to get all version information of the client and server is the **docker version**.
    
* To get only the server version details, we can run **docker version --format '{{.Server.Version}}'**
    

---

## DockerIntermediate Interview Questions

### 1\. Differentiate between virtualization and containerization.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1674206162865/81006ce2-6daa-4ebc-8460-1bd08bcf3edc.png align="center")

### 2\. Differentiate between COPY and ADD commands that are used in a Dockerfile?

Both the commands have similar functionality, but COPY is preferred because of its higher transparency level than that ADD. COPY provides just the basic support of copying local files into the container whereas ADD provides additional features like remote URL and tar extraction support.

### 3\. Can a container restart by itself?

Yes, it is possible only while using certain docker-defined policies while using the docker run command. The following are the available policies:

* **Off**: In this, the container won’t be restarted in case it's stopped or fails.
    
* **On-failure:** Here, the container restarts by itself only when it experiences failures not associated with the user.
    
* **Unless-stopped:** Using this policy, ensures that a container can restart only when the command is executed to stop it by the user.
    
* **Always:** Irrespective of the failure or stopping, the container always gets restarted in this type of policy.
    
* These policies can be used as: **docker run -dit --restart \[restart-policy-value\] \[container\_name\]**
    

### 4\. Can you tell the differences between a docker Image and a Layer?

**Image:** This is built up from a series of read-only layers of instructions. An image corresponds to the docker container and is used for speedy operation due to the caching mechanism of each step.

**Layer:** Each layer corresponds to an instruction of the image’s Dockerfile. In simple words, the layer is also an image but it is the image of the instructions run.

Consider the example Dockerfile below:-

> FROM ubuntu:18.04
> 
> COPY . /myapp
> 
> RUN make /myapp
> 
> CMD python /myapp/app.py
> 
> Importantly, each layer is only a set of differences from the layer before it.

* The result of building this docker file is an image. Whereas the instructions present in this file add the layers to the image. The layers can be thought of as intermediate images. In the example above, there are 4 instructions, hence 4 layers are added to the resultant image.
    

### 5\. What is the purpose of the volume parameter in a docker run command?

* The syntax of docker run when using the volumes is: **docker run -v host\_path:docker\_path &lt;container\_name&gt;**
    
* <mark>The volume parameter is used for syncing a directory of a container with any of the host directories</mark>. Consider the below command as an example: **docker run - v /data/app:usr/src/app myapp**
    
* The above command mounts the directory /data/app in the host to the usr/src/app directory. We can sync the container with the data files from the host without needing to restart it.
    
* This also ensures data security in cases of container deletion. This ensures that even if the container is deleted, the data of the container exists in the volume-mapped host location making it the easiest way to store the container data.
    

### 6\. Where are docker volumes stored in docker?

Volumes are created and managed by Docker and cannot be accessed by non-docker entities. <mark>They are stored in the Docker host filesystem at </mark> **<mark>/var/lib/docker/volumes/</mark>**

### 7\. What does the docker info command do?

<mark>The command gets detailed information about Docker installed on the host system</mark>. The information can be like what is the number of containers or images and in what state they are running and hardware specifications like total memory allocated, speed of the processor, kernel version, etc.

### 8\. Can you tell what are the purposes of the up, run, and start commands of docker-compose?

* Using the **up** command for keeping a docker-compose up (ideally at all times), we can start or restart all the networks, services, and drivers associated with the app that are specified in the docker-compose.yml file. Now if we are running the docker-compose up in the “attached” mode then all the logs from the containers would be accessible to us. In case the docker-compose is run in the “detached” mode, then once the containers are started, it just exits and shows no logs.
    
* Using the **run** command, the docker-compose can run one-off or ad-hoc tasks based on the business requirements. Here, the service name has to be provided and the docker starts only that specific service and also the other services to which the target service is dependent (if any).
    
    This command helps test the containers and also performs tasks such as adding or removing data to the container volumes etc.
    
* Using the **start** command, only those containers can be restarted which were already created and then stopped. This is not useful for creating new containers on its own.
    

### 9\. What are the basic requirements for the docker to run on any system?

Docker can run on both Windows and Linux platforms.

* For the Windows platform, docker at least needs Windows 10 64bit with 2GB RAM space. For the lower versions, docker can be installed by taking the help of the toolbox. Docker can be downloaded from [https://docs.docker.com/docker for- **windows/**](https://docs.docker.com/desktop/get-started/) website.
    
* For Linux platforms, Docker can run on various Linux flavors such as
    
    > Ubuntu=12.04, Fedora &gt;=19, RHEL &gt;=6.5, CentOS &gt;=6 etc.
    

### 10\. List the most commonly used instructions in Dockerfile?

* **FROM:** This is used to set the base image for upcoming instructions. A docker file is considered to be valid if it starts with the FROM instruction.
    
* **LABEL:** This is used for image organization based on projects, modules, or licensing. It also helps in automation as we specify a key-value pair while defining a label that can be later accessed and handled programmatically.
    
* **RUN:** This command is used to execute instructions following it on the top of the current image in a new layer. Note that with each RUN command execution, we add layers on top of the image and then use that in subsequent steps.
    
* **CMD:** This command is used to provide default values of an executing container. In cases of multiple CMD commands, the last instruction would be considered.
    

### 11\. What is the way to establish communication between the docker host and the Linux host?

This can be done using networking by identifying the **“ipconfig”** on the docker host. This command ensures that an ethernet adapter is created as long as the docker is present in the host.

### 12\. What is the best way of deleting a container?

We need to follow the following two steps for deleting a container:

* docker stop &lt;container\_id&gt;
    
* docker rm &lt;container\_id&gt;
    

### 13\. Can you tell the difference between CMD and ENTRYPOINT?

**CMD** command provides executable defaults for an executing container. In case the executable has to be omitted then the usage of ENTRYPOINT instruction along with the JSON array format has to be incorporated.

**ENTRYPOINT** specifies that the instruction within it will always be run when the container starts.

This command provides an option to configure the parameters and the executables. If the DockerFile does not have this command, then it would still get inherited from the base image mentioned in the FROM instruction.

* The most commonly used ENTRYPOINT is **/bin/sh or /bin/bash** for most of the base images.
    
* As part of good practices, every DockerFile should have at least one of these two commands.
    

---

## Docker Advanced Interview Questions

### 01\. Can we use JSON instead of YAML while developing a docker-compose file in Docker?

Yes! It can be used. To run docker-compose with JSON, **docker-compose -f docker-compose.json up** can be used.

### 02\. How many containers you can run in docker and what are the factors influencing this limit?

There is no clearly defined limit to the number of containers that can be run within docker. But it all depends on the limitations - more specifically hardware restrictions. The size of the app and the CPU resources available are 2 important factors influencing this limit. In case your application is not very big and you have abundant CPU resources, then we can run a huge number of containers.

### 03\. Describe the lifecycle of a Docker Container?

The different stages of the docker container from the start of creating it to its end are called the docker container life cycle. The most important stages are:

* **Created**: This is the state where the container has just been created new but has not started yet.
    
* **Running:** In this state, the container would be running with all its associated processes.
    
* **Paused:** This state happens when the running container has been paused.
    
* **Stopped:** This state happens when the running container has been stopped.
    
* **Deleted:** In this, the container is in a dead state.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1674208312573/30537ace-a0a0-4636-9c32-68715826fbc5.png align="center")

### 04\. How to use docker for multiple application environments?

* The docker-compose feature of docker will come to help here. In the docker-compose file, we can define multiple services, networks, and containers along
    
    with the volume mapping in a clean manner, and then we can just call the command **“docker-compose up”**.
    
* When there are multiple environments involved - it can be either dev, staging, uat, or production servers, we would want to define the server-specific dependencies and processes for running the application. In this case, we can go ahead with creating environment-specific docker-compose files of the name “**docker-compose.{environment}.yml**” and then based on the environment, we can set up and run the application.
    

### 05\. How will you ensure that container 1 runs before container 2 while using docker-compose?

Docker-compose does not wait for any container to be “ready” before going ahead with the next containers. To achieve the order of execution, we can use:

The “depends\_on” which got added in version 2 of docker-compose can be used as shown in a sample docker-compose.yml file below:

```yaml
version: "2.4"
services:
 backend:
  build: .
  depends_on:
  - db
db:
 image: postgres
```

The introduction of service dependencies has various causes and effects:

* The docker-compose up command starts and runs the services in the dependency order specified. For the above example, the DB container is started before the backend.
    
* docker-compose up SERVICE\_NAME by default includes the dependencies associated with the service. In the given example, running docker-compose up backend creates and starts DB (dependency of backend).
    
* Finally, the command docker-compose stop also stops the services in the order of the dependency specified. For the given example, the backend service is stopped before the DB service.
    

---

# Conclusion

DevOps technologies are growing at an exponential pace. As the systems are being more and more distributed, developers have turned towards containerization because of the need to develop software faster and maintain them better. They also aid in easier and faster continuous integration and deployment process which is why these technologies have experienced tremendous growth.

Docker is the most famous and popular tool for achieving the purpose of containerization and continuous integration/development and also for continuous deployment due to its great support for pipelines. With the growing ecosystem, docker has proven itself to be useful to operate on multiple use cases thereby making it all the more exciting to learn it!

To build a good DockerFile: [https://docs.docker.com/engine/reference/builder/](https://docs.docker.com/engine/reference/builder/)

---