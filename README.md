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




 

