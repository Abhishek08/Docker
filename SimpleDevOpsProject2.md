
# Simple DevOps Project CI CD Using Node JS 


##### Steps 1 - Install Node Js on Ubuntu Machine 

``` sh 

sudo apt update

sudo apt install nodejs

sudo apt install npm

nodejs -v  // To check the node JS version 

```

##### Step 2 -  Download the Publish Over SSH plugins 

``` sh

Key -- define the private Key ( you will get from .pem while when you will open as text file)

ssh Server - 

Name - define the name of the server.
HostName - Provide the IP address of your server.
UserName - Provide the user name here ex. if we are using Ubuntu ec2 instance then username is ubuntu

Click Save and Apply 

```

##### Step 3 -  Create the Free Style Node JS project .

``` sh 

Git URL - https://github.com/Abhishek08/webapp.git

WebHook Connection URL - http://IPADDRESS/github-webhook/ (push)

BUILD - npm install  // to download all the dependecines 
      - npm test  // to perform test case execution 
     
```

##### Step 4 - Post Build Action Define below details.
``` sh 

sudo mv  ./home/ubuntu/com/target/WebApp.war /home/ubuntu/com; // Copy the war file into the your Server Location 
cd /home/ubuntu/com; // Goto the Location where DockerFile is present.
docker stop mycontainer; // Stop the Container if its running 
docker rm mycontainer; // Remove the container
docker build -t myimage .; // Create the new Image using Docker file
docker run -d --name mycontainer -p 8090:8080 myimage; // Create new Container using the custom Image.

```



