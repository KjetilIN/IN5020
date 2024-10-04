What are the advantages of replication?
- Performance enhancement
- Increased server availability
- Fault tolerant
  - Correct service even if servers fail


What are the different mechanism to propagate updates between replica?
- Push-based propagation 
- Pull-based propagation 
- Hybrid based propagation 

Are ... legal outputs for sequentially consistent memory?
- If happened-before in each sequence, then they are sequentially consistent 
- Check each output => illegal if the order of instruction 
- (for the task) Special case in the binary where it is not valid. Look for the characteristic 

What are the different replication schemes?
- Active replication
  - Every replica gets all request from the clients
- Passive replication 
  - One replica acts as primary 
  - Primary handles execution
  - Failure of primary is sent to primary or cold backup 
- Quorum based replication 
  - Set of replicas are write quorum and some are read quorum
  - Client send request to write quorum 