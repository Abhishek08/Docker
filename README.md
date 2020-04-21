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



