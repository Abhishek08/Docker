
# Docker Networking 

Docker networking is basically used to establish communication between the docker containers and the outside world via host machine or you can say it is a communication passage through which all the isolated containers communicate with each other in various situations to perform the required actions. I

When Docker is installed, a default VPN is created called bridge. bridge. This is default Network driver of Docker

Each new Docker container is automatically attached to this network, unless a custom network is specified.

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

1. List of Available network 
```sh
docker network ls  // Show the list of network 
```

2. Create new Network 
```sh
docker network create [--driver <driver-name>] <network-name> 

Example : docker network create --driver bridge my_network 

If the option –driver is not given then the network will be created as a bridge network. Else, the specified driver will be used.

```
3. Provides details for the given Docker network. 
```sh
docker network inspect <network-name|network id>

example : docker network inspect my_network
```

4. Filter in inspect command. Ex. want to see the only container info 

```sh
docker network inspect -f '{{.Containers}}' my_network  // this command will give the information of only container running on 
my_network 
```

5. Remove the given Docker network. 

```sh
docker network rm  <network-name|network id>
```

6. Disconnects the given container to the specified network.

```sh
docker network disconnect <network-name|network id> <container-name|Container ID>
```

7. Create the container on Specific network 

```sh
docker container run -d --name <container_name> --network <network_id|network_name> <imageId|image_name>

example : docker container run -d --name nginx_container --network my_network nginx
```
## Docker Network DNS   
DNS stands for Domain Name System.  

DNS makes it possible for us to use easy to remember domain names in place of complex IP addresses.

Containers uses DNS to communicate. Containers don’t use IP address to Communicate.

Example . Ping Nginx container from another container 

```sh
Step 1: launch 2 nginx container 
 
docker run -d --name nginx_01 --network my_netwrork nginx 
docker run -d --name nginx_02 --network my_netwrork nginx 
 
Step 2: Login to Nginx server and install ping command 
 
docker exec -it nginx_01 /bin/bash  // After executing this command you are login into nginx and execute below command 
 
apt-get update
apt-get install inetutils-ping

Step 3: ping nginx_02 from nginx_01 

docker exec -it nginx_01 ping nginx_02

```

