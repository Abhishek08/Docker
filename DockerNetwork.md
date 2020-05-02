
# Docker Networking 

For Docker containers to communicate with each other and the outside world via the host machine, there has to be a layer of networking involved. Docker supports different types of networks, each fit for certain use cases.

When Docker is installed, a default bridge network named  docker0 is created. Each new Docker container is automatically attached to this network, unless a custom network is specified.

Each Container connect to virtual private network called ‘bridge’.

bridge : This is default Network driver of Docker

All Containers on same bridge can communicate each other with-out -p (port)

Docker Network is easy to Plugged-in in Containers.

User is allow to Create Multiple VPN.

Create Multiple Rules for Single Network.

Attach Multiple Containers to One Network, and Attach single container to more than One Network or no need to attach any network to container.

##  Default networks provided by Docker
  1. Bridge 
  2. None 
  2. Host 

## Bridge Network - 
Docker provides the bridge network by default. A docker container created on the host is connected to this network by default. The bridge network maps to the docker0 bridge of the host.

## None Network - 
The none is used to attach a Docker container to a no-network network! This means that the Docker container will have its own network stack but it will not be configured. Containers attached to the none network will not have an IP address and will be stand-alone. 

## Host Network - 
When a container is connected to the host network, it gets the same network configuration as in the host OS.

## Docker Network Commands  

List of Available network 
```sh
docker network ls  // Show the list of network 
```



