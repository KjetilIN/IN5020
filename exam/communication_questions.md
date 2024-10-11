What is the difference between transient and persistent storage in communication paradigms?
- Transient 
  - Messages may not be delivered because they are transient 
  - Message goes directly to intermediate-term storage 
  - Example: sockets 
- Persistent  
  - The messages is stored
  - Example: pub-sub 



What is the responsibility of the message brokers in the message oriented middleware paradigm?

- MOM (message-oriented-middleware) - is an approach, an architecture for distributed system i.e. a middle layer for the whole distributed system, where there's lot of internal communication (a component is querying data, and then needs to send it to the other component, which will be doing some processing on the data) so components have to share info/data among them.
- Message broker - is any system (in MOM) which handles messages (sending as well as receiving), or to be more precise which routes messages to the specific consumer/recipient. A Message Broker is typically built upon a MOM. The MOM provides the base communication among the applications, and things like message persistence and guaranteed delivery. "Message brokers are a building block of Message oriented middleware."

TLDR; format conversion between protocols, used for routing in the middleware


What are the different states of nodes in epidemic protocol?
- Epidemic protocol is a multicast protocol used to send messages to receivers quickly. 
- Is inspired by how epidemic spread in the network  
- The states are: 
  - Infected => node holds data and willing to spread the data to other nodes
  - Susceptible => A node that hasn't seen the data yet
  - Removed => dd


When searching for files in an unstructured peer-to-peer system, it may help to restrict the search to nodes that have similar to yours. Explain how gossiping can help to find those nodes.

- Gossiping is a way to multicast, but it relies on probability of sending to
  - Will pick one to send to
  - If lucky, you get the message
- It will help by
  - During gossiping, share membership information 
  - Nodes will eventually get to now all other nodes in the system