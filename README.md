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

## Docker volume list

docker volume ls

docker volume inspect volumeid

## SWORM MODE

   docker swarm init --advertise-addr $(hostname -i)


root@whynotmhost helloword]# docker swarm init --advertise-addr $(hostname -i)
    Swarm initialized: current node (d9i88ihkk112lyuuu45teox0l) is now a manager.

    To add a worker to this swarm, run the following command:

    docker swarm join --token SWMTKN-1-631oe1x6i6s5fqkf04o2tsyknq0kr6amfq5mwdcnpflst0cj5p-1izjtci1jw6p3ved42x0hv8l9 127.0.0.1:2377

To add a manager to this swarm, run 'docker swarm join-token manager' and follow the instructions.

[root@whynotmhost helloword]#








## DOCKER ENGINE SERVICE



    [root@whynotmhost helloword]# service docker start  
    Redirecting to /bin/systemctl start docker.service
    [root@whynotmhost helloword]#
    [root@whynotmhost helloword]#  systemctl status docker -l
● docker.service - Docker Application Container Engine
        Loaded: loaded (/usr/lib/systemd/system/docker.service; disabled; vendor preset: disabled)
       Active: active (running) since Tue 2018-10-16 15:08:30 WEST; 2s ago
     Docs: https://docs.docker.com
 Main PID: 55249 (dockerd)
   Memory: 44.8M
   CGroup: /system.slice/docker.service
           ├─55249 /usr/bin/dockerd
           └─55255 docker-containerd --config /var/run/docker/containerd/containerd.toml

Oct 16 15:08:29 whynotmhost dockerd[55249]: time="2018-10-16T15:08:29.285580644+01:00" level=info msg="pickfirstBalancer: HandleSubConnStateChange: 0xc42030c260, CONNECTING" module=grpc
Oct 16 15:08:29 whynotmhost dockerd[55249]: time="2018-10-16T15:08:29.285777191+01:00" level=info msg="pickfirstBalancer: HandleSubConnStateChange: 0xc42030c260, READY" module=grpc
Oct 16 15:08:29 whynotmhost dockerd[55249]: time="2018-10-16T15:08:29.285796369+01:00" level=info msg="Loading containers: start."
Oct 16 15:08:29 whynotmhost dockerd[55249]: time="2018-10-16T15:08:29.833812266+01:00" level=info msg="Default bridge (docker0) is assigned with an IP address 172.17.0.0/16. Daemon option --bip can be used to set a preferred IP address"
Oct 16 15:08:30 whynotmhost dockerd[55249]: time="2018-10-16T15:08:30.008090408+01:00" level=info msg="Loading containers: done."
Oct 16 15:08:30 whynotmhost dockerd[55249]: time="2018-10-16T15:08:30.018846899+01:00" level=info msg="Docker daemon" commit=e68fc7a graphdriver(s)=overlay2 version=18.06.1-ce
Oct 16 15:08:30 whynotmhost dockerd[55249]: time="2018-10-16T15:08:30.018912724+01:00" level=info msg="Daemon has completed initialization"
Oct 16 15:08:30 whynotmhost dockerd[55249]: time="2018-10-16T15:08:30.020262801+01:00" level=warning msg="Could not register builder git source: failed to find git binary: exec: \"git\": executable file not found in $PATH"
Oct 16 15:08:30 whynotmhost dockerd[55249]: time="2018-10-16T15:08:30.033200063+01:00" level=info msg="API listen on /var/run/docker.sock"
Oct 16 15:08:30 whynotmhost systemd[1]: Started Docker Application Container Engine.
[root@whynotmhost helloword]#



## GIT PUSH

git init .

git add $DIRECTO_TO_PUSH


 git status
git commit -m "Ajout fichier de configuration de gitlab et gitignore"



git remote add origin http://whynotm@172.21.0.2/config/whynotm.git


git push origin master
