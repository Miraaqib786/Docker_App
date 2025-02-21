# Docker Hands-on Guide

## Docker Commands

### IMAGES:
#### List all Local images
```sh
docker images
```
#### Delete an image
```sh
docker rmi <image_name>
```
#### Remove unused images
```sh
docker image prune
```
#### Build an image from a Dockerfile
```sh
docker build -t <image_name>:<version> .  # version is optional
```
#### Build without cache
```sh
docker build -t <image_name>:<version> . --no-cache
```

### CONTAINER:
#### List all Local containers (running & stopped)
```sh
docker ps -a
```
#### List all running containers
```sh
docker ps
```
#### Create & run a new container
```sh
docker run <image_name>
```
*If the image is not available locally, it’ll be downloaded from DockerHub.*

#### Run container in the background
```sh
docker run -d <image_name>
```
#### Run container with a custom name
```sh
docker run --name <container_name> <image_name>
```
#### Port Binding in a container
```sh
docker run -p <host_port>:<container_port> <image_name>
```
#### Set environment variables in a container
```sh
docker run -e <var_name>=<var_value> <container_name> (or <container_id>)
```
#### Start or Stop an existing container
```sh
docker start <container_name> (or <container_id>)
docker stop <container_name> (or <container_id>)
```
#### Inspect a running container
```sh
docker inspect <container_name> (or <container_id>)
```
#### Delete a container
```sh
docker rm <container_name> (or <container_id>)
```

### TROUBLESHOOT:
#### Fetch logs of a container
```sh
docker logs <container_name> (or <container_id>)
```
#### Open shell inside a running container
```sh
docker exec -it <container_name> /bin/bash
```
```sh
docker exec -it <container_name> sh
```

### DOCKER HUB:
#### Pull an image from DockerHub
```sh
docker pull <image_name>
```
#### Publish an image to DockerHub
```sh
docker push <username>/<image_name>
```
#### Login into DockerHub
```sh
docker login -u <username>
```
Or simply:
```sh
docker login
```
To remove stored credentials:
```sh
docker logout
```
#### Search for an image on DockerHub
```sh
docker search <image_name>
```

### VOLUMES:
#### List all volumes
```sh
docker volume ls
```
#### Create a new named volume
```sh
docker volume create <volume_name>
```
#### Delete a named volume
```sh
docker volume rm <volume_name>
```
#### Mount a named volume with a running container
```sh
docker run --volume <volume_name>:<mount_path>
```
Or using `--mount`:
```sh
docker run --mount type=volume,src=<volume_name>,dest=<mount_path>
```
#### Mount an anonymous volume with a running container
```sh
docker run --volume <mount_path>
```
#### Create a Bind Mount
```sh
docker run --volume <host_path>:<container_path>
```
Or using `--mount`:
```sh
docker run --mount type=bind,src=<host_path>,dest=<container_path>
```
#### Remove unused local volumes
```sh
docker volume prune  # For anonymous volumes
```

### NETWORK:
#### List all networks
```sh
docker network ls
```
#### Create a network
```sh
docker network create <network_name>
```
#### Remove a network
```sh
docker network rm <network_name>
```
#### Remove all unused networks
```sh
docker network prune
```

---

### 🚀 Happy Dockering! 🎯
