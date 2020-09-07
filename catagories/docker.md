# Docker

<details>
<summary>什么是Docker，用来做什么?</summary><br><b>
Docker container image is a lightweight, standalone, executable package of software that includes everything needed to run an application: code, runtime, system tools, system libraries and settings.
</b></details>

<details>
<summary>容器和虚拟机有什么区别?</summary><br><b>

The primary difference between containers and VMs is that containers allow you to virtualize
multiple workloads on the operating system while in the case of VMs the hardware is being virtualized to
run multiple machines each with its own OS.

- Containers don't require an entire guest operating system as VMs
- It's usually takes a few seconds to set up a container as opposed to VMs which can take minutes or at least more time than containers as there is an entire OS to boot and initialize as opposed to container where you mainly lunch the app itself
- Docker is one of the technologies allowing you to manage containers - run multiple containers on a host, move containers between hosts, etc.
  </b></details>

<details>
<summary>In which scenarios would you use containers and in which you would prefer to use VMs?</summary><br><b>

You should choose VMs when:

- you need run an application which requires all the resources and functionalities of an OS
- you need full isolation and security

You should choose containers when:

- you need a lightweight solution
- Running multiple versions or instances of a single application
  </b></details>

<details>
<summary>解释Docker的架构</summary><br><b>
</b></details>

<details>
<summary>详细说明当运行`docker run hello-world`时发生了什么?</summary><br><b>

1. Docker CLI 将请求发给 Docker Daemon
2. Docker daemon 从 Docker Hub 下载镜像
3. Docker daemon 使用镜像创建一个容器
4. Docker daemon 重定向输出从容器内到 Docker CLI，Docker CLI 再将该输出重定向到标准输出
   </b></details>

<details>
<summary>How would you transfer data from one container into another?</summary><br><b>
</b></details>

<details>
<summary>What happens to data of the container when a container exists?</summary><br><b>
</b></details>

<details>
<summary>解释以下命令的作用:

- docker run
- docker rm
- docker ps
- docker pull
- docker build
- docker commit</summary><br><b>
  </b></details>

<details>
<summary>如何删除旧的不在运行的容器?</summary><br><b>

1. 方法一：指定要删除的容器`docker rm <container-id>`
2. 方法二：删除所有停止的容器、所有没使用的镜像和没用的网络`docker system prune`
3. 方法三：删除所有容器，若容器在运行会跳过`docker rm $(docker ps -aq)`
   </b></details>

##### Dockerfile

<details>
<summary>Dockerfile是什么</summary><br><b>

Docker can build images automatically by reading the instructions from a Dockerfile. A Dockerfile is a text document that contains all the commands a user could call on the command line to assemble an image.
</b></details>

<details>
<summary>What is the difference between ADD and COPY in Dockerfile?</summary><br><b>

COPY takes in a src and destination. It only lets you copy in a local file or directory from your host (the machine building the Docker image) into the Docker image itself.
ADD lets you do that too, but it also supports 2 other sources. First, you can use a URL instead of a local file / directory. Secondly, you can extract a tar file from the source directly into the destination.
Although ADD and COPY are functionally similar, generally speaking, COPY is preferred. That’s because it’s more transparent than ADD. COPY only supports the basic copying of local files into the container, while ADD has some features (like local-only tar extraction and remote URL support) that are not immediately obvious.
</b></details>

<details>
<summary>What is the difference between CMD and RUN in Dockerfile?</summary><br><b>

RUN lets you execute commands inside of your Docker image. These commands get executed once at build time and get written into your Docker image as a new layer.
CMD is the command the container executes by default when you launch the built image. A Dockerfile can only have one CMD.
You could say that CMD is a Docker run-time operation, meaning it’s not something that gets executed at build time. It happens when you run an image. A running image is called a container.
</b></details>

<details>
<summary>Do you perform any checks or testing related to your Dockerfile?</summary><br><b>

A common answer to this is to use [hadolint](https://github.com/hadolint/hadolint) project which is a linter based on Dockerfile best practices.
</b></details>

<details>
<summary>Explain what is Docker compose and what is it used for</summary><br><b>

Compose is a tool for defining and running multi-container Docker applications. With Compose, you use a YAML file to configure your application’s services. Then, with a single command, you create and start all the services from your configuration.

For example, you can use it to set up ELK stack where the services are: elasticsearch, logstash and kibana. Each running in its own container.
</b></details>

<details>
<summary>Describe the process of using Docker Compose</summary><br><br>

- Define the services you would like to run together in a docker-compose.yml file
- Run `docker-compose up` to run the services
  </b></details>

<details>
<summary>Explain Docker interlock</summary><br><b>
</b></details>

<details>
<summary>Where can you store Docker images?</summary><br><b>
</b></details>

<details>
<summary>What is Docker Hub?</summary><br><b>
</b></details>

<details>
<summary>What is the difference between Docker Hub and Docker cloud?</summary><br><b>

Docker Hub is a native Docker registry service which allows you to run pull
and push commands to install and deploy Docker images from the Docker Hub.

Docker Cloud is built on top of the Docker Hub so Docker Cloud provides
you with more options/features compared to Docker Hub. One example is
Swarm management which means you can create new swarms in Docker Cloud.
</b></details>

<details>
<summary>What is Docker Repository?</summary><br><b>
</b></details>

<details>
<summary>Explain image layers</summary><br><b>

A Docker image is built up from a series of layers. Each layer represents an instruction in the image’s Dockerfile. Each layer except the very last one is read-only.
Each layer is only a set of differences from the layer before it. The layers are stacked on top of each other. When you create a new container, you add a new writable layer on top of the underlying layers. This layer is often called the “container layer”. All changes made to the running container, such as writing new files, modifying existing files, and deleting files, are written to this thin writable container layer.
The major difference between a container and an image is the top writable layer. All writes to the container that add new or modify existing data are stored in this writable layer. When the container is deleted, the writable layer is also deleted. The underlying image remains unchanged.
Because each container has its own writable container layer, and all changes are stored in this container layer, multiple containers can share access to the same underlying image and yet have their own data state.
</b></details>

<a name="docker-advanced"></a>

<details>
<summary>What best practices are you familiar related to working with containers?</summary><br><b>
</b></details>

<details>
<summary>How do you manage persistent storage in Docker?</summary><br><b>
</b></details>

<details>
<summary>How can you connect from the inside of your container to the localhost of your host, where the container runs?</summary><br><b>
</b></details>

<details>
<summary>How do you copy files from Docker container to the host and vice versa?</summary><br><b>
</b></details>
