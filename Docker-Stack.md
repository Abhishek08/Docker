# Docker-Stack

##### What is Docker Stack ?
Docker stack is group of interrelated service , that share dependecies and can be orchestrated and scale together.

Docker Stack use compose Yml to create the Stack. 

#####  Limitation of Docker Compose
Docker compose is used to create multiple service in Single host but if you have requirement like to create multiple services in multiple host that we cant use the Docke compose because docker compose not work in Swarm mode. 

If you execture docker compose file in the docker swarm mode it will create the container in current node where you execute the compose file.

In Docker compose file we have to add docker stack related propertry because some functionality of docker compose will not support in Docker stack.





