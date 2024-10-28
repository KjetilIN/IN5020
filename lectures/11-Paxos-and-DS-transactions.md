# Lecture 28.oct - Paxos and Distributed Transactions

- Paxos is the most commonly used consensus algorithm
- A fundamental building block for data centers 
- Used by most data center and cloud providers 

Google uses Chubby, 


## Roles in Paxos
- Client => issue request to Paxos server
- Proposer => accepts the client request and publicizes and advocates the state change to the other processes
- Acceptor => executes the agreement and records the state change once agreement is achieve.
- Learner => once a client a request has been agreed on, learner may take an execution. For example lock change
- Leader => Requires a distinguished proposer to make progress

Paxos has many flavors.
- Basic paxos: one decision only
- More usable paxos version agrees on a sequence of events 


## Basic Paxos - Iterations

The steps are: 
1. Prepare
2. Confirm 
3. Accept 
4. Accepted 


### Attempt 1:


First problem is parallelism.
- Two parallel by multiple proposer
  - Possible solution: use proposer ID, to allow only the highest ID 

Second problem failure: 
- Solution: monitor active proposers for failures. Logical Time to allow the waiting proposer. 
  - Allows for the waiting to ....


Third failure is failure of proposer: 
- The accepted message cannot be sent to the proposer 
- We cannot have accept for different values


Dueling proposer problem: 
- When we have two different prop


Failure of an Acceptor: 
- How to handle this?
- Use a quorum of acceptors 
- Results in the possibility of two different values being excepted, but only one can be accepted by a quorum

Selecting value for Accept: 
- Send timestamp for for when prepare was sent. Accept the one with the highest timestamp. The newest Accept.


### Complete protocol: 

.....


## Multi-Paxos

- Typically use a stream of agreed values acting as commands to update a distributed state machine 
- We include instance number for each proposal 
- Problem can be viewed as a sequence of independent consensus instances. 

## Paxos Optimization and Extensions :  

There is about 50 different flavors of Paxos. 

- How many acceptors doe we need? We don't need that many. 
  - Less Acceptors can lead to missing messages. 
  - We can tolerate some F acceptor failures
  - Typically have backup acceptors by doing a reconfiguration protocol
- Without leader communication to Acceptors directly:
  - Faster when there is are no conflicts. 

## Distributed Transactions

Servers can offer concurrent access to the data the service encapsulates

For example Client invokes operation. 

Transactional Service: 
- Offers access to resources via transactions.
- Offers creating transaction and then closing or opening an transaction

Transaction has: 
- Commit point
- Transaction si committed when the services has executed the transaction

DS Transaction systems has: 
- Transactional Client
- Transaction Server
- Coordinator

Coordinator: 
- Manages the transactions. 

Problem: commit on multiple servers:
- Each server must verify that they can commit all transactions 
- If one cannot commit the transaction, then xxxxx

### 2PC protocol

One phase protocol is insufficient, so we propose a two phase protocol: 
- First phase: Agreement
  - Ask all servers if they can commit given transaction 
- Second phase: execution.
  - Collect replies from all servers
  - Abort if at least one responded no. 
  - If all okay, tell all servers to perform a commit 
  - All respond with "have committed" message


What happens a previously failed server recovers?
- Depending on the state of the coordinator and participant 

CORBA Transaction Service implements 2PC