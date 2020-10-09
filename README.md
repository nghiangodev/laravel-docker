# ![N|laravel](https://laravel.com//img/logomark.min.svg) ![N|laravel](https://laravel.com//img/logotype.min.svg)

### Docker daily useful commands
Below is the list of most useful docker commands.

Download docker image from the repository

Install the dependencies and devDependencies and start the server.

```sh
docker pull image_name
```
Check a list of all docker images

```sh
docker images
```

Check if Docker containers are up & running

```sh
docker ps -a
```
Start and stop a container

```sh
docker ps -a
```
Check if Docker containers are up & running

```sh
docker start container_name
docker stop container_name
```
Get inside of running docker container

```sh
docker exec -i -t container_name command
 
e.g for ubuntu image
docker exec -i -t ubuntu_container_name bash
```
Remove all docker containers

```sh
docker rm $(docker ps -a -q)
```
Forcefully remove all docker containers

```sh
docker rm -f $(docker ps -a -q)
```
Remove all docker images

```sh
docker rmi $(docker images -a -q)
```
 Forcefully remove all docker images

```sh
docker rmi -f $(docker images -a -q)
```
See the logs from docker container

```sh
docker logs -ft container_name
```

### Docker compose commands
Build all Images

```sh
docker-compose build
```
Build and run all containers

```sh
docker-compose up -d
```
Stop all containers

```sh
docker-compose stop
```
Remove all containers

```sh
docker-compose rm
```
Restart only one container

```sh
docker-compose restart container_name
```

### MY SQL Docker Container

Sometimes we need to run SQL queries inside docker-containers to check database data. Below is the list of useful commands to run inside my SQL container.

Get inside running MySQL container
```sh
docker exec -it mysql_container-name mysql -uroot -p
```

“root” is the username for MySQL database.
After running above command it will ask you a password.

Select database
```sh
USE Database_name
```

Show tables
```sh
show tables;
```

Select table
```sh
docker exec mysql_container-name /usr/bin/mysqldump
-u root 
--password=root 
database_name > backup.sql
```

Restore MySQL database to docker container
```sh
cat backup.sql | docker exec -i mysql_container-name 
/usr/bin/mysql
-u root 
--password=root database_name
```

Take back of MySQL database from docker container
```sh
docker exec mysql_container-name /usr/bin/mysqldump
-u root 
--password=root 
database_name > backup.sql
```

#### Docker Container Stats command
To find out CPU, memory usage of each container.

```sh
docker stats container_name
```
See memory and usage for all docker containers
```sh
docker ps -q | xargs  docker stats --no-stream
``` 
https://hub.docker.com/_/mysql
        https://webomnizz.com/containerize-your-laravel-application-with-docker-compose/
        https://www.youtube.com/watch?v=Ra1CetTcSeo&feature=emb_logo
        https://hub.docker.com/_/nginx
        https://docs.docker.com/compose/compose-file/

