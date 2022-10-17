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

```
docker start web
web
```

```
docker run -it --name temp ubuntu:latest /bin/bash
root@2381527f69b1:/#
```

To get out of CRTL + P + Q 

```
root@2381527f69b1:/# [user@10-168-129-9 ~]$

docker ps
CONTAINER ID        IMAGE                                COMMAND                  CREATED             STATUS              PORTS                  NAMES
2381527f69b1        ubuntu:latest                        "/bin/bash"              4 minutes ago       Up 4 minutes                               temp
4050b78fd240        nigelpoulton/pluralsight-docker-ci   "/bin/sh -c 'cd /src…"   30 minutes ago      Up 5 minutes        0.0.0.0:80->8080/tcp   web
```


```
docker stop $(docker ps -aq)
2381527f69b1
4050b78fd240
88898a9f491f
3f864b592ac0
```

Gives us all -a = all, -q = quietly

```
docker rm  $(docker ps -aq)
2381527f69b1
4050b78fd240
88898a9f491f
3f864b592ac0
```

```
docker rmi $(docker images -q)
Untagged: ubuntu:latest
Untagged: ubuntu@sha256:747d2dbbaaee995098c9792d99bd333c6783ce56150d1b11e333bbceed5c54d7
Deleted: sha256:1d622ef86b138c7e96d4f797bf5e4baca3249f030c575b9337638594f2b63f01
Deleted: sha256:279e836b58d9996b5715e82a97b024563f2b175e86a53176846684f0717661c3
Deleted: sha256:39865913f677c50ea236b68d81560d8fefe491661ce6e668fd331b4b680b1d47
Deleted: sha256:cac81188485e011e56459f1d9fc9936625a1b62cacdb4fcd3526e5f32e280387
Deleted: sha256:7789f1a3d4e9258fbe5469a8d657deb6aba168d86967063e9b80ac3e1154333f
Untagged: alpine:latest
Untagged: alpine@sha256:9a839e63dad54c3a6d1834e29692c8492d93f90c59c978c1ed79109ea4fb9a54
Deleted: sha256:f70734b6a266dcb5f44c383274821207885b549b75c8e119404917a61335981a
Deleted: sha256:3e207b409db364b595ba862cdc12be96dcdad8e36c59a03b7b3b61c946a5741a
Untagged: nigelpoulton/pluralsight-docker-ci:latest
Untagged: nigelpoulton/pluralsight-docker-ci@sha256:61bc64850a5f2bfbc65967cc33feaae8a77c8b49379c55aaf05bb02dcee41451
Deleted: sha256:dd7a37fe7c1e6f3b9bcd1c51cad0a54fde3f393ac458af3b009b2032978f599d
Deleted: sha256:62c2dc8575cf79fddcbf8466311d893100d89d8fe30532cd8949a6399bf0c59e
Deleted: sha256:41d87f201eb33b39af235cb7aae8dce404407dbff9654886854ef076fedec0ed
Deleted: sha256:fec1957285f8b705269c691bd78a70584888e4a7674a7f3e74351f131926edcf
Deleted: sha256:27a18cba123036ad9cedaeed9dc75d3a55c81bf2da5c21837a2f23583882aee4
Deleted: sha256:937d6f78d3ffb0b5bd95a1e8a39974008915ac044f7c7c89a18962efe973ca81
Deleted: sha256:9e607bb861a7d58bece26dd2c02874beedd6a097c1b6eca5255d5eb0d2236983
Untagged: hello-world:latest
Untagged: hello-world@sha256:8e3114318a995a1ee497790535e7b88365222a21771ae7e53687ad76563e8e76
Deleted: sha256:bf756fb1ae65adf866bd8c456593cd24beb6a0a061dedf42b26a993176745f6b
Deleted: sha256:9c27e219663c25e0f28493790cc0b88bc973ba3b1686355f221c38a36978ac63


[user@10-168-129-9 ~]$ docker images
REPOSITORY          TAG                 IMAGE ID            CREATED             SIZE
```

# Termonology

- A cluster = A swarm
- Engines in swarn run in swarn mode

Manager nodes maintain the swarm

 - H/A  - recommands 3 or 5
 - Only one is leader
 
 worker nodes execute tasks
 
 Services
 - Declarative & saclable

Tasks
- Assigned to workers

# Mongo Setup

```
 docker pull mongo
Using default tag: latest
Trying to pull repository docker.io/library/mongo ...
latest: Pulling from docker.io/library/mongo
23884877105a: Pull complete
bc38caa0f5b9: Pull complete
2910811b6c42: Pull complete
36505266dcc6: Pull complete
a4d269900d94: Pull complete
5e2526abb80a: Pull complete
d3eece1f39ec: Pull complete
358ed78d3204: Pull complete
1a878b8604ae: Pull complete
dde03a2883d0: Pull complete
4ffe534daa34: Pull complete
f164ba21e17c: Pull complete
6494c387442c: Pull complete
Digest: sha256:50d7b0aef8165b542612a4f57fd7b70703eb7db095588fb76e5a3f01cda396a0
Status: Downloaded newer image for mongo:latest

```


```
docker run --name CONTAINERNAME --restart=always -d -p 8080:8080 mongo mongod --auth
b9d1277dbc7aaa028489c3f72f4b3ab22bd6487654d44c44d1cbf242540ececc
[dc-user@ech-10-168-129-9 PRATEEK]$ sudo docker exec -i -t CONTAINERNAME bash
[sudo] password for dc-user:
root@b9d1277dbc7a:/# mongo
MongoDB shell version v4.2.6
connecting to: mongodb://127.0.0.1:27017/?compressors=disabled&gssapiServiceName=mongodb
Implicit session: session { "id" : UUID("63c972d5-d558-4f0a-b088-efa38787a71e") }
MongoDB server version: 4.2.6
Welcome to the MongoDB shell.
For interactive help, type "help".
For more comprehensive documentation, see
        http://docs.mongodb.org/
Questions? Try the support group
        http://groups.google.com/group/mongodb-user
> show dbs

```

# MySQL Setup on Docker

```
docker pull mysql
Using default tag: latest
Trying to pull repository docker.io/library/mysql ...
latest: Pulling from docker.io/library/mysql
54fec2fa59d0: Pull complete
bcc6c6145912: Pull complete
951c3d959c9d: Pull complete
05de4d0e206e: Pull complete
319f0394ef42: Pull complete
d9185034607b: Pull complete
013a9c64dadc: Pull complete
42f3f7d10903: Pull complete
c4a3851d9207: Pull complete
82a1cc65c182: Pull complete
a0a6b01efa55: Pull complete
bca5ce71f9ea: Pull complete
Digest: sha256:61a2a33f4b8b4bc93b7b6b9e65e64044aaec594809f818aeffbff69a893d1944
Status: Downloaded newer image for mysql:latest

[user@user]$ docker run -d --name mysql -p 3306:3306 -e MYSQL_ROOT_PASSWORD=root -e MYSQL_ROOT_PASSWORD=root -e MYSQL_DATABASE=order-service mysql
5ad7a9d9f464f3c026f1668f5507d3bc9eb98069b6a543ad94e6a74c68dfefc7

[user@user]$ docker exec -it mysql bash -l
root@5ad7a9d9f464:/# 

root@5ad7a9d9f464:/# mysql -uroot -proot
mysql: [Warning] Using a password on the command line interface can be insecure.
Welcome to the MySQL monitor.  Commands end with ; or \g.
Your MySQL connection id is 8
Server version: 8.0.20 MySQL Community Server - GPL

Copyright (c) 2000, 2020, Oracle and/or its affiliates. All rights reserved.

Oracle is a registered trademark of Oracle Corporation and/or its
affiliates. Other names may be trademarks of their respective
owners.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

mysql> show database;
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'database' at line 1
mysql> show databases;
+--------------------+
| Database           |
+--------------------+
| information_schema |
| mysql              |
| performance_schema |
| sys                |
| test               |
+--------------------+
5 rows in set (0.01 sec)

mysql>
```

# Remove all images at once

`docker rmi $(docker images -q)`

# Stop all running containers

`docker stop $(docker ps -a -q)`

# Delete all stopped containers

`docker rm $(docker ps -a -q)`

https://www.freecodecamp.org/news/how-to-remove-images-in-docker/

# Setting up Postgres

```
prateekashtikar@Prateeks-MacBook-Pro Documents % docker pull postgres
Using default tag: latest
latest: Pulling from library/postgres
927a35006d93: Already exists 
deff285050ab: Pull complete 
e224327e9ea2: Pull complete 
a193ca6ee34e: Pull complete 
40dd6251c43b: Pull complete 
f6e965c00368: Pull complete 
5aa7eb1c3a64: Pull complete 
b306316bf0e9: Pull complete 
0f29cd457498: Pull complete 
99c25330d51c: Pull complete 
fa592219b219: Pull complete 
51fb2144651e: Pull complete 
90502911dd39: Pull complete 
Digest: sha256:f329d076a8806c0ce014ce5e554ca70f4ae9407a16bb03baa7fef287ee6371f1
Status: Downloaded newer image for postgres:latest
docker.io/library/postgres:latest
```

## 1. Create a folder in a known location for you
`mkdir ${HOME}/postgres-data/`

## 2. run the postgres image
`docker run -d --name dev-postgres -e POSTGRES_PASSWORD=postgres	-v ${HOME}/postgres-data/:/var/lib/postgresql/data -p 5432:5432 postgres`

## 3. check that the container is running
```
docker ps
>>>
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS              PORTS                    NAMES
dfa570d6e843        postgres            "docker-entrypoint.s…"   27 hours ago        Up 3 seconds        0.0.0.0:5432->5432/tcp   postgres-test
```

```
docker exec -it dev-postgres bash
>>> Now you are in the container's bash console. Connect to the database
root@dfa570d6e843:/# psql -h localhost -U postgres
>>>
psql (12.2 (Debian 12.2-2.pgdg100+1))
Type "help" for help.
postgres-# \l
List of databases
Name       |  Owner   | Encoding |  Collate   |   Ctype    |   ...
-----------+----------+----------+------------+------------+------postgres   | postgres |   UTF8   | en_US.utf8 | en_US.utf8 |   ...

```

# Start AxonIQ

```
docker run -d --name axon-server -p 8024:8024 -p 8124:8124 --restart always axoniq/axonserver:latest
```

# Start MongoDB

```
docker run -it -d --name mongo-container -p 27017:27017 --restart always -v mongodb_data_container:/data/db mongo:latest 
```

# MySQL

```
docker run -it -d --name mysql-container -p 3306:3306 -e MYSQL_ROOT_PASSWORD=Password --restart always  -v mysql_data_container:/var/lib/mysql  mysql:latest
```

# RabbitMQ

if you launched rabbitmq by using somthing like:

```docker run -d --name some-rabbit -p 4369:4369 -p 5671:5671 -p 5672:5672 -p 15672:15672 rabbitmq```

then you can enable its management plugins while that container runs using the following command:

```docker container exec -it some-rabbit rabbitmq-plugins enable rabbitmq_management```

Best: `docker run -it --rm --name rabbitmq -p 5672:5672 -p 15672:15672 rabbitmq:3.10-management`

and the management GUI is running on `http://localhost:15672` For management GUI

username: guest

password: guest

# nginx

```sh
version: "3"
services:
  nginx:
    image: nginx:1.15-alpine  
    volumes:
      - ./conf:/etc/nginx/conf.d
    ports:
      - 6566:6566
    command: "nginx -c /etc/nginx/conf.d/nginx.conf"
```

# Redis

```
version: '3'
services:
  redis:
    container_name: redis
    hostname: redis
    image: redis:6.2
    ports:
    - 6379:6379
```

```sh
docker exec -it redis bash
```

# ActiveMQ

Link: http://localhost:8161/admin,  username/password => admin/admin
```
docker pull rmohr/activemq
docker run -p 61616:61616 -p 8161:8161 rmohr/activemq

docker -it rmohr/activemq bash
```

# Postgres Setup

```sh
version: "3"
services:
  postgres:
    image: postgres
    container_name: postgres
    environment:
      - POSTGRES_USER=admin
      - POSTGRES_PASSWORD=admin
      - POSTGRES_DB=productdb
    volumes:
      - ./data/db:/var/lib/postgresql/data
      - ./data/init.sql:/docker-entrypoint-initdb.d/init.sql
    ports:
      - 5432:5432
  pgadmin:
    image: dpage/pgadmin4
    container_name: pgadmin
    environment:
      - PGADMIN_DEFAULT_EMAIL=admin@admin.com
      - PGADMIN_DEFAULT_PASSWORD=admin
    ports:
      - 80:80
```

