# Lecture 4.november 

Web based: composition of services to create new services. 
Middleware for machines and automation 

### Web based and their Proxy Strategies  
- Web Proxy
  - Was created to original do conversion between protocols. 
  - Today:
    - Filtering request, and logging. 
    - Compression => not that used 
    - caching => the most important use 

Proxy Caches: 
- Needs to be updates to not have stale data
- GET has if-modified-since to do pull based propagation => most used to update
- Lease based is also an option, but not used that often. 
- Some Web content might not be cashable or waste to cache 
- Cache policy based on size is possible, or LRU 

Proxy Caching Hierarchy:
- If proxy does not have the resource in cache it requests, then we go to another proxy
- Assumption: it is cheaper to go through proxies than to the web server 

Cooperative Proxy Caching: 
- Ask neighbor proxy. 
- Used for per-organization basis: one proxy for a department.
- Assumption: it is faster to look at neighbor proxies

Request Dispatchers: 
- Goal: equally load servers with request 
- Monitor the load
- Options: 
  - DNS Round-Robin: Multiple IPs for a name, and then send request to ..
    - Useful when there the same type of requests
  - Content Aware: inspect HTTP request 
    - Useful to better distribute the request based on load
  - TCP-level switch: 
    - Much faster then the others, but not better. 


CDN: Content-distribution network (CDN)
- Placement of data/object replication 
- Akamai CDN
  - Get base document (skeleton without structure)
  - Lookup the CDN from a CDN DNS server 
  - Get embedded documents from closest CDN 


### Cloud Computing: 
- Delegate computing to the cloud
- IaaS, PaaS, SaaS are layered architectures
  - IaaS: for computation, storage, communication 
  - PaaS: useful to create environments for developments and deployment
  - SaaS: applications used by the end user 

Five essential characteristic: 
1. On-demand self service
2. Elasticity => provide the required resources on demand
3. Resource Pooling => allocate resources to users 
4. Measured Service => measure usage for each customer
5. Broad Network Access => support different protocols, interfaces, and security 



### Blockchain

- Many use cases. Most interesting is the architecture. 
- Creating decentralized trust. 
- EBSI: European Blockchain Service Infrastructure 


Distributed Ledge Technology (DLT):
- Chain of blocks 
- Each block stores transactions 
- Block refers the last block in a secure way
- Replicated on multiple nodes
- Peers maintain the block chain data structure
- Data is replicated on the peers. 
- Whenever there is a decision, we add a new block: 
  - It must be agreed between all peers
- Cryptography is used in multiple steps 
- Secure pointer with previous block
  - Hash changes on changes, which makes the pointer no longer value
  - It becomes harder and harder to mutate blocks without detecting the error. 
- Use Byzantine consensus algorithm 


### IoT - Internet of Things 

Interconnected objects with addressable protocols. 
- Enables RFID and WSN 
- Decisions in IoT applications are chosen based on data analysis
  - We need data

IoT System Designs are simple to complex models to solve different models.
- Level 1:
  - No cloud 
  - Monitoring a node
  - Data are stored on database
- Level 2:
  - Data is now big, move database to the cloud 
- Level 3: 
  - Cloud is now for analysis also on the cloud 
  - Analysis is computational hard  
  - F.exp levels of vibrations 
- Level 4: 
  - Multiple monitor nodes now
  - Observer node which subscribes to events 
    - Data is overwhelming and we need to summarize the information 
- Level 5: 
  - Coordinator node is introduced for sending data to the cloud 
  - F.exp forest fire detection: many sensors and collect for multiple sectors.  
- Level 6:
  - Centralized controller in the cloud 
    - Control the individual endpoints 
    - Sends control commands 
  - Used in weather monitoring 