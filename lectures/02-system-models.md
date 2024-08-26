# Lecture 26.aug 

- The idea is to describe a system with common models 
- Three types of model

## Physical model 
  - Focus on the hardware 
  - LAN 
    - Original model but limited in scale
    - Openness was not priorities or quality of service
  - Internet 
    - Large amount of users
  - Cloud computing models
    - Very large scale
    - Any type of device can connect 
    - Major challenges for openness between different types of services

## Architectural model
- Software and system architecture
- We try to visualize the main components in the system.
    - Described with entities, connections, communication paradigms 
- Roles and responsibilities
    - Client-server model is the simples 
    - Peer-to-peer with a sharable objects 
    - Hybrids
- Placement strategies
    - Multiple servers to cover a larger geographical 
    - cache based with a proxy server 
    - Content Distributed Network (CDN)
    - Server Cache 
    - Client Cache 
    - Client side execution 
    - Agent takes care of handling service or data
      - Example is WebCrawler 
- Patterns 
    - Recurrent structures that have shown to work well 
    - Gives you an idea to how to build the target application 
    - Layered
      - Extract common services as DB, and security to the middleware
      - You as a developer do not need to think about these services
      - The challenge is that all the service must serve all needs for the application model
    - Tiered
      - Tiers for development 
      - There is a lot of middleware services that are useful - i.e publish-subscribe, message ques, peer-to-peer etc. 
    - Microservice
      - Each service is small, and has what it needs in the single component. 
      - Make the development of a service by using a set of micro services
      - Makes it easier to switch components 
    - Thin Client
      - Client does nothing, server side execution
      - Remote desktop is an example of this
  

## Fundamental models
- Formal description of properties
- Properties shared by all models 
- Make some assumptions on the model 
- Interaction model
  - process, messages and coordination between entities
  - Messages can be delayed 
  - Performance of such a system is latency, bandwidth and jitter.
    - Latency => delay between the start of transmission and the beginning of reiving
    - Bandwidth => how much amount of information can be transmitted
    - Jitter => variation in the time taken to deliver a series of multimedia data
  - Computer clocks is an issue, due to different times and clock drift 
    - Physical clocks are not a solution per say
  - Ordering of events could be important 
    - Email exchange is an example where the order is important
- Failure model 
  - Define and classify failures that can occur
  - Making a new service that masks the faulty behavior 
  - Understand the effects of the failure
  - Ex. TCP on top of IP
  - Three types of failure: 
    - Omission failure
    - Arbitrary failure => unknown failure 
      - Systems that implement this model, they are **ultra-reliable**
      - They are also very complex  
    - Timing failure
  - Mask the whole failure or just part of the failure 
  - Masking by hiding or converting the failure 
- Security Model 
  - Define and classify attacks that can occur
  - basis for analysis of the threats
  - Will not be focused on in this course 


Synchronous DS => the time to execute each stem of a process has a known lower and upper bound of time. 
Asynchronous DB => each step can take an unknown amount of time. 
- Two army problem => two armies much arrive at the same time for winning an battle 
  - Communication is unreliable 
  - Solution: 

### Logical Clock 
Logical clocks describe logic ordering of events even without accurate clocks
- A -> B : A happened before B
- Happened-before relationship