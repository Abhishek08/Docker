
# Docker Networking 

For Docker containers to communicate with each other and the outside world via the host machine, there has to be a layer of networking involved. Docker supports different types of networks, each fit for certain use cases.

When Docker is installed, a default bridge network named  docker0 is created. Each new Docker container is automatically attached to this network, unless a custom network is specified.

##  Default networks provided by Docker
  1. Bridge 
  2. None 
  2. Host 

1. Each Container connect to virtual private network called ‘bridge’. 
2. bridge : This is default Network driver of Docker
3. All Containers on same bridge can communicate each other with-out -p (port) 
4. Docker Network is easy to Plugged-in in Containers. 
5. User is allow to Create Multiple VPN. 
6. Create Multiple Rules for Single Network. 
7. Attach Multiple Containers to One Network, and Attach single container to more than One Network or no need to
 attach any network to container.
