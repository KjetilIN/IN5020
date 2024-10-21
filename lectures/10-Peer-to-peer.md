# Lecture 21.oct - Peer to Peer

- P2P systems distribute processing and traffic between nodes 
- Each node is a client and a server 
- Main motivation was to offload the servers to provide better scalability 
  - Today, this is not that required due to cloud computing 
  - Spotify used P2P until they where rich enough to replace it with cloud servers 
- Two main reasons to use: 
  - Lack of serialization. F.exp block chain technology 
  - Increased privacy => with client/server clients need to disclose information 
  - Self organization => Servers at Google fail every 10min. 
    - Not reasonable to re-config every 10 minutes. 
    - P2P promotes self organization 
- P2P has unpredictable availability for processes and nodes
  - Simply uses the network of nodes at that time 

History: 
- Started with the launch of Napster 
- Early on used for file sharing and middleware
- Publish/sub, media streaming and in cloud
- Blockchain is the newest usage of P2P

P2P middleware: 
- Place resources on nodes 
- Route messages on behalf of clients
- Hide the location of resources from clients


Difference between overlay routing and IP for P2P: 
- IP routing is set and shared between applications
- Application level can address needs for the specific P2P application

Napster: 
- Maintain server index (list of peers that have resources)
- Peer send request to server
- Server responds with a list of peers that offers the file
- Peer request from peer to get the file 
- Server update the index

- Napster was shutdown after lawsuit 
- Lost its lawsuit because indexing of peers on the server
- New services like Napster, where the list of peers are also on peers!



Designing middleware: 
- Challenge: ...

Routing overlay:
- Each peer has routing knowledge 
- Routing overlays the routing knowledge between nodes 
- This are implemented in the application level, but can be implemented int he middleware level 


Essential API for Distributed Hash-table:
- ...

Case Study: Pastry: 
- ...


Circular routing: Correct but efficient:
- ...



Routing algorithm: using the routing table:
- Improves performance with routing table 
- Mapping between IP addresses and GUID prefixes 
- Go down the rows in the table if IP is not there
- Can be visualized as a three: also known as a three table 
- The first step will be biggest, and then smaller steps
- Message delivered in $log_{16}(N)$ hops