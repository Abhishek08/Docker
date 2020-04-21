## Important docker command 

1. Show the Docker version information
```sh
    docker --version
```

2. Display system-wide information
 ```sh
    docker info
```

3. You can use the docker inspect command to find out low-level information about your container or image
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

16. Docker Exec Bash and Docker SSH into Container
You'll often need to interact with a container's shell to create a service or solve problems. 
You can use the docker exec command to create an interactive shell. Let's start a container
from the ubuntu image with a bash shell:
```sh
   docker run --name my_ubuntu -it ubuntu:latest bash
   
   Suppose you want to Docker ssh into container 'my_ubuntu'. You can use the docker exec   bash method:
   docker exec -it my_ubuntu bash
   
   Use docker exec   to issue commands into your container. For example, you can run the ls  command on your 'my_ubuntu'     docker container directly from the command prompt:
   docker exec -it my_ubuntu ls
   
```



