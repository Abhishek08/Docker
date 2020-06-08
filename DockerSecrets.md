

# Docker Secrets 

Secrets : A secret is a piece of data, such as a password, SSH private key, SSL certificate, or another piece of data that should not be transmitted over a network or stored unencrypted in a Dockerfile or in your application’s source code.

In Docker 1.13 and higher, you can use Docker secrets to centrally manage this data and securely transmit it to only those containers that need access to it. 

Docker Secrets is only available in the Swarm mode, so standalone containers can not use this feature.

A given secret is only accessible to those services which have been granted explicit access to it, and only while those service tasks are running.


#### How Docker Swarm manage the secrets.

When a user adds a new secret to a Swarm cluster, this secret is sent to a manager using a TLS connection. 
