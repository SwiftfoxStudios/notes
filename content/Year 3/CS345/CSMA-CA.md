> **Carrier-Sense Multiple Access with Collision Avoidance** is a transmission method which relies on the use of **idle-checking** for effective transmission.

## Example Without Handshaking

Given the example network below, with arrows indicating a request for transmission:

![[Screenshot 2023-10-12 at 11.58.35.png|200]]

With transmission requests according to the table, assuming we have an **inter-frame spacing (IFS)** time of 2 and each packet takes 4 seconds to transmit:

| Node | Time Epoch |
| ----------- | ----------- |
| $S_1$ | 0 |
| $S_2$ | 3 |
| $S_3$ | 5 |

We can note what occurs at each time interval as such:

| $T_n$ | Event |
| ----------- | ----------- |
| 0 | $S_1$ attempts to transmit, IFS window opens. |
| 2 | IFS window closes. Data begins transmission. |
| 3 | $S_2$ attempts to transmit but connection is busy. Fails. |
| 5 | $S_3$ attempts to transmit but connection is busy. Fails. |
| 6 | $S_1$ transmission ends. |

At this time interval, the **contention window** opens. This is when all transmissions that have been forced to wait get assigned a random position aligning to **back-off time** before transmitting. In the case where $S_2$ and $S_3$ pull a time of 4 and 5 respectively, we have:
![[Screenshot 2023-10-13 at 18.45.56.png|500]]
After this contention window closes, another will open.

> **Issue:** The [[Hidden Node Problem]].
> ![[Screenshot 2023-10-13 at 18.50.11.png|200]]

If two nodes aren't communicating but are both requesting to transmit a packet, a collision will occur:
![[Screenshot 2023-10-13 at 18.51.47.png|500]]


## Handshaking
We need handshaking to solve the [[Hidden Node Problem]].
### Transmitter
Essentially, the node requesting to transmit does two things:
> - If the channel is idle, transmit an RTS, else, wait.
> - If a CTS is received, transmit data, else, wait.
> - 
![[Screenshot 2023-10-16 at 13.33.54.png|400]]
### Receiver
> - The receiver waits for an RTS. It responds to it with a CTS unless one has already been sent.
> - Once the packet is transmitted, it sends an ACK to notify the network that the channel is clear.



> How does handshaking solve the [[Hidden Node Problem]]?

Essentially, only one packet can be successfully transmitted at a time, once a CTS is received.