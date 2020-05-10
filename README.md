# docker

# Steps to install Docker on Oracle 7+
https://oracle-base.com/articles/linux/docker-install-docker-on-oracle-linux-ol7
https://stackoverflow.com/questions/48957195/how-to-fix-docker-got-permission-denied-issue


# docker version
```
Client:
 Version:           18.09.1-ol
 API version:       1.39
 Go version:        go1.10.8
 Git commit:        b2a1f2a
 Built:             Sat Feb  9 02:05:49 2019
 OS/Arch:           linux/amd64
 Experimental:      false

Server: Docker Engine - Community
 Engine:
  Version:          18.09.1-ol
  API version:      1.39 (minimum version 1.12)
  Go version:       go1.10.8
  Git commit:       b2a1f2a
  Built:            Sat Feb  9 01:54:37 2019
  OS/Arch:          linux/amd64
  Experimental:     false
  Default Registry: docker.io
  ```


# docker run hello-world
```
Unable to find image 'hello-world:latest' locally
Trying to pull repository docker.io/library/hello-world ...
latest: Pulling from docker.io/library/hello-world
0e03bdcc26d7: Pull complete
Digest: sha256:8e3114318a995a1ee497790535e7b88365222a21771ae7e53687ad76563e8e76
Status: Downloaded newer image for hello-world:latest

Hello from Docker!
This message shows that your installation appears to be working correctly.

To generate this message, Docker took the following steps:
 1. The Docker client contacted the Docker daemon.
 2. The Docker daemon pulled the "hello-world" image from the Docker Hub.
    (amd64)
 3. The Docker daemon created a new container from that image which runs the
    executable that produces the output you are currently reading.
 4. The Docker daemon streamed that output to the Docker client, which sent it
    to your terminal.

To try something more ambitious, you can run an Ubuntu container with:
 $ docker run -it ubuntu bash

Share images, automate workflows, and more with a free Docker ID:
 https://hub.docker.com/

For more examples and ideas, visit:
 https://docs.docker.com/get-started/
```

```
$ docker ps
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS              PORTS               NAMES

$ docker ps -a
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS                      PORTS               NAMES
88898a9f491f        hello-world         "/hello"            7 minutes ago       Exited (0) 7 minutes ago                        gallant_lumiere
3f864b592ac0        hello-world         "/hello"            18 minutes ago      Exited (0) 18 minutes ago                       clever_jennings
```

# List Docker Images

```
docker images
REPOSITORY          TAG                 IMAGE ID            CREATED             SIZE
hello-world         latest              bf756fb1ae65        4 months ago        13.3kB
```

# Highlights

- docker run to run a new container

- docker ps to see running and stopped containers

- docker images to see info about images

- Intsalling docker gives you the client and Daemon, client makes API call to Daemon, Daemon implements the Docker Remote API, docker run starts a new container
- Docker Hub is a docker image registry, a place where to can store images right a place where we want to use containers

# Containers and Images

Images = Stopped Containers
Containers = Running Images


```
docker pull alpine
Using default tag: latest
Trying to pull repository docker.io/library/alpine ...
latest: Pulling from docker.io/library/alpine
cbdbe7a5bc2a: Pull complete
Digest: sha256:9a839e63dad54c3a6d1834e29692c8492d93f90c59c978c1ed79109ea4fb9a54
Status: Downloaded newer image for alpine:latest
```

# Get the specific version of Images

```
docker pull ubuntu
Using default tag: latest
Trying to pull repository docker.io/library/ubuntu ...
latest: Pulling from docker.io/library/ubuntu
d51af753c3d3: Pull complete
fc878cd0a91c: Pull complete
6154df8ff988: Pull complete
fee5db0ff82f: Pull complete
Digest: sha256:747d2dbbaaee995098c9792d99bd333c6783ce56150d1b11e333bbceed5c54d7
Status: Downloaded newer image for ubuntu:latest
```

```
docker pull ubuntu:16.04
Trying to pull repository docker.io/library/ubuntu ...
16.04: Pulling from docker.io/library/ubuntu
e92ed755c008: Pull complete
b9fd7cb1ff8f: Pull complete
ee690f2d57a1: Pull complete
53e3366ec435: Pull complete
Digest: sha256:db6697a61d5679b7ca69dbde3dad6be0d17064d5b6b0e9f7be8d456ebb337209
Status: Downloaded newer image for ubuntu:16.04
```

```
docker images
REPOSITORY          TAG                 IMAGE ID            CREATED             SIZE
ubuntu              16.04               005d2078bdfa        2 weeks ago         125MB
ubuntu              latest              1d622ef86b13        2 weeks ago         73.9MB
alpine              latest              f70734b6a266        2 weeks ago         5.61MB
hello-world         latest              bf756fb1ae65        4 months ago        13.3kB
```


