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

# Remove Docker Image

```
docker rmi ubuntu:16.04
Untagged: ubuntu:16.04
Untagged: ubuntu@sha256:db6697a61d5679b7ca69dbde3dad6be0d17064d5b6b0e9f7be8d456ebb337209
Deleted: sha256:005d2078bdfab5066ae941cea93f644f5fd25521849c870f4e1496f4526d1d5b
Deleted: sha256:a83c92a7c7a0f4a52fc74fa38496be9a5e6b738bc5fd5d60e54768fed238c173
Deleted: sha256:c6a36d55655e576fc8166a32fd05e281d03bedc26b1118902e92e7ba421dfa72
Deleted: sha256:d1c997f15060e07ff557383387d6839e0377873837025fc843fa5d94bea2c4e5
Deleted: sha256:b592b5433bbffb04389a0e6349cdba6af8d006779bbb93beb69aa77d59133be4


docker images
REPOSITORY          TAG                 IMAGE ID            CREATED             SIZE
ubuntu              latest              1d622ef86b13        2 weeks ago         73.9MB
alpine              latest              f70734b6a266        2 weeks ago         5.61MB
hello-world         latest              bf756fb1ae65        4 months ago        13.3kB
```

```
run -d --name web -p 80:8080 nigelpoulton/pluralsight-docker-ci
Unable to find image 'nigelpoulton/pluralsight-docker-ci:latest' locally
Trying to pull repository docker.io/nigelpoulton/pluralsight-docker-ci ...
latest: Pulling from docker.io/nigelpoulton/pluralsight-docker-ci
729ec3a6ada3: Pull complete
f0a3eea3dca0: Pull complete
e07851c50ad6: Pull complete
f78e7cd1f8dc: Pull complete
7cad1fbd2f07: Pull complete
22835c51693f: Pull complete
Digest: sha256:61bc64850a5f2bfbc65967cc33feaae8a77c8b49379c55aaf05bb02dcee41451
Status: Downloaded newer image for nigelpoulton/pluralsight-docker-ci:latest
4050b78fd240763286cc74140163dedb68978bac5d108fdb17550e80c57f911c
```

then simply hit the ``http://ech-10-168-129-9``,  where ``ech-10-168-129-9`` is the docker host.

```
docker ps
CONTAINER ID        IMAGE                                COMMAND                  CREATED             STATUS              PORTS                  NAMES
4050b78fd240        nigelpoulton/pluralsight-docker-ci   "/bin/sh -c 'cd /src…"   4 minutes ago       Up 4 minutes        0.0.0.0:80->8080/tcp   web
```

# Stop the container

```
docker stop web
web
```

Now hit the ``http://ech-10-168-129-9``, you should see things are not working !

Now again start the container

``
docker start web
web
```

```
docker run -it --name temp ubuntu:latest /bin/bash
root@2381527f69b1:/#
```

To get out of CRTL + P + Q 

root@2381527f69b1:/# [dc-user@ech-10-168-129-9 ~]$

docker ps
CONTAINER ID        IMAGE                                COMMAND                  CREATED             STATUS              PORTS                  NAMES
2381527f69b1        ubuntu:latest                        "/bin/bash"              4 minutes ago       Up 4 minutes                               temp
4050b78fd240        nigelpoulton/pluralsight-docker-ci   "/bin/sh -c 'cd /src…"   30 minutes ago      Up 5 minutes        0.0.0.0:80->8080/tcp   web
```


