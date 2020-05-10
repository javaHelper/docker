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
