# Lecture 23. september 

- Each entity/process has their own clock, and their clocks are not synced 
- Notation of time is relative, and that is a problem 
- Latencies has not improved over time 

## Time in DS: 
- Work around the limitations 
- Do we need order of events, or real-time synchronization?
- Sometimes, the order of events are all we need. 
- We try to reduce the scale, (limit how many we need to synchronize with)

## Logical time: 
- Capture dependencies to message exchange and local produced. 
- Happened-before: x happened before y. 
- Logical clock: each process has its own clock. 
  - Rules for logical clock: counts events and piggybacks values
- Alternative - Vector Clocks:
  - Assumes: N processes,
  - Uses a vector for each process 
  - Piggyback the whole vector for the message 
  - Happened-before when: xx

We cannot build a single sequence of events because some might be concurrent.
How do we model executions? History h:

- Global histories: xx
- Cut: xxxx

Consistent cuts: when xx

Inconsistent cuts can never happen. Therefore, we don't do it. 


Partial order of events vs. full order of events.
- Example: garbage collection 


Liberalization: partial order, extended to a full order, and the sequence of events are possible. 


## Snapshot problem

- Find a global state that may have occurred
- We don't know what have occurred 
- A consistent state from which is reachable from the initial state.
- We can use this to create checkpoints, and we can use a snapshot to get to the reachable state. 
- The snapshot could be reached from the initial state, and must be able to reach the final state.


ADD: PROBLEM EXAMPLE FROM LECTURE 

- The capture of state may be inconsistent 

Algorithm assumptions:
- No process/network failure
- ..

Algorithm (correct from Chandy, Lamport 1885): 
- xx



Proof of protocol correctness:
- The recorded state is consistent 
- S2 must be reachable from S1
- S3 must be reachable from S2

TODO: add last topics from lecture 
