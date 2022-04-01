
# Docker Container as Service

This is a simple example that makes use of docker compose to create 3 containers (having persistent data volumes) for 
- web api in python 
- rabbitmq for queues and 
- mongodb for database





## Installation

- Install docker and docker-compose
- The simple clone the project
- Go to the cloned directure and run the docker compose CMD
    
## Tech Stack

**WebAPI Client:** Python

**NoSQL:** Node, MongoDB

**Queue Agent:** RabbitMQ


## Docker CMD

### Create Docker Volumes
```
docker volume create --driver local --opt type=none --opt device="C:\user\_local_data\app" --opt o=bind docker_exec_container_vol_app

docker volume create --driver local --opt type=none --opt device="C:\user\_local_data\mongod\data\" --opt o=bind docker_exec_container_vol_mongo_data

docker volume create --driver local --opt type=none --opt device="C:\user\_local_data\mongod\conf\" --opt o=bind docker_exec_container_vol_mongo_conf

docker volume create --driver local --opt type=none --opt device="C:\user\_local_data\mongod\log\" --opt o=bind docker_exec_container_vol_mongo_log

docker volume create --driver local --opt type=none --opt device="C:\user\_local_data\rabbitmq\data\" --opt o=bind docker_exec_container_vol_rabbitmq_data

docker volume create --driver local --opt type=none --opt device="C:\user\_local_data\rabbitmq\log\" --opt o=bind docker_exec_container_vol_rabbitmq_log

docker volume create --driver local --opt type=none --opt device="C:\user\_local_data\rabbitmq\conf\" --opt o=bind docker_exec_container_vol_rabbitmq_conf

```


### Docker Build
```
docker build . -t docker_exec_main
```

### Docker Compose CMD

#### Start as service
```
docker-compose up -d

or

docker-compose up
```

#### Stop and delete
```
docker-compose down
```

#### Stop 
```
docker-compose stop
```

### Docker Run
```
docker run --rm -it -p 8080:8080 --name my_docker_exec docker_exec_main:latest
```

## 🚀 About Me
I'm a full stack developer and I like to tryout new things to enhance the product features and prodcutivity!


## Authors

- [@austinnoronha](https://www.github.com/austinnoronha)


## Acknowledgements

 - [Docker Hub for Mongo](https://hub.docker.com/_/mongo/)
 - [Docker Hub Rabbitm 3-Alpine](https://hub.docker.com/_/rabbitmq)

## Issues

- [ ]  Not able to setup mongod.conf volume to a persistant directory
- [ ]  Not able to setup /var/lib/mongo volume to a persistant directory