
# Docker Registry

The Registry is a stateless, highly scalable server side application that stores and lets you distribute Docker images. The Registry is open-source, under the permissive Apache license.

### Why use it

You should use the Registry if you want to:

tightly control where your images are being stored
fully own your images distribution pipeline
integrate image storage and distribution tightly into your in-house development workflow

### Docker Compose file to see the images into the registry

```sh

version: "3"
services:
  docker-registry:
    image: registry:2
    container_name: registry
    ports:
    - 5000:5000
    restart: always
    volumes:
    - ./docker-registry:/var/lib/registry

  docker-registry-ui:
    image: konradkleine/docker-registry-frontend:v2
    container_name: registry_ui
    ports:
    - 8080:80
    restart: always
    environment:
      ENV_DOCKER_REGISTRY_HOST: docker-registry
      ENV_DOCKER_REGISTRY_PORT: 5000

```

### Run the docker compose file 

```sh

docker-compose up -d  

```

### Setup the insecure docker registry 

```sh 

vi /etc/docker/daemon.json

{
    "insecure-registries" : ["youripAddress:5000"]
}

restart the Docker 

sudo systemctl stop docker

sudo systemctl start docker

```

### Pull the image from docker hub and upload into the docker registry 

```sh

1. Pull the image 

docker pull nginx 

2. update the tag for nginx image 

docker image tag nginx:latest ipaddress:5000/imagename_version

3. upload this image into the docker registry 

docker image push ipaddress:5000/imagename_version

4. Pull the image from docker registry 

docker pull ipaddress:5000/imagename_version
```



