
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

### run the docker compose file 

```sh

docker-compose up -d  

```

