# Homework 4

## Question 1

**A)**

![](RackMultipart20221201-1-uqlweg_html_407fb5fadeda0adc.png)

**B)**

|    <br>N’          	|    <br>D(A), p(A)    	|    <br>D(B), p(B)    	|    <br>D(C), p(C)    	|    <br>D(D), p(D)    	|    <br>D(E), p(E)    	|    <br>D(F), p(F)    	|    <br>D(G), p(G)    	|    <br>D(H), p(H)    	|
|--------------------	|----------------------	|----------------------	|----------------------	|----------------------	|----------------------	|----------------------	|----------------------	|----------------------	|
|    <br>C           	|    <br>∞             	|    <br>∞             	|    <br>-             	|    <br>4, C          	|    <br>3, C          	|    <br>∞             	|    <br>9, C          	|    <br>8, C          	|
|    <br>CE          	|    <br>∞             	|    <br>∞             	|    <br>-             	|    <br>              	|    <br>              	|    <br>∞             	|    <br>              	|    <br>8, C          	|
|    <br>CED         	|    <br>∞             	|    <br>∞             	|    <br>-             	|    <br>              	|    <br>              	|    <br>8, D          	|    <br>              	|    <br>6, D          	|
|    <br>CEDH        	|    <br>11, H         	|    <br>∞             	|    <br>-             	|    <br>              	|    <br>              	|    <br>              	|    <br>              	|    <br>              	|
|    <br>CEDHF       	|    <br>11, H         	|    <br>11, F         	|    <br>-             	|    <br>              	|    <br>              	|    <br>              	|    <br>              	|    <br>              	|
|    <br>CEDHFG      	|    <br>10, G         	|    <br>              	|    <br>-             	|    <br>              	|    <br>              	|    <br>              	|    <br>              	|    <br>              	|
|    <br>CEDHFGA     	|    <br>              	|    <br>              	|    <br>              	|    <br>              	|    <br>              	|    <br>              	|    <br>              	|    <br>              	|
|    <br>CEDHFGAB    	|    <br>              	|    <br>              	|    <br>              	|    <br>              	|    <br>              	|    <br>              	|    <br>              	|    <br>              	|

**C)**

| Destination | Next Hop | Shortest path cost |
| --- | --- | --- |
| A | **G** | **10** |
| B | **D** | **11** |
| C | **C** | **0** |
| D | **D** | **4** |
| E | **E** | **3** |
| F | **D** | **8** |
| G | **G** | **9** |
| H | **D** | **6** |

## Question 2

**A)**

**B)**

### Node P Table

### Node Q Table

### Node R Table


## Question 3

**A)**

Router 3c learns the prefix of x from eBGP

**B)**

Router 3a leans the prefix of x from iBGP

**C)**

Router 1c learns the prefix of x from eBGP

**D)**

Router 1d learns the prefix of x from iBGP.

## Question 4

**A)**

We can find the optimal value of p by derivation the expression and setting it equal to 0. Because we have 2 unknown variables N and p we can see N as a constant instead of a variable when performing derivation.

$$ ∂/∂p Np(1-p)^(N-1)=N((1-p)^(N-1)-(N-1)p(1-p)^(N-2) ) $$

We then set it equal to 0

$$ N((1-p)^(N-1)-(N-1)p(1-p)^(N-2) )=0 $$

**B)**

I couldn't find the maximum value of p. But if we leave out p the expression would be:

$$ lim┬(N→∞)⁡〖Np(1-p)^(N-1) 〗$$

where p is the optimal value based on N.

**C)**

This means that pure ALOHA will have a maximum efficiency of:

$$ lim┬(N→∞)⁡〖Np(1-p)^(N-1) 〗=1/2e $$

# Question 5

**A)**

**B)**

**C)**

**D)**


# Question 6

**A)**

| **Path** | **Source MAC** | **Destination MAC** | **Source IP** | **Destination IP** |
| --- | --- | --- | --- | --- |
| **From A to C** | A0-43-5B-CC-06-7D | EE-F3-56-FC-26-12 | 192.168.10.8 | 192.168.10.12 |
| **From C to B** | 42-73-BB-0A-06-87 | 13-05-32-EF-DD-02 | 192.168.10.8 | 192.168.10.12 |

**B)**

Yes, it will. This is because the switches tables are initially empty which means that it has no information where Host B is located. This means that it will forward the broadcast packet to find out more information on the network. Meaning that it will flood all ports beside the incoming port with the ARP packet. Doing this host E will receive the ARP query packet that initially was sent from host A.

**C)**

| **MAC Address** | **Interface** |
| --- | --- |
| A0-43-5B-CC-06-7D | 1 |
| 13-05-32-EF-DD-02 | 2 |

**D)**

Yes. This is because in the given scenario host E doesn't not know the MAC address of host B and therefore needs to send out an ARP query. But because switch C knows which interface leads to the correct MAC address it will not forward the ARP query packet to interface 1. Meaning that host A will not receive the ARP query packet.

**E)**

| **MAC Address** | **Interface** |
| --- | --- |
| A0-43-5B-CC-06-7D | 1 |
| 13-05-32-EF-DD-02 | 2 |
| 7D-51-12-F3-EE-06 | 3 |