# Homework 2

# Question 1

$$ F=3 Gbits=3000 Mbps,u_s=60,d_i=3Mbps $$

**A)**

Time to distribute F to N clients using client-server approach:

$$ D_(c-s)≥max⁡(NF/u_s ,F/d_min ) $$

$$ N=10,→max⁡((3000*10)/60,3000/3)=max⁡(500,1000)=1000 $$

$$ N=100→max⁡{(3000*100)/60,3000/3}=max⁡{5000,1000}=5000 $$

$$ N=1000→max⁡{(3000*1000)/60,3000/3}=max⁡{50000,1000}=50000 $$

|| **Upload rate: 0.3 Mbps** | **Upload rate: 1 Mbps** | **Upload rate: 3Mbps** |
| --- | --- | --- | --- |
| **Peers: 10** | 1000 | 1000 | 1000 |
| **Peers: 100** | 5000 | 5000 | 5000 |
| **Peers: 1000** | 50000 | 50000 | 50000 |

**B)**

$$ D_{2P2}≥max⁡{F/u_s ,F/d_{min} ,NF/((u_s+∑u_i ) )} $$

#

$$ N=10,u=0.3→max⁡{3000/60,3000/3,(10*3000)/((60+0.3*10) )}=max⁡{50,1000,476}=1000 $$
$$ N=10,u=1→max⁡{3000/60,3000/3,(10*3000)/((60+1*10) )}=max⁡{50,1000,428.57}=1000 $$
$$ N=10,u=3→max⁡{3000/60,3000/3,(10*3000)/((60+3*10) )}=max⁡{50,1000,333}=1000 $$

#

$$ N=100,u=0.3→max⁡{3000/60,3000/3,(100*3000)/((60+0.3*100) )}=max⁡{50,1000,3333.33}=3333 $$
$$ N=100,u=1→max⁡{3000/60,3000/3,(100*3000)/((60+1*100) )}=max⁡{50,1000,1875}=1875 $$
$$ N=100,u=3→max⁡{3000/60,3000/3,(100*3000)/((60+3*100) )}=max⁡{50,1000,833.33}=1000 $$

#

$$ N=1000,U=0.3→max⁡{3000/60,3000/3,(1000*3000)/((60+0.3*1000) )}=max⁡{50,1000,8333.33}=8333.33 $$
$$ N=1000,u=1→max⁡{3000/60,3000/3,(1000*3000)/((60+1*1000) )}=max⁡{50,1000,2830.19}=2830.19 $$
$$ N=1000,u=3→max⁡{3000/60,3000/3,(1000*3000)/((60+3*1000) )}=max⁡{50,1000,980.39}=1000 $$



|| **Upload rate: 0.3 Mbps** | **Upload rate: 1 Mbps** | **Upload rate: 3Mbps** |
| --- | --- | --- | --- |
| **Peers: 10** | 1000 | 1000 | 1000 |
| **Peers: 100** | 3333.33 | 1875 | 1000 |
| **Peers: 1000** | 8333.33 | 2830.19 | 1000 |

# Question 2

**A)**

$$ 2*t+3*2t=8t $$
It requires one RTT to establish a connection and then a total of four different RTTs.

**B)**
$$ 2*t+3*2t=8t $$

It requires one RTT to establish a connection and then a total of four different RTTs.

**C)**
$$ 2t $$

It requires one RTT to establish a connection and then the local DNS will return the result during the next RTT. This is the same for both scenarios.

# Question 3

Document size = 1KB, image size=50KB, download rate=1Mbps=1000kbps, RTT=0.1s

**A)**

Nonpersistent HTTP = 2RTT+ file transmission time

This means that for each object it will take 2RTT + file transmission time

Transmission delay = L/R

$$ 5(2RTT+(50*8)/1000)+1(2RTT+(1*8)/1000)=3.208s $$

**B)**

$$ 2(2RTT+(50*2*8)/1000)+1(2RTT+(50*8+1*8)/1000)=2.608s $$

**C)**

$$ 1(2RTT+(50*5*8+1*8)/1000)=2.208s $$

**D)**

$$ 1RTT+(1RTT+(50*5*8+1*8)/1000)=2.208s $$

**E)**

*Nonpersistent:*

$$ (2*RTT_{avg}+L_d/R)+N(2*RTT_{avg}+L_i/R) $$

*Persistent:*

$$ RTT_{avg}+(RTT_{avg}+(L_d+N*L_i)/R) $$

# Question 4

Byte 1: 01110000, Byte 2: 00101101, Byte 3: 11000011

**A)**

| **Byte 1** | 0 | 0 | 1 | 1 | 1 | 0 | 0 | 0 | 0 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| **Byte 2** | 0 | 0 | 0 | 1 | 0 | 1 | 1 | 0 | 1 |
| **Sum 1** | 0 | 1 | 0 | 0 | 1 | 1 | 1 | 0 | 1 |
| **Byte 3** | 0 | 1 | 1 | 0 | 0 | 0 | 0 | 1 | 1 |
| **Sum 2** | 1 | 0 | 1 | 1 | 0 | 0 | 0 | 0 | 0 |
| **Wraparound** | 0 | 0 | 1 | 1 | 0 | 0 | 0 | 0 | 1 |
| **1's Complement** | | 1 | 0 | 0 | 1 | 1 | 1 | 1 | 0 |

**B)**

The reason that UDP uses checksum is to detect errors with the transmitted packet. Compared to TCP, UDP is connectionless meaning that to verify that the correct packages have been received the receiver will calculate the 1s complement of the sum of the packages and add it to the checksum in the headers

In detail it works as follows; we first add all the bits of the packages together using wraparound. Then we take the 1's complement of the calculated checksum which will result in inverted bits of the result. We then add that result with the checksum in the headers. This calculation should result in a length of bits that should be equal to all 1s. If the calculation contains any 0s we know that there exists a bit error.

**C)**

No, if a 1-bit error occurs the error will not go undetected because when the receiver calculates the 1s complement with the checksum the bit error will show.

**D)**

Yes, it is. This is because if two bytes would both be corrupted (bits switching) the sum could be equal to the real sum. For example: Byte 1: 101 (Real 100), Byte 2: 010 (Real 011), Sum: 111 (Real 111). In this example both packages are wrong, but no error is detected.

**E)**

As mentioned, there are situations where different bit errors could work against each other meaning that computed Internet checksum could match up with the checksum field even though multiple bit errors could have happened. This means that with UDP the checksum can't with 100% certainty tell if no bit errors have occurred.

## Question 5

**A)**

Sequence number: 128 + 50 = 178

Source port number: 133

Destination port number: 100

**B)**

acknowledgement number: 178

Source port number: 100

Destination port number: 133

**C)**

Acknowledgment number: 128

**D)**

![](RackMultipart20221028-1-8szgt1_html_52e9a465dfbcb7a.png)
