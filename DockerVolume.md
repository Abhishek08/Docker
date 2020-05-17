# Docker Volume


#### Container Persistent Data Problem 

➤ Containers are immutable : Once deploy never change, only re-deploy. 

➤ Config Change or version Upgrade need re-deploy. 

➤ By default all files created inside a container are stored on a writable container layer.

➤ The data doesn’t persist when that container no longer exists, and it can be difficult to get the data out of the container if another process needs it

#### Docker Volumes 

➤ Volumes : Volumes are stored in a part of the host filesystem which is managed by Docker

➤ Volumes can be create by Volume Command in Docker File. 

➤ When you create a volume, it is stored within a directory on the Docker host machine. 

➤ Volumes can not be removed when user destroy the containers

➤ We can assign same volume to multiple container 

#### Example of Docker Volume 

```sh

Step 1  Create the volume
        docker volume create MyVolume

Step 2  Pull the image from docker hub 
        docker pull busybox
 
Step 3  Run the containr with named volume 
        docker run -d -it --nmae [nameofcontaineer] --mount source=[nameofVolume],target=[destination] [nameofImage]
        ex. docker run -d --name mybusybox --mount source=MyVolume,target=/app busybox

Step 4  bash login into the container 
        docker exec -it mybusybox sh
        
Step 5  create the folder in /app  and file 
        mkdir TEST 
        cat -> one.txt 
        exit // exit from the container
 
Step 6  create the another container with same volume 
        docker run -d --nmae [nameofcontaineer] --mount source=[nameofVolume],target=[destination] [nameofImage]
        ex. docker run -d --name mybusybox2 --mount source=MyVolume,target=/app busybox
        
Step 7  bash login into the container 
        docker exec -it mybusybox2 sh
        
Step 8  go to app and you can see TEST folder and one.txt file are present. 
               
 
```

#### Example 2 Docker volume example using mySQL 
```sh

Step 1  Create the volume
        docker volume create DBVOL
        
Step 2  Pull the image of mysql
        ocker pull mysql
        
Step 3  Run the containr with named volume 
        docker run -d --name [nameofcontainer] -e [enviourment] -v [volumename]:[destinationpath] [imagename]             
        ex: docker run -d --name myDb1 -e "MYSQL_ROOT_PASSWORD=1234" --mount source=DB,target=/var/lib/mysql mysql
  
Step 4  Download mysql client 
        apt-get install mysql-client
 
Step 5  Inspect the container and get the IP address and port 
        docker inspect [containername]
        
Step 6  login to mysql  
        mysql -u root[password] -h[ipaddress] -P[port]
        ex. mysql -u root -p1234 -h 172.17.0.3 -P 3306
        
Step 7  Create the database
        create database one;  // this command create the database 
        show databases;       // this command show the list of database 
        exit                  // Exit from mysql 
        
Step 8  Stop and Remove the container 
        docker stop [container] 
        docker rm   [container] 

Step 9  create another container with same volume
        docker run -d --name [nameofcontainer] -e [enviourment] -v [volumename]:[destinationpath] [imagename]             
        ex: docker run -d --name myDb2 -e "MYSQL_ROOT_PASSWORD=1234" --mount source=DB,target=/var/lib/mysql mysql
        
Step 10 login to mysql new container 
        mysql -u root[password] -h[ipaddress] -P[port]
        ex. mysql -u root -p1234 -h 172.17.0.3 -P 3306
        
Step 11 We can see the same db is available with new container means db is persistant      
        
```





