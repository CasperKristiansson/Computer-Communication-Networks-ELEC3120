# Networking Midterm

_2 Questions per chapter (6 total)_

## Chapter 1

**Chapter Coverage on Midterm:**

- Delay: 1.43 to 1.48
- Throughput 1.52

**Notes:**

- Delay
  - A router has a buffer which could be filled up if the output link capacity is less then the packet arrival rate
  - There are four primary sources to packet delay
    - which represent the processing delay in a router. The delay to check for bit errors, determine output link.
    - which represent the queuing delay in the router
    - represents the time it takes to get all bits into the wire from the host.
    - represents the time it takes one bit to travel from one end of the wire to the other
  - Queuing delay
    - The queuing delay can be determined as a factor using where a represents the average arriving packets per second
- Throughput
  - Is the rate of bits per second being transferred between sender/receiver
    - Instantaneous: the rate at any given time
    - Average: rate over longer period
  - In many cases the throughput will be bottleneck meaning that certain links will have a lower capacity then others
    - , In practice R is never the bottleneck

## Chapter 2

**Chapter Coverage on Midterm:**

- Client-server vs P2P architecture 2.6, 2.70
- Persistent and non-persistent http 2.25
- DNS resolution resolve hostname 2.63

**Notes:**

- Client server vs P2P architecture
  - Client-Server
    - **Server** : Always on host, permanent Ip address, data centers for scaling
      - **Server** process waits to be connected
    - **Client** : Communicates with the server, may be intermediately connected, dynamic Ip address, do not communicate with each other directly
      - **Client** process initiates the communication
  - P2P
    - There won't be an always on server
    - Arbitrary and end system directly communicate
    - Peers usually request services from other peers which in return the peers do services for other peers
    - Peers are intermittently connected and change IP addresses. This kind of architecture can become complex
    - Examples of systems running P2P
      - File distribution (BitTorrent)
      - Streaming (Kankan)
      - VoIP (skype)
  - Advantages/Disadvantages
    - P2P is cheaper than server client architecture because no central server is required
    - Client-server is much more secure because file access is controlled by the server and not by all the nodes
    - Performance wise does client-server perform robust while P2P the more nodes the worse the performance
- DNS
  - DNS servers, root DNS, top level, local…
  - Iterated query
  - Recursive query
  - How long it takes to get the Ip address in each queue
    - You know RTT in each server connections
    - RTT could be different for each server
- HTTP
  - The basics
    - HTTP uses TCP to communicate
    - It is stateless where it doesn't keep track of past client requests
  - Non persistent HTTP
    - At most one object at a time can be sent over a TCP connection. Meaning downloading multiple objects requires multiple connections
    - This means that sending an object over non persistent requires
    - A solution to improve the time could be to initialize multiple TCP connections in parallel
  - Persistent HTTP
    - Multiple objects can be sent over a single connection
    - One RTT for all the reference objects

## Chapter 3

**Chapter Coverage on Midterm:**

- TCP and UDP 3.6, 2.15-2.16
- Flow control and congestion control 3.75, 3.99-3.100
- Selective repeat and go back N 3.46
- Checksum 3.18

**Notes:**

- UDP and TCP
  - TCP
    - Basics
      - Reliable transport
      - Congestion control: throttle sender when network overload
      - Connection oriented
    - Example of usage
      - Email, web, file transfer
  - UDP
    - Basics
      - Unreliable transport
      - Does not provide flow control, congestion control
    - Example of usage
      - Streaming multimedia (both TCP and UDP)
      - Internet telephony (skype) both TCP and UDP
  - Both UDP and TCP transport using cleartext
    - SSL can be used to securely transfer
- Flow control
  - Receiver controls the sender, so sender won't overflow receiver's buffer
- Congestion control
  - Too many sources sending too much data too fast for a network to handle
    - Results in packets drop and increased packet delay
  - TCP RENO
    - Sets cwnd to half if packet loss is detected
    - Then grows linearly
  - TCP Tahoe
    - Sets cwnd to 1 if packet loss is detected
- Selective repeat and go back N
- Checksum
  - Understand when you can use it and when it shows and error
  - 2 flip is small chance of happening
