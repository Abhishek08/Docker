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
4. Launching a container with ‘docker run’ command
 ```sh
   docker run --rm [IMAGE] – removes a container after it exits.
   docker run -td [IMAGE] – starts a container and keeps it running.
   docker run -it [IMAGE] – starts a container, allocates a pseudo-TTY connected to the container’s stdin, and creates an interactive bash shell in the container.
   docker run -it-rm [IMAGE] – creates, starts, and runs a command inside the container. Once it executes the command, the container is removed.
```
