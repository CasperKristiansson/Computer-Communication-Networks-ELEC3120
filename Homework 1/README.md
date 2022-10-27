# Homework 1

## **Question P1**

**A)**

$$ d_p=(length of physical link)/(propagation speed)=m/s $$

**B)**

$$ d_t=(packet length)/(link bandwidth)=L/R $$

**C)**

If we exclude the processing and queuing delays.

$$ d_e)=d_t+d_p=L/R+m/s $$

**D)**

When t=d_trans  the last bit will have just left its destination (Host A) and now exists in the wire on the way to Host B.



**E)**

If d_prop>d_trans and the time is t=d_trans means that the first bit that was sent to Host B hasn't arrived yet, when Host A has sent out all bits to the wire. That means when t=d_trans means that the first bit still is in the link on the way to Host B.

**F)**

If d_prop<d_trans and the time is t=d_trans the first bit will have arrived at Host B when Host A has finished sending out all bits to the wire.

**G)**

$$ d_t=m/s,d_p=L/R→m/s=L/R→m=sL/R→m=(2.5*10^8*60)/(65*10^3 )=230769m≈231km $$

## **Question P2**

Link rate=4.5Mbps,User transmission speed=250kbps, user transmission rate=15%

**A)**

$$ 4.5Mbps = 4500kbps→(Link speed)/(user transmission speed)=4500/250=18 users $$

If circuit switching is used the network can support a total of 18 users.

**B)**

In the information of the question, we can see that the probability that a given user is transmitting is 15%.

**C)**

The formula for binomial distribution is as follows: $$ ((total users)¦(transmitting users)) P^(transmitting users)*(1-P)^(idle users) $$

where P=propability that a user is transmitting.

$$ P=0.15→(200¦n)0.15^n (1-0.15)^(200-n)=〖(200¦n)*0.15〗^n*〖0.85〗^(200-n) $$

**D)**

Suppose there are 200 users. To find the probability that there are 25 or more users we can use the formula as above and just add them together with every value equal and greater to 25.

$$ P=\Sigma_{n=25}^{200}(200¦n) *〖0.15〗^n (1-0.15)^{200-n} $$

## Question P3

**A)**

10 packets, packet length 50bits, link transmission rate 5Mbps.

Total packages = 50*10=500bits
Link transmission rate = 5Mbits=5000000bits/s

Because for each transmitting delay can be formalized as L/R we can than for each of the packages. This means that the first package has 0 queuing delay, the second has L/R  and the third has 2L/R and so on.

This means that we can then summarize all of expressions into a formula to calculate the average queuing delay. The formula for calculating the average queuing delay is:

$$ ((L/R+2L/R+3L/R…(N-1)L/R))/N=(N-1)L/2R $$

The average delay then for the N packets is:

$$ ((10-1)*50)/(2*5000000)=0.000045 seconds=45 microseconds $$

**B)**

10^(-4) seconds=10000000 micro seconds delay between each of the 10 packets.

Because 45*10<10000000 each time 10 packets arrives the queue will be empty. Meaning that the average queuing delay will be the average queuing delay for the 10 packages. Which in this case is: 

$$ (N-1)L/2R=((10-1)*50)/(2*5000000)=0.000045 seconds=45 microseconds $$


## Question P4

**A)**

R_s=20Mbps,R_c=10Mbps

Because R_s=20Mbps each time the server sends a traffic it sends 2 messages while the router sends 1 message because of R_c=10Mbps. By simply graphing second for second we can see when the router starts receiving packet loss and exactly how many messages the server has sent when it happens.


|| **Total messages sent by server** | **Router buffer** | **Total messages sent by router** |
| --- | --- | --- | --- |
| **Init State** | 0 | 0 | 0 |
| **Second 1** | 2 | 0 | 0 |
| **Second 2** | 4 | 2 | 0 |
| **Second 3** | 6 | 3 | 1 |
| **Second 4** | 8 | 4 | 2 |
| **Second 5** | 10 | 5 (Packet loss) | 3 |

To clarify in the table above at any given time for example second 1 the messages that has been sent by the server has just left it and have not arrived at the router. This means that when the packages loss starts happening at second five to messages will still be on its way to the router and one packages will be on its way to the client. From the table we can than see that the server has been able to send out a total of 10 messages before the router starts to receive package loss.

**B)**

At any given time, the router buffer contains excluding second 1 when the buffer is empty. This means that when the router will start receiving packet loss. In this case above when the messages sent (10) is greater than 2x the buffer size (m) the router will start to receive packet loss.

## Question P5

**A)**

We know that when host A sends its packets the first one will arrive after two seconds . Because the packets are coming in consecutively the rest of the packets from Host A will arrive right after. This is if we ignore the transmission delay at Host A. This means that the three packets that the switch is receiving from Host A will have the following delays:

| **Delay** | **Packet nr Host A** |
| --- | --- |
| 0 | 1 |
|$$ L/R$$| 2 |
|$$ 2L/R $$| 3 |

Host B will then after seconds from the initial time send out their packets. If we as above come to the conclusion that there is no transmission delay the packets will arrive at the switch seconds after Host A.

This means that their delay will be:

| **Delay** | **Packet nr Host B** |
| --- | --- |
|$$ 3L/R- ε $$| 1 |
|$$ 4L/R- ε $$| 2 |
|$$ 5L/R- ε $$| 3 |

This means that the total delay for each of the packets summed equals:

$$ 0+L/R+2L/R+3L/R+4L/R+5L/R- 3*ε= $$
$$ 1000/1000+2000/1000+3000/1000+4000/1000+5000/1000-3*ε= $$
$$ 1+2+3+4+5-3*ε= $$
$$ 15-3*ε→ $$

If ε is very small value,the average queing delay will be $$ 15/6=2.5 seconds per packet. $$

**B)**

Using the formula as above we get:

$$ 15-3*ε where ε=1→15-3*1=12 seconds→The average queing delay is=12/6=2 seconds per packet   $$

**C)**

As we saw in the result of A the queuing delay is quite big due to the reason that all the packets are arriving at the same time from the two different hosts (ε seconds difference). If ε is very small means that the switch will have to handle six 1000 bits packets at once. But in question B we see that if host B waits for example one second before transmitting reduces the delay a lot (20%). Doing this means that the switch won’t have all the packets at once which means that the traffic intensity won’t be as high.

From the formula (15-3*ε) we can see that the higher delay before host B sends its packages the lower the overall queuing delay will be. The formula has a restriction and that is that ε<3L/R. Because otherwise the events would be independent where the switch queue will be empty when the first packet from Host B arrives.

In the questions above I did come to the conclusion that there is no transmission delay. But in a real-world example there would be a transmission delay which would impact the result.