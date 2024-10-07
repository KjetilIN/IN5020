# Lecture 7.october

- A set of communication primitives 


### Communication properties:
- Addressing scheme and space decoupling 
- Content based addressing 
- Persistence levels
  - How can we make sure the message is received?
  - Fully precisian - message receives the message no matter what
  - Fully transient - no effort of verifying 
  - Intermediate - some effort but no guarantee
- Synchrony 
  - Fully synchronous - stops execution until receives response, only when response is received it continues executing 
    - The next step will always be to receive a message, meaning the communication steps are simpler 
  - Fully asynchronous - can do computation after sended the message
  - Intermediate
- Time decoupling => doing something independent of time

### Communication paradigms 

- RPC (Remote Procedure call)
- Message-oriented communication 
- Stream-oriented communication 
- Software-based distributed shared memory (DSM)
  - Used in tightly-coupled systems 

### Message oriented communications: 
- Raw socket programming:
  - Uses IP addresses as addressing scheme
  - No time decoupling 
  - Transient 
  - Mainly used for building higher-level abstractions 
- Message Programming Interface (MPI)
  - Addressing scheme is a group of nodes assigned logical addresses
  - Not designed to cope with failures
  - Transient without time decoupling 
  - Data-oriented 
  - Used in parallel computation in fast memory 
  - For example: matrix operations => use MPI_scatter to send a part of the matrix to a node 
- Message oriented middleware (MOM)
  - Addressing scheme is logical queue name
  - Persistent => message is certain to reach the queue
  - Full time decoupling
  - Need to manage the queues   
  - Routing by using a message broker to perform inter-domain routing with format conversion 
    - Messages have hierarchical names
  - Examples: complementary databases where a query needs to be split
    - with MOM: send part of the query to the queue of the database 
- Publish-subscribe communication:
  - Publisher adds information
  - Subscribers express what type of information they what to receive
  - Notification is done by a pub-sub service 
  - Address scheme through the content 
  - Examples:
    - News distribution 
    - Social notification 
  - Topic based pub-sub
    - Subscribers subtribe to topic, get information from that topic
    - Also allow wildcard subscribe
    - EX: MQTT with topics that are hierarchical
  - Type-based pub-sub
    - Subscribe to a type of event 
    - Uses the fact that events of the same type has the same structure 
  - Content-based pub-sub
    - All attributes known 
    - Event represent a set of attributes
    - Subscribe to a place in the event space (where the event space is created by all the attributes)
    - Can include constrain => which is another dimension in the event space
    - Routing by having routing table for each broker in the pub-sub system
      - A broker then now what notification types to forward to another broker  
      - A broker means the same as a router 

### Multicast and its effects on communication abstraction

.........