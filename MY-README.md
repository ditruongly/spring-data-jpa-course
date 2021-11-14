# Spring Boot Tutorial | Spring Data JPA | 2021
## Amigoscode
https://www.youtube.com/watch?v=8SGI_XS5OPw&t=404s

## Download PostgresSQL Docker Image and Start Container
```
docker run --name postgres -e POSTGRES_PASSWORD=mysecretpassword -d postgres
```
## Rename Docker Image
```
docker image tag postgres:latest learning/postgres:latest
```
## Delete Docker Image Tag
```
docker rmi postgres/latest
```
## Create Docker Volume for Persistence
```
docker volume create learning_postgres_data
```
## Inspect Docker Volume
```
docker volume inspect learning_postgres_data
```
## Remove All Stopped Containers
```
docker container prune
```
## Remove All Local Volumes Not Used By At Least One Container
```
docker volume prune
```
## Start Container with Persistence
- -d --detauch Run container in background and print container ID
- -e --env Set environment variables
- -p --publish Publish a container's port(s) to the host
- -v --volume Bind mount a volume
- --name Assign a name to the container
```
docker run --name learning-postgres -p 5432:5432 -v learning_postgres_data:/var/lib/postgresql/data -e "POSTGRES_PASSWORD=mysecretpassword" -d learning/postgres
```
## Stop Container
```
docker container stop learning-postgres
```
## Start Container
```
docker container start learning-postgres
```
## Show Container Log Messages
```
docker logs learning-postgres
```
## Check Container Status
```
docker ps -a -f name=learning-postgres
```