# AMP AWS Instructions

The following readme is a general summary on how to access and use AMP within an AWS hosted instance. 
It is assumed that a swarm manager has already been provisioned and is running on AWS. 

##Prerequisites

[AMP Cli](https://github.com/appcelerator/amp#prerequisites) 

## AWS Specifics

By default, AMP uses HAPROXY to route traffic from external sources into the swarm cluster. The accessible ports should be:

**8080** is reserved for the amplifier service 
**80** is reserved for the admin UI

In order to route traffic to internal containers... //TODO

BASE URL = *.engage.amp.appcelerator.io.

`amp --server engage.amp.appcelerator.io:8080 stats`

 

## TROUBLESHOOTING
