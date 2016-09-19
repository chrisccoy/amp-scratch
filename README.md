# AMP AWS Instructions

The following readme is a general summary on how to access and use AMP within an AWS hosted instance. 
It is assumed that a swarm manager has already been provisioned and is running on AWS. 

##Prerequisites

 - [AMP Cli](https://github.com/appcelerator/amp#prerequisites) installed on developer machine
 -	AWS Instance running at a minimum swarm manager

## Ports

By default, AMP uses HAPROXY to route traffic from external sources into the swarm cluster. The accessible ports should be:

### Port 8080
This port is reserved for the amplifier service and is responsible for all internal interaction with the cluster. This included monitoring and cluster management.

###Port 80 
is reserved for the admin UI

In order to route traffic to internal containers, a public DNS entry should be created in order allow access to internal containers. For example, `engage.amp.appcelerator.io`


## Using the CLI
In order to monitor and/or manage the AMP cluster the *server* option should be selected. For example,

`amp --server engage.amp.appcelerator.io:8080 stats`



 

## TROUBLESHOOTING

The current version of docker that is running in the swarm is `1.12.1`. This version of docker is considered experimental and under certain circumstances, it might be necessary to manually manage the installation on the swarm host machine. Below are some useful commands to keep handy, when the situation arises. Note:


You will need to be given access to the pem file containing the private SSH Key in order to execute the following commands.

### Delete All Services
`docker service rm $(docker service ls -q) `

### Remove All  Containers
`docker rm -f $(docker ps -aq)`

### Remove the Docker Networks
`docker network rm $(docker network ls -q)`

### Restart the Docker Daemon

`sudo service docker restart`

### Remove Docker Volumes

`docker volume rm $(docker volume ls -q)`

