> **Routing** is the process of path selection for packet transmission.
## Flooding
**Flooding** is an example of a routing method. Considering a source node, $S$, and destination node, $D$, a flooding algorithm will recursively broadcast to all neighbours of the source node until $D$ is reached.

> **N.B.** Whilst flooding is simple and can be efficient when transmitting low data volumes, there is the potential for high overheads and there is a large power wastage; data is sent unnecessarily to many nodes.

In [[Wireless Sensor Network|wireless sensor networks]], flooding has three major issues:
- **Implosion**: multiple copies of the same data sent to the same node. This can be mitigated using **smart gossiping**, where transmission to a single random neighbour is selected according to a probability function, measured by sensor density in a given area.
- **Sensor Overlap**: sensors sensing similar regions return similar data.
- **Resource Blindness**
## Dynamic Source Routing (DSR)
**DSR** is built upon the fundamentals of flooding, but introduces a **TTL** for maximum number of hops. DSR introduces three types of packets.

- **Route Request (RR)** packets are flooded into the network and at any given time $t$ contain the route from $S$ to the current node at $t$, as well as the source and destination.
- **Route Reply (RRp)** packets are sent once the transmission reaches $D$, by reversing the route contained within the RR packet.
- When a link breakage is detected along a transmission path, a **Route Error (RE)** packet is sent back to $S$.

> **N.B.** DSR cannot locally repair broken links in the network; the network has to be re-flooded. Moreover, as the entire route is contained within the packet header, there is a large packet overhead.

## Ad-hoc On-demand Distance Vector Routing (AODV)
**AODV** stores cached route information locally (at the node), representing the previous hop as a pointer within a **RR** packet. For example, consider a route:
$$S \to N_1 \to N_2 \to D$$
At $N_2$, the packet contains a pointer to the previous hop, $N_1$. This is reversed for an **RRp** - when the packet reaches $D$, it has the route to send the **RRp**, as each node contains a pointer to the previous node.

Cached route information contains $D$ and the next hop - in this case, also $D$. It will also contain a timeout value.

## Routing in WSNs
There are four major methods of routing in [[Wireless Sensor Network|wireless sensor networks]]:
### Data Centric Routing
> DCR methods aim to route information from sensor nodes to the sink when data at that sensor meets a given criterion. **A large issue with this is data overload near the sink due to a larger density.**
#### Directed Diffusion (DD)
There are four stages to constructing routes within this method.
- **Interest Propagation** - the sink [[#Flooding|floods]] the network with interest messages for data that matches a given criterion.
- **Gradient Setup** - gradients indicate the node from which the interest originated. [[Sensor Node|Sensor nodes]] that match the criterion will then become source nodes and send the data along the gradient.
- **Reinforcement** - the route becomes reinforced by sending more data along it. This increases the data rate along that route.
- **Data Delivery** - positive reinforcement increases the data rate. This is complemented by negative reinforcement, for when an alternative route is preferred. The data rate is reduced.
#### Rumour Routing
- Nodes that sense an event sends a data packet along a random walk. This route is propagated to each agent along the walk.
- **Meanwhile**, if the sink is interested in an event, it will send a query on a random walk. The idea is **'meet in the middle'**.
- This method also allows agents to shorten existing paths if one exists.

### Hierarchical Routing
To solve the data density issue in DCR methods, we can use **hierarchical routing**.
> In **HR**, nodes are split into groups (clusters) with a leader (cluster head).
#### Low Energy Adaptive Clustering Hierarchy (LEACH)
> **LEACH** is a standard for HR methods. The clusters sense data, transmit this data to cluster heads, who aggregate the data and transmit it to the sink. Each node uses a stochastic algorithm to determine whether it will be the cluster head in the next round. This spreads out battery usage, improving lifetime.

![[Screenshot 2023-10-24 at 16.36.24.png]]
### Geographical Routing
> When the physical location of nodes are known, it is wise to take advantage of this. Whilst GPS is energy inefficient and costly, other heuristic methods can be used for localisation, such as **signal strength algorithms**.

This culminates in what is known as **Greedy Forwarding**, where packets are forwarded according to a specific metric. Four example metrics are seen in the image below:
![[Screenshot 2023-10-24 at 16.39.22.png|500]]
Greedy forwarding may fail in specific scenarios. For example, consider a scenario where two sensors are geographically close with an impenetrable medium between them, **such as a wall**.

Likewise, like many heuristic-based algorithms, it may get trapped in a local maximum, such as below.
![[Screenshot 2023-10-24 at 16.41.37.png|300]]

Because greedy schemes may fail, we consider **Greedy Perimeter Stateless Routing (GPSR)**.
![[Screenshot 2023-10-31 at 16.02.56.png|400]]
Essentially, we use Greedy Routing until it fails. After this, we use **Perimeter Routing**, picking the next node that aligns closest to the direction of the destination, without overshooting it (this would result in a loop). This is seen below:
![[Screenshot 2023-10-31 at 16.31.12.png|200]]
The general idea here is that if we ever have to backtrack, we use **Perimeter Routing** in order to find an alternative route.

### Quality of Service Based Routing
> QoS finds optimal routes given a specific criterion (e.g. throughput)
#### Minimum Cost Path Forwarding
This is a heuristic based implementation that calculates the minimum cost of all the paths calculated between the sink and a given node, such that:
$$C_{val} = \min\{C_{in} + cost(C,C_{in})\}$$