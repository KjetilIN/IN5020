# Lecture 30. september - Replication 

- Replicate the server instance 
- Will improve the performance 
- For distribution Geographically 
- Better availability

Challenges:
- Complex
- Protocol for consume bandwidth 
- Some complexity is exposed to the client

There are different tiers of replicas:
- Caches is a form of replica => we will improve the performance with cache
- Permanent replicas 
  - Cluster of servers 
  - CDN servers for serving data (Akamai example)
- Server-initiated caches:
  - Placement of hosting servers 
  - Cater demand by creating replicas 
  - Placement of caches 
- Client-initiated caches:
  - Enterprise proxies or browser caches 

Propagation of updates: 
- Push-based:
  - a replica pushes the update to other replicas
  - Ensures fresher information sooner
  - Reduces traffic compared to traffic 
  - Requires deterministic operation 
- Pull-based:
  - A replica request other replica to send the newest data it has
- If there is a lot of updates, then pull is better, because we don't want to push every update
- If there is not that many updates then we might want to push. 
- Hybrid push-pull approach:
  - Lease based propagation => Push based, but can be pull based on different occasion
  - Send message to other replicas that, I have updated. Notifications are a lot smaller, and easier. Then the notified replica can pull newest changes. 


The issue of consistency:
- With multiple replicas, there might be inconsistencies between all the replicas
- Update on a replica, does not mean update to all other replicas 
- Single replica systems avoids this, because all operations will happen on the same server

Consistency:
- A contract between the client developer and the server  => sematic contract
- "Ideal consistency": system behaves as if there it is a non-replica system 
- Tradeoffs between: consistency efficiency and simplicity. Two but not three of these factors 


Sequential consistency:
- A system consists of a number of servers and a number of objects replicated on those servers 
- An execution consists of events 
- There should include a linearization 


Example deposit() and balance(): 
- Not sequential consistent because there is no corresponding sequential consistency 
- When there is no way to order the events, it is not sequential consistent 


Replicate state machines:
- Active replication
- Passive replication => one primary server 
- Primary-backup replication => cold backup with only primary being active 
- Primary-backup warm backup => hot standby 
- Local-write scheme => the primary migrates between servers 
- Quorum-based replication => update to majority, and then use this fact 

Reliable group communication: 
- Broadcast to a group of machines 
- Multicast many to many 
- Very challenging to reason, because the multiplicity of the states 
- Adds group membership service on top of multicast  
  - Dynamic maintenance of groups
  - Fail detection 


View and view sync: 
- View epoch of system evolution between two consecutive changes of membership
- Evolution of systems as views 

Ordered message delivery: some rule to order messages, with two variants 
- Unreliable: should deliver the latest message
  - When you don't want to allow to delay communication 
  - F.exp: For example media stream. Because you won't see a missing 
- Reliable: must delivered first message before the second message.
  - TCP is reliable, because it will break the connection if the bytes are not continued.
  - Means that we need to delay messages


Common ordering: 
- FIFO
- Causal: two messages are ordered if happened-before relation
- Total: all messages will be received in the sam order by all the processes in the group

Implement ordered delivery:
- Two queues: delivery and hold back queue
- Incoming messages in the holdback queue
- When deliver is satisfied, move the message to delivery queue