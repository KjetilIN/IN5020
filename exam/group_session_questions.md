# Group Session questions and answers: 

## G1: 

?


## G2:

What is the purpose of "stub" in RMC
- Marshall and un-marshall parameters
- Take care of communication between client and server
- Helps with access transparency 

Why do we need Interface Definition Language (IDL)?
- We need them to allow communication between client and servers
- This allows us to use multiple languages for the same system 

What are the similarities between RPC and RMI?
- both uses xxx
- differences: RMI uses object oriented programming 


Calculate total time -> client make remote procedure call to the server (what is total time):
- draw on whiteboard 
- (marshal and os time at each point, before sending over network)
- for one thread, two requests, we just multiply the time by 2
- with two threads: ....



## Group session - Component based and Web based 

What are the issues with Object Oriented Middleware?
- We had to connect to a middleware server, then waiting. The latency is an issue
- Interaction level is low. Have to connect to know to discover services 
- Component based like Javascript: we use our own resources to compute  

What is a container and why do we need it?
- What?
  - Container holds one or more component 
- Why?
  - Container will pack everything, so that the application can run on every machine


What is the difference between URL and URN?
- URL Uniform Resource Locator => includes location of resource it identifies 
- URN is location independent and relies on a service for finding resource 

## Group - Peer-to-peer System 

What is the key problem in P2P?
- Placement of data objects across many host
- Lookup of data objects 
  - How long can you do it?
- Challenges:
  - Naming 
    - How to make machines have names?
  - Routing Table
    - How to build and maintain?
    - Without a routing table you are stuck
  - Handling node churn  

Discuss the function and non-functional requirements of peer-to-peer middleware?
- Functional:
  - Locate and communicate with node
  - Add or remove resources 
  - Simple API for the resources
- None-Functional requirements:
  - Scaling
  - Load balancing
  - Optimization of interaction 
  - Handle node churn 
  - Security and anonymity 


Napster. What other solution to indexing problem can you identify?
- Distributed Hash Table 
  - F.exp Pastry uses DHT based on GUID and uses circular routing protocol


Squirrel P2P. 4.11 hops were required fora cached entry, but only 1.7 hops for cambridge. How come?
- Different amount of nodes. 
- Pastry use O(log_16 N) hops to deliver a messages for N nodes in the network 
  - Log 16 because of the size of the routing table 
- We can use this to show that the theoretical formula 