# Homework 4

## Question 1

**A)**

![image](https://user-images.githubusercontent.com/36133918/205082030-0ed642e4-3ccc-4d9e-9c46-c715e79e6c2c.png)

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
![image](https://user-images.githubusercontent.com/36133918/205082154-51bf0e7b-74da-46e8-a275-6b594d5deb55.png)

**B)**

### Node P Table
![image](https://user-images.githubusercontent.com/36133918/205082220-0b4d56ba-f79e-4b5a-960d-e0cca5d66c98.png)
![image](https://user-images.githubusercontent.com/36133918/205082250-1f4c9302-a502-4f41-ad39-8dedf1f79bb6.png)


### Node Q Table
![image](https://user-images.githubusercontent.com/36133918/205082326-4ca06675-35e2-4dd8-90f6-c078a96160da.png)

### Node R Table
![image](https://user-images.githubusercontent.com/36133918/205082367-9c146f70-bad1-4f4f-b5e3-ffe29b22444d.png)


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
![image](https://user-images.githubusercontent.com/36133918/205082515-c755317b-7175-4121-b656-0ff5e7841534.png)


**B)**
![image](https://user-images.githubusercontent.com/36133918/205082681-eca75e48-ac89-4b89-8bca-cd0721102a18.png)

**C)**
![image](https://user-images.githubusercontent.com/36133918/205082733-1cafad75-7aa1-4ad0-9a10-b9810821fc67.png)

**D)**
![image](https://user-images.githubusercontent.com/36133918/205082834-d6dce377-8ba7-4050-bec1-384d50c0d4db.png)

## Question 6

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
