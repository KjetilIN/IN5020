## Course Overview

Oral exam!
No practical exercises, but you can do them if you want to. 

Texts books: 
- Distributed Systems - Concepts and Designs
- Distributed Systems - Principles and Paradigms

## Intro to Distributed Systems  


### Definitions
- Very expensive computers in the beginning. 
- Better performing computers now, compared to before. 
- The result is that we can take a large composed of connected components.


Operational Perspective: 
- Components located a networked computers and communicate through passing messages. 

User perspective: 
- The user sees it as a single coherent system. 

A distributed system is organized as a middleware between users and applications. 

Examples of distributed systems: 
- Web Search
- Large Scale retailers
- Multiplayer online games
- Financial trading
- Bitcoin

It is important to know why you are distributing a system

### Goals

Why do we want to do this? 
- Resource sharing
  - Storage, I/O, Printer, RAM, Data, Threads, CPU power
  - Making resources accessible is very useful. Especially accessing remote resources
  - Resource managers controls access adn offer a scheme for naming and controlling concurrency 
  - Client-Server is model for resource sharing. 
  - Object-Based resource model
    - For example: CORBA, Java RMI
- Transparency 
  - Hide the fact the process and resources are distributed
  - If the system is seen as a single coherent computer system. Then it is transparent. 
  - There are different forms of transparency. For example location, access, migration, failure, concurrency, etc. 
    - For example: Migration => when you download a file from server in Norway, and then you move to Germany and you want to download the same file. 
  - There is a tradeoff between hiding a lot of information or not. 
- Openness
  - System that offers services that follows standard rules that describe syntax and semantics of those services.
  - Such standards could be IDL, WSDL and other semantics. 
- Scalability
  - Should stay efficient 
  - Scale in size, geographical and administratively 
  - Centralized solution is difficult to scale 
  - There are a set of techniques for duplicating a service
    - Replication, Sharding, Hiding commination latencies.  
- Fault tolerance
    - DS must maintain availability even in cases where hardware/software/network have low reliability
    - Many different ways to handle failures. 
    - Google has a lot of services, and about 2-3% will fail. Each day, 20 servers are need of a restart.  

### Implications

- Concurrency 
- No global clock. You cannot assume the same clock. 

### Pitfalls
Assumptions that are not true, but often assumed in DS:
- Network is reliable, secure and homogeneous.
- Speed and cost of transport.  

### Types

- Three types:
  - Computing
    - Used for computing high performance computing task
    - Cluster and Cloud computing systems
      - With a cluster based system, you have a single master node and some computing nodes. 
    - Grid computing where each machine have different system where each machine is in different geographical areas. 
  - Information 
    - Communication middleware is used between the client and server
      - For example Kafka 
  - Pervasive 
    - exploiting small devices. 
    - used in smart homes, where the system 