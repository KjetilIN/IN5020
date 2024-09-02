# Lecture 2.sept 2024 - Object based Distributed System 


## Remote Procedure Call (RPC)
Consider: 

```txt
count = read(fd, buf, bytes)
```

call-by-reference => buffer
call-by-value => fd and bytes

Ideally: make remote call look as local one

1. Call remote procedure
2. Local calls the local function 
3. Local returns result to server 

- This is done with Client and Server stubs. 
- We want to do this without knowing that the call is done through a network
- The problem is call-by-reference, because the buffer is not located in the same memory!
  - You as a client have the buffer, but not the server! (or the buffer is difference)
  - Problem: How to handle call-by-reference

## Passing Value parameters: 
- Parameter Marshaling: packing parameter in a message (un-marshaling is unpacking)
  - Works if the packet has all the info needed.
  - Also the machines must be identical as OS (to read values the same way)
    - Exp: Intel and Spark machines would interpreted the value 5 differently 
    - They have different interpretation of bytes (order of reading, left to right and reverse)

## Passing References parameters:
- Could share the same data
- For arrays: 
  - Copy the array into the message and send to the server
  - Does not work for very complicated data structures
- Sending pointer:
  - Passing pointer to server and generate the code for using the pointer



Client and server must agree on the RPC protocol!


## Distributed Objects

- Has remote interfaces
- Defined by IDL (interface definition language)
- An object has methods that are remotely accessible (some are not)
- Remote Object Reference (ROR): unique identity of distributed object
  - Can be an argument to call a 


## Remote Method Invocation (RMI)

- Closely related to RMI, but is related to DS objects. 
  - They are common in working with interface, request-reply protocol and both offer a similar level of transparency. 
  - They are different as in RMI is object focused 
- ROR is used to identify the object
- Send method name and arguments
- Factory methods to create new objects to distribute workload between threads. 

TODO: Learn RMI Software model 

## Object Server

- Hosts distributed objects 
- Policies are required for creating new objects, what data to operate and thread distribution
- Transient object: created at request and deleted when client has no bound to object 
- Data and Code sharing: They cannot share code nor data e.g for security reasons 
- Policies with respect to threading 
- Object Adapter / Wrapper: Group object per policy shares policies between objects


# Cobra and Java RMI

- Middleware services for a Object based DS
- CORBA
  - Clients can invoke methods without thinking about of lot critical aspects
  - Key part is the Object Request Broker (ORB) 
  - Supports Language Heterogeneity => uses IDL to communicate with different clients in different is 
  - COBRA IDL is not computationally complete 
- Java RMI
  - Pure Java based, which makes it simpler adn removes complexity
  - Use `java.rmi.Remote` to make objects for the system be accessible  