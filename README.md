# Docker Swarm Tutorial 

<img src="https://miro.medium.com/max/2694/1*dybB9cpWGPfRB5y_E6Upxw.jpeg">

## Introduction 

This tutorial is about docker swarm as the name suggests. The scope of this tutorial is talk about the motivation behind docker swarm, how it works in brief and provide a quick guide to jump start on your local machine to see how it works.


## About Container Orchestration 

In a world of containers, managing them can often prove to be difficult in the context of scalability, distributed environments and having a lot of infrastructure. Docker swarm allows just for that. It allows for containers to run across several computing devices often virtual machines in the cloud. It is similar to kubernetes in the sense of its goal to orchestrate and manage containers. It often is far easier to setup and get started than kubernetes. Docker swarm has many goals, some of them include:

- An easy way to scale applications across computing resources 
- Offerring fault tolerance & reliablity 
- Load Balancing requests 
- Rolling Updates that allows the service to be up despite updates through replicas 
- Easy to Learn 
- Built natively into docker engine

## Prerequisites & Getting Started

For this tutorial to work, you will need to have docker version 19.0 or above installed through docker for linux or desktop for mac or docker desktop for windows. Downloads to these can be found [here](https://docs.docker.com/get-docker/).

## Basic Concepts 

This section contains some of the key concepts part of docker swarm. 

### A Node

A node is used to indicate a physical computing resource in the context of docker swarm. A node often defines a single virtual machine running docker engine. 

### Manager Nodes

Manager nodes distribute and schedule incoming tasks onto the Worker nodes, maintain the cluster state and perform orchestration and cluster management functions. Manager Nodes can also optionally run services for Worker nodes.

Cluster management tasks include:
- Maintaining the cluster state
- Scheduling services
- Serving swarm mode to HTTP API endpoints

There should always be multiple manager nodes in your swarm because of the following reasons:

- Maintaining high availability
- Easily recover from a manager node failure without downtime

That is why Docker recommends you implement an odd number of nodes according to your projects availability requirements.

### Worker Nodes 

Worker nodes are also instances of the Docker Engine whose sole purpose is to execute containers and services as instructed by the Manager Nodes.

### A service

A service is the definition of the tasks to execute on the nodes. It is the primary root of user interaction with the swarm.

When you create a service, you specify which container image to use and which commands to execute inside running containers. You also define other options for the service including:
- the port you want to expose
- CPU and memory limitations
- the number of replicas of the image to run in the swarm
- a rolling update policy

These parameters can also be defined through a docker-compose yaml file and deployed into the swarm. 

The following is an image of a service which is nginx (a web server) having 3 replicas being deployed on 3 nodes. 

![](https://docs.docker.com/engine/swarm/images/services-diagram.png)

## Acknowledgements 

- [Docker Swarm Guide](https://gabrieltanner.org/blog/docker-swarm)

