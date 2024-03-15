>An ad-hoc network is a collection of network devices without a fixed infrastructure (such as routers or access points) that wish to communicate.

Specifically, we note that **not all nodes are able to directly communicate with each other**.

A **Mobile** Ad-hoc Network (MANET) is comprised of devices that move freely (as such, cannot rely on fixed infrastructure).

## Types
There are two types of topology for ad-hoc networks:
- **Heterogenous** networks consist of nodes with different capabilities
- **Homogenous** networks have nodes with identical features and capabilities

## Use Cases
Environments which require rapid deployment such as:
- Military operational theatres
- Space exploration
- Temporary infrastructure networks

Whereas a cellular network relies on base stations and stable connectivity, mobile connections prioritise a sporadic, dynamic network, often in hostile or unfamiliar environments.

![[Screenshot 2023-10-02 at 16.48.11.png]] 

## Issues
### Scalability
This is defined as whether the ad-hoc network continues to provide an acceptable level of service for large numbers of nodes. **This is often accomplished by using routing and location hierarchy within the network.**

### Power Sources & Energy Saving
Due to the lack of fixed infrastructure, nodes commonly rely on small, portable power sources. Hence, energy efficiency is vital. Most modern solutions rely on specific routing protocols.

### [[Denial of Service Attack|Denial of Service Attacks]]
MANETs are vulnerable to DoS attacks as the comms medium is often insecure. The adaptable nature of an ad-hoc network means these attacks are often harder to track down.

### Supporting Novel Technologies
Designing ad-hoc networks that can take advantage of modern communication and signal processing techniques, such as [[Beamforming|beamforming]], have proven a challenge. In this case, most routing protocols have been designed for omnidirectional antennas, proving MANETs difficult to implement with beamforming.

### Supporting Unmanned Systems
Unmanned systems commonly integrate several aspects of operation, such as networking, decision-making and movement. As such, a challenge is combining situational knowledge with the routing layer.

### Physical RF Path Attenuation
Specifically, there is a lack of models surrounding how RF scattering occurs around real-life objects such as foliage or vehicles. The reduction in signal strength in physical environments due to interference is difficult to quantify.



## Footnotes
Citation: [A brief overview of ad hoc networks: challenges and directions - IEEE Communications Magazine (2002)](https://warwick.ac.uk/fac/sci/dcs/teaching/material/cs345/ramanathanredi_commag2002_adhocoverview_printed.pdf)

