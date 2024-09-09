# Lecture Notes 9.september 2024 - Component and Web based distributed systems


## Software component 

- Component based Software developing
- Component: a unit of composition software. Independent and self-deployable code. Replaceable with clear function.
- Example: JavaBeans, CORBA, etc
- Components is a natural way to build systems
- We use them to reduce complexity and manage change 


### The three basic design concepts

1. Component model: Set of properties, methods (required and provided), events 
   - Components implements interfaces. 
   - Shows dependencies to other components. 
   - Components can be distributed over a network

2. Connection models and composition: 
    - Method based or event based

3. Deployment model 
    - Process of installation the components on servers and such 
    - Define rules for deployment, composition and activation of components
  
Contracts as the key design element: 
- Set of provided and required interfaces
- Extra requirements can also be provided such as guarantees, conditions and transaction requirements

What is the different between components vs object based?
- Object based: encapsulate for re-usability's. 
- Objects are tightly coupled, while components are loosely coupled. 


### Distributed components

- Example: Inter-process com. as middleware. Then two computers have their own components. 
- In Object Based, the developer needs to be implemented all services. It is also tightly coupled to the object. 
- In component based, you can separate the concerns of life-cycle, persistance and security. 
  - Developer only focuses on the logic
  - Use a container to handle life-cycle, security 



## Web Based Systems 

- Client and Web server
- Uses HTTP protocols 
- Uses URI - Uniform Resource Identifier.
- Web services allows for cross organization calls 

