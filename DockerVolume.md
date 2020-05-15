# Docker Volume


#### Container Persistent Data Problem 

➤ Containers are immutable : Once deploy never change, only re-deploy. 

➤ Config Change or version Upgrade need re-deploy. 

➤ By default all files created inside a container are stored on a writable container layer.

➤ The data doesn’t persist when that container no longer exists, and it can be difficult to get the data out of the container if another process needs it
