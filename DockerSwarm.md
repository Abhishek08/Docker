
# Docker Swarm

Docker Swarm is a container orchestration tool built and managed by Docker, Inc. 
It is the native clustering tool for Docker.

It allows to connect multiple hosts with Docker together.

#### Problem Statement that solve by Docker 
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



