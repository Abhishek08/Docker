
# Docker Swarm

Docker Swarm is a container orchestration tool built and managed by Docker, Inc. 
It is the native clustering tool for Docker.


###### How to Scale Containers? 

###### How to manage Containers or re-create if they Fails/Crash? 

###### How to Upgrade the Service with Zero DownTime? 


###### Build-in Service discovery and Load balancing

Docker Engine swarm mode makes it easy to publish ports for services to make them available to resources outside the swarm. All nodes participate in an ingress routing mesh.The routing mesh enables each node in the swarm to accept connections on published ports for any service running in the swarm, even if there’s no task running on the node. The routing mesh routes all incoming requests to published ports on available nodes to an active container.
 
If you expose a port from a service, it’ll be available on any node in cluster. It really helps with external load balancing.
 
 
#####  Security

Docker Swarm comes with great security features out of the box. When a node joins the swarm, it uses a token that not only verifies itself but also verifies it is joining the swarm you think it is. From that moment on, all communication between nodes takes place using mutual TLS encryption. This encryption is all provisioned and managed automatically by the Swarm, so you never need to worry about renewing certificates, and other typical security hassles.


###### Important component of Docker swarm 

 1. Service : Service define the task that need to be execute on manager and workder nodes.
 
 2. Task : Tasks are Docker containers that execute the commands you defined in the service.
 
 3. Manager Node: It delivers work (in the form of tasks) to worker nodes. and Monitor the worker node.
 
 4. Worker node: Worker nodes run tasks distributed by the manager node in the swarm.Each worker node runs an agent that reports back to the master node about the state of the tasks assigned to it, so the manager node can keep track of services and tasks running in the swarm.


##### Docker Swarm Cluster

![Cluster](https://foxutech.com/wp-content/uploads/2017/03/swarm-architecture.png)



Docker Swarm contain multiple Docker Host that running on Docker Swarm mode. Each host may be work as Master or Worker. 
Master Host will work as Manager or Worker.


##### Formula for Creating the Master Host.

 Master Or Manager = (n-1)/2 
 
 N= Number of Nodes 

##### How to Initialize the Docker Swarm

```sh
 docker swarm init 
 
or

 docker swarm init --advertise-addr <MANAGER-IP>
   
```

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



