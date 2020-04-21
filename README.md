## Important docker command 

1. Show the Docker version information
```sh
    docker -version
```

2. Display system-wide information
 ```sh
    docker info
```

3. Return low-level information on a container or image
 ```sh
    docker inspect [Container or Image name /ID]
```

4. Pull an image or a repository from a registry
 ```sh
   docker pull ubuntu 
```

5. pull a docker image with old version
 ```sh
   docker pull ubuntu:16.04
```

6. List of all available images in local
 ```sh
   docker images 
```

7. Launching a container with ‘docker run’ command
 ```sh
   docker run [imagename|ImageId]
   
   Create/run/start a docker container from image
   
   docker run -d --name <container_Name> <image_name>:<image_version/tag>
   d - run your container in back ground (detached)
   
   Expose your application to host server
   
   docker run -d  -p <host_port>:<container_port> --name <container_Name> <image_name>:<Image_version/tag>
   Example : docker run -d --name httpd_server -p 8080:80 httpd:2.2
   
```

8. run a OS based container which interactive mode (nothing but login to container after it is up and running)
```sh
   docker run -i -t --name <container_Name> <image_name>:<Image_version/tag>
   i - interactive
   t - Terminal

   Example: docker run -i -t --name ubuntu_server ubuntu:latest
```

9. List out running containers
```sh
   docker ps
```

10. List out all docker container (running, stpooed, terminated, etc...)
```sh
   docker ps -a
```

11. Stop a container
```sh
   docker stop <container_id>
```

12. start a container which is in stopped or exit state
```sh
   docker start <container_id>
```

13. Remove a container
```sh
   docker rm <container_id>
```

14. Kill a container by sending a SIGKILL to a running container
```sh
  docker kill [CONTAINER]
```

15. Remove the image
```sh
  docker rmi [IMAGE]
```

16. login to a docker container
```sh
   docker exec -it <container_Name> /bin/bash
```



