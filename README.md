# **Legal Portal**

## Requirements

Before anything, you need the following softwares installed on your machine:

- [Node](https://nodejs.org/en/download/current/) >= 10
- [Docker](https://docs.docker.com/engine/installation/)
- [Docker Compose](https://docs.docker.com/compose/install/)
- **npm** (not yarn!)

## Installation

Clone `plant-manager` project repository:

```bash
git clone https://github.com/thibault-jacquet/plant-manager.git
```

Enter the project directory:

```bash
cd plant-manager
```

Clone following repositories in the project repository.

```bash
git clone https://github.com/thibault-jacquet/plant-manager-webapp.git
git clone https://github.com/thibault-jacquet/plant-manager-api.git
```
Create plant_manager_network.
```bash
docker network create plant_manager_network
```

Then, install the dependecies.

```bash
docker-compose run --rm plant-manager-webapp npm install
docker-compose run --rm plant-manager-api npm install
```

## Start entire application and services:

```bash
docker-compose up
```

## Access to application

You can now access your application using below url:  
[https://localhost:3000](https://localhost:3000)

## Docker clean

Potentially, you may need to **kill**, **delete** or even **stop** your Docker containers, please follow the commands below for:

Kill all running containers with:

```bash
docker kill $(docker ps -q)
```

Delete all stopped containers with:

```bash
docker rm $(docker ps -a -q)
```

Delete all images with :

```bash
docker rmi $(docker images -q)
```
