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
