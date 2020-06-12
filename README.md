# typecho-docker

## Requirements
Install [Docker](https://docs.docker.com/get-docker/) and [Docker Compose](https://docs.docker.com/compose/install/)
## Usage
1.Clone `typecho-docker` 
``` shell script
git clone https://github.com/hanekoo/typecho-docker.git
```
2.Clone `typecho` program to `./typecho/`
``` shell script
git clone https://github.com/typecho/typecho.git ./typecho/
```
3.Open the.env file and modify it as needed
```shell script
vim .env
```
4.Run it
```shell script
docker-compose up -d
```

## Other

### data
mariadb data path :`data/matiadb/`
### typcho
typecho program path:`typecho/` 
### install typecho 
database address：
 just input mariadb service name：`mariadb`,or get the `mariadb` service container IP:
```shell script
docker ps
#CONTAINER ID        IMAGE          ...  NAMES
#24e68b1da482        mariadb:latest ...  typecho-docker_mariadb_1
docker inspect -f '{{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}' typecho-docker_mariadb_1
#172.20.0.2
```

