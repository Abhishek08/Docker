## Important docker command 

##### Important tag for Docker 
```sh
--detach , -d        Run container in background and print container ID
--name                Assign a name to the container
--publish , -p        Publish a container’s port(s) to the host
--volume , -v        Bind mount a volume
--restart            Restart policy to apply when a container exits
```
1. Show the Docker version information
```sh
    docker version
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

##### .......................................................................................
# Docker File 

1. The Dockerfile is a text file that (mostly) contains the instructions that you would execute on the command line to create an image.

2. You’ll use a Dockerfile to create your own custom Docker image.

3. Docker will build a Docker image automatically by reading these instructions from the Dockerfile.

Creating the Custom Docker image below is the process 

1. you create the Dockerfile and define the steps that build up your images

2. you issue the docker build command which will build a Docker image from your Dockerfile

3. now you can use this image to start containers with the docker run command

Docker provides a set of standard instructions to be used in the Dockerfile, like FROM, COPY, RUN, ENV, EXPOSE, CMD just to name a few basic ones.

##### Example 1 . 

Step 1. create the DockerFile  
```sh
vi Dockerfile
```

Step 2. Paste below instruction paste into Dockerfile
```sh
FROM ubuntu  
RUN mkdir TEST
RUN apt-get update
RUN apt-get install tree
```
Step 3. docker build -t <imageName> <Define the path where Dockerfile present>

```sh
  docker build -t ubuntu_server . 
```
 . is represent that Dockerfile is present in same Directory .
 
Step 4. To create the container from Docker Image. docker run -d --name <containerName> <image_name>:<Image_version/tag>
```sh
  docker run -d --name ubuntu_container  ubuntu_server
```
##### Example 2 . 
Create custom image for Nginx server .
    
Step 1. Create Index.html file 
 ```sh
  vi index.html
```  
Step 2. Put Some content into the index.html 
 ```sh
 <html>
 <body>
     <h1> This is sample example of docker ngnix </h1>
 </body>
 </html>
```  
Step 3: Create the DockerFile in same Directory 

```sh
vi Dockerfile
```
Step 3: Paste below content into the Dockerfile and save (press esc btn then wq! end enter to save the file).

```sh
FROM nginx:latest
COPY index.html /usr/share/nginx/html/index.html   // Copy the file from source location to Destination
RUN chmod +r /usr/share/nginx/html/index.html      // Providing the permission to index.html 
CMD ["nginx","-g","daemon off;"]                   //  Nginx uses the daemon off directive to run in the foreground.  
```



