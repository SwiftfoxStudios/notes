**Wireless Sensor Networks** are a type of [[Ad-Hoc Network|ad-hoc network]] in which [[Sensor Node|sensor nodes]] can interact with the environment through on-board sensors whilst handling information and communicating with other nodes.

They are commonly represented as undirected graphs:
![[Screenshot 2023-10-04 at 16.59.52.png]]

## Communication Principles
Nodes act as a host but may *also* act as a router.
As such, we can characterise communication between nodes as such:
### Detection & Mobility
New nodes are detected when in range to other nodes (such as two bluetooth devices in close proximity).

When a node is removed from the network, the other nearby nodes reconfigure themselves.
This principle can affect routing. Consider the change in shortest path after the removal of $x$ below.
![[Screenshot 2023-10-04 at 18.53.12.png]]
### [[Routing]]
Where two nodes are adjacent, a **single-hop** is performed. This is a direct connection between two nodes. Where this is not the case, a **multi-hop** can be performed, in which other nodes act as routers to forward the connection.

Traffic may impact routing. In the case below, where heavy traffic exists on the channel $S_2 \to D_2$, the alternative route in black may be chosen:![[Screenshot 2023-10-04 at 19.26.28.png]]

