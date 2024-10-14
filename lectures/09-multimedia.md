# Lecture 14.october - Distributed Multimedia Systems 

## Multimedia 

Computer integration of different resources
- text, graphics, audio, etc

There is two types: 
- discrete media: is time independent => text, image
- continuous media: implicit time dimension => video, audio

Continuous media:
- Uses data stream
- Timing is crucial 

Some key requirements: 
- Represent the continuous media
- Synchronization mechanism => sime synchronization is required 
- Quality of Service

Programming models:
- Cannot use a simple request, need continuous stream of data


Representation:
- the temporal relationship between data items of the stream mus be preserved 
- F.example audio: use a series of 16-bits representing amplitudes. Must be played in the same rate it was sampled


QoS-aware streaming: 
- uses compressed multimedia data 


Forms of synchronization:
- Intra media: maintain uniform time spacing of a single continuous media stream
- Inter media synchronization between several streams 
  - For example: stream for video and stream for audio need to be merged, or sync of video and subtitles
- Distributed state: stop video operation by a user should be observed by all
- External: sync on time based streams 
- It can be supported by high level interfaces such as a middleware 

## Quality of service

- Balance the cost and quality 
  - Tradeoff between both 
- IDL: functional specification on what is going to be done
- QoS has a non-functional specification that tells us how the function should perform 
- QoS Managements: monitor and control to that insures requests 


Jitter: variation of delay 


Admission control: allow a new task to add new service
- Schedulability: can CPU slots be assigned for the tasks  