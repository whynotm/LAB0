# LAB0
LAB0 First Project on GIT



# DOCKER
##List Docker Images

[root@whynotmhost helloword]# docker image ls
REPOSITORY            TAG                 IMAGE ID            CREATED             SIZE
whynotm/get-started   part2               a6ad9d65bcb0        29 minutes ago      132MB
friendlyhello         latest              a6ad9d65bcb0        29 minutes ago      132MB
python                2.7-slim            14dad3ead5f4        5 days ago          120MB
hello-world           latest              4ab4c602aa5e        5 weeks ago         1.84kB
[root@whynotmhost helloword]#

## List Conatiners runnung
docker container ls --all

## RUn Docker
[root@whynotmhost helloword]# docker run -d -p 4000:80 friendlyhello
29cedfeb1f64ee23425a9cdc4121eba44adaad34e44fb386cd7f3e34b800ecd5
[root@whynotmhost helloword]#


## Helloword dockers Running
root@whynotmhost helloword]# docker container ls --all
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS              PORTS                  NAMES
29cedfeb1f64        friendlyhello       "python app.py"     18 seconds ago      Up 18 seconds       0.0.0.0:4000->80/tcp   festive_snyder
[root@whynotmhost helloword]#


## Test docker's http CURL
"[root@whynotmhost helloword]#  curl http://localhost:4000

<h3>Hello World!</h3><b>Hostname:</b> 29cedfeb1f64<br/><b>Visits:</b> <i>cannot connect to Redis, counter disabled</i>[root@whynotmhost helloword]#
[root@whynotmhost helloword]#"


## Test docker's http CURL

Browser : tape  localhot:4000 : 

Hello World!
Hostname: 29cedfeb1f64
Visits: cannot connect to Redis, counter disabled


##Docker STOP LIST RM LIST

[root@whynotmhost helloword]# docker container ls --all
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS              PORTS                  NAMES
29cedfeb1f64        friendlyhello       "python app.py"     5 minutes ago       Up 5 minutes        0.0.0.0:4000->80/tcp   festive_snyder


[root@whynotmhost helloword]# docker stop 29cedfeb1f64
29cedfeb1f64

[root@whynotmhost helloword]# docker container ls --all
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS                       PORTS               NAMES
29cedfeb1f64        friendlyhello       "python app.py"     6 minutes ago       Exited (137) 2 seconds ago                       festive_snyder

[root@whynotmhost helloword]# docker container rm 29cedfeb1f64
29cedfeb1f64

[root@whynotmhost helloword]# docker container ls --all
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS              PORTS               NAMES
[root@whynotmhost helloword]#



## DOCKER COMPOSE

 curl -L "https://github.com/docker/compose/releases/download/1.22.0/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
 
 
 
  chmod +x /usr/local/bin/docker-compose
  
  [root@whynotmhost helloword]#  docker-compose --version
docker-compose version 1.22.0, build f46880fe
[root@whynotmhost helloword]#



## Docker service status
service docker status

##Docker volume list

docker volume ls

docker volume inspect volumeid


