# Networking Finale

# Part 1 – Short Questions

**Which protocols belongs to which layer**

Application layer [Application (application layer protocol)]:

- Email (SMTP, POP3 IMAP)
- Remote terminal access (Telnet)
- Web (HTTP)
- File transfer (FTP)
- Streaming multimedia, ex YouTube (HTTP)
- Internet Telephony (SIP, RTP)

Transport Layer:

- TCP
- UDP

Networking Layer

- Routing Protocols (RIP, OSPF, BGP)
- IP protocol (address convention, datagram format, packet handling)
- ICMP protocol (Error reporting, router signaling)

Link Layer

- MAC Address protocols (Channel partitioning, Random access, Taking turns)
- Random Access: slotted ALOHA, ALOHA, CSMA, CSMA/CD, CSMA/CA

**Data plane vs Control Plane**

Data plane

Forwarding, the process of moving a packet from an input port to the correct router output port. This is where the most of data transformations happens.

Control Plane

Routing, determining the route a packet should take from source to destination. This means that control plane is responsible for populating routing tables, forwarding tables. It includes the different protocols; STP, ARP, RIP, DHCP. The reason for separating them is to create a highly available system and divided the functionalities up for their respective parts.

**Control Plane implementation**

Two approaches; Per router control (traditional) & logically centralized control (software defined networking (SDN)). Per router control each router has individual routing algorithm where each router interacts with each other, typically hardware based. Logically centralized control (aka SDN) typically remote interacts with control agents in routers to compute the forwarding tables. Doing this means that we are using a centralized controller distribute the forwarding table to achieve reliability and scalability.

**Why do we need both?**

Having a SDN allows the network control logic to be implemented and operated on a global view.

**Router vs Switch**

Routers

Network layer device (examines the network layer header). Computes tables using IP addresses and routing algorithms. Allows connections between different networks.

Switch

Link layer device (examines the link layer header). Learns forwarding table using flooding.

Store & Forward: Entire packet must arrive at router before it can be transmitted on next link. Both routers and switches are store-and-forward.

**MAC and IP addresses**

MAC

Operates on the data link layer. The Mac address is used to ensure physical address of a computer. Switches stores the MAC address of devices when determining the forwarding path. Because the hardware is assigned the MAC address (sometimes could be software settable) is portable.

IP Address

IP address is a logical address of a computer, and it operates on the network layer. Is not portable and works on the network layer.

**MAC Protocols**

The protocols specify two things; how to detect collisions and how to recover from them. Random access involves Aloha, CSMA.

Channel Partitioning

Two kinds; Time division multiple access, frequency division multiple access. TDMS access to the channel in rounds where each station gets a fixed length of transmission time. Unused slots go idle. FDMA has a channel spectrum which divided the frequency bands for each station (fixed length). Unused transmission time leads to the frequency bands to go idle.

Random Access

Aloha

Two different kinds; slotted and pure. Pure allows a host to send whenever they have data to send. If they don't receive an acknowledgement, they will wait a random time before transmitting again. Slotted groups the timing to send out a packet in slots. If the sender misses the slot it will have to wait until next available slot. Therefore, slotted aloha has better performance (lower collision), double the performance. But this means that the time is on a shared channel.

CSMA

Listens before sending. If the link is busy it will wait. Collision can still happen due to propagation delay. **CSMA/CD** uses carrier sensing for detecting collision. With it, it can detect collision in a short time and abort transmissions to save channel waste. It is easy in wire LANs but difficult in wireless. If collision is detected it uses binary backoff.

Taking Turns

**Channel partitioning** performs well when the load is fairly high but is inefficient at low load. It allows hosts to access the channel in rounds. While Random access protocols perform well on low load but have high collision overhead. Therefore, taking turns uses the best of both worlds. Two different types of taking turns; polling (master tells slaves when they can transmit) and toking (a token is passed from one node to the next).

**Network vs Link layer**

Network Layer:

Divided into the control and data plane. Meaning that it handles the routing and sending data between networks.

Link Layer

Data link layer handles the communication send between devices on the same network. This means that this layer provides the means to detect and possibly correct errors such as collisions on the link.

# Part 2 – Long Questions

**IPv4 vs IPv6**

IPv4 has a 32bit address length while IPv6 has a 128bit identifier. Because of this the address space is much larger for IPv6 and was the primary reason for redesigning the address space. IPv6 is represented in hexadecimal while IPv4 is in binary. IPv6 has no checksum field, and it has a fixed 40 bytes header while IPV4 has a 20-60 bytes header. IPv4 address can be converted to IPv6 but not always the other way around.

**IPv4 Fragmentation**

Network links has a MTU (max transfer size). This means that the data packet must be divided into frames. The datagrams are then resembled at the destination. The IP header is used to identify and order of the fragments.