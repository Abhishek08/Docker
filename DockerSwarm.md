
# Docker Swarm

Docker Swarm is a container orchestration tool built and managed by Docker, Inc. 
It is the native clustering tool for Docker.


#### Problem Statement that solve by Docker Swarm
➤ How to Scale Containers? 

➤ How to manage Containers or re-create if they Fails/Crash? 

➤ How to Upgrade the Service with Zero DownTime? 

➤ How to Manage the containers that running on Difference Host / Node


#### Docker swarm 

➤ It allows to connect multiple hosts with Docker together.

➤ High availability 

 There are two node types in cluster: master and worker. One of masters is the leader. If current leader fails, other master will become leader. If worker host fails, all containers will be rescheduled to other nodes.

➤ Declarative configuration.

  How many replicas, and they’ll be automatically scheduled with respect to given constraints.

➤ Rolling updates 

  Swarm stores configuration for containers. If you update configuration, containers are updated in batches, so service by default will be available all the time.

➤ Build-in Service discovery and Load balancing

  Similar to load balancing done by Docker-Compose. You can reference other services using their names, it doesn’t matter where containers are stored, they will receive requests in a round-robin fashion.

➤ Overlay network 

  If you expose a port from a service, it’ll be available on any node in cluster. It really helps with external load balancing.
  
➤ Docker Swarm have Two Type of Nodes Master(Manager) and Worker. 

➤ Docker Swarm is working based on RAFT algorith. 

➤ Raft Algo : The leader node is constantly checking in with its fellow manager nodes and syncing their states

#### Docker Service 

Basic Comamnd of Docker Service 

```sh
 create      Create a new service
  inspect     Display detailed information on one or more services
  logs        Fetch the logs of a service or task
  ls          List services
  ps          List the tasks of one or more services
  rm          Remove one or more services
  rollback    Revert changes to a service's configuration
  scale       Scale one or multiple replicated services
  update      Update a service

```

#### Create first Docker service example 
```sh

docker service --name[nameofservice] [imagename] [action]   
docker service --name pingservice alpine ping www.google.com .  // New Service will create with the name of pingservice

List of service 

docker service ls // Give the list of available service 

Inspect the docker service  

docker service inspect pingservice 

Scaling the service 

docker service update pingservice --replicas=3 // Create the replicas for same service 

List of container runnong for that service 

docker ps -a  // all the running container will be visisble here 


Remove any container docker service will create new container automatically 

docker kill [container_name]
docker ps -a // after sometime you can see new container will created because we define that we need 4 replicas 
```



