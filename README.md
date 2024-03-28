# Docker Commands

This README includes various Docker commands for managing containers, networks, images, and Docker Compose configurations.

## Basic Docker Commands

```bash
#$docker version
#$docker info
$docker container run --publish 80:80 nginx
$docker container run --publish 80:80 --detach nginx
$docker container ls
$docker container ls -a 
$docker container run --publish 80:80 --detach --name nickos nginx
$ docker container help
$docker container run --publish 8080:80 --name webhost -d nginx:1.11 nginx -T 
$ docker run --name mongo -d mongo
     NGINX       HTTPD      MYSQL
      80:80  | 8080:80 |3.3306:3306
$docker container run -d -p 3306:3306 --name nick -e MYSQL_RANDOM_ROOT_PASSWORD=yes mysql
$docker ps
$docker container top
$docker container inspect 
$docker container run -d --name nginx nginx
$docker container run -d --name mysql -e MYSQL_RANDOM_ROOT_PASSWORD=true mysql 
$docker container top mysql 
$docker container top nginx
$docker container inspect mysql
Shell Commands
$docker container run -it --name proxy nginx bash 
$docker container run -it --name  ubuntu ubuntu
Network Commands
$docker container run -p 80:80 --name webhost -d nginx 
$docker container port webhost
$docker container inspect --format '{{ .NetworkSettings.IPAddress }}' webhost
$docker network ls
$docker network inspect  
$docker network disconnect 
$docker network inspect bridge
$docker network create my_app_net
DNS PING COMMANDS
$docker container run -d --name my_ngninx --network my_app_net nginx 
$docker container exec -it my_nginx ping new_nginx
'Image, Tags, Files, and Volume Commands'
$docker image ls
$docker pull nginx
$docker history ngunx:latest
$docker history mysql
$docker image inspect nginx
$docker image tag --help
$docker image ls
$vim Dockerfile 
$docker volume --help
$docker pull mysql 
$docker image inspect mysql
$docker container run -d --name mysql -e MYSQL_ALLOW_EMPTY_PASSWORD=True mysql
$docker volume ls
$docker volume inspect  8004901c6827293fd662db6f13c6ebc72b209c
$docker container run -d --name mysql2 -e MYSQL_ALLOW_EMPTY_PASSWORD=True mysql
$docker container stop mysql
$docker container stop mysql2 
$docker container ls
$docker container ls-a
$ docker container rm mysql mysql2
$docker container run -d --name psql2 -v psql:/var/lib/postgresql/data postgres:9.6.2
$docker container ps -a
$docker container ls
$docker container logs
Docker Compose
$docker-compose up
$docker-compose down
Docker Compose Paradeigma
version: '3'
services:
  proxy:
    image: nginx:1.11
    ports:
      - '80:80'
    volumes:
      - ./nginx.conf:/etc/nginx/conf.d/default.conf:ro
  web:
    image: httpd


 

