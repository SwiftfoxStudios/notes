> A **sensor node** or **mote** is an individual node of a [[Wireless Sensor Network|sensor network]] capable of handling and processing data and performing desired actions.

It typically consists of:
- Microcontroller
- Transceiver
- Power Source
- Memory Unit
- Sensors

Sensor nodes can be modelled using a **four-layer** stack:
## Application

## Network
The network layer is responsible for packet forwarding by [[Routing#Routing in WSNs|routing]].
## Data
The data layer is concerned with transmissions. For our specific purposes, we will consider that nodes are **half-duplex** so can either transmit or receive at any given time, but not both. As such, methods of transmission are usually governed by [[Medium Access Control]] protocols and multiple access methods. One such method is [[CSMA-CA]].

We'll characterise two main issues. The [[Hidden Node Problem]] and the [[Exposed Node Problem]].
## Physical
> The role of the physical layer is to convert binary or analog data into signals suited for wireless transmission.
### Operation
Data is taken from the upper layer and passed through a [[Modulation|modulator]] to convert it:

![[Screenshot 2023-10-05 at 10.28.34.png]]

Communications typically employ electromagnetic waves. The bandwidth determines the transmission capacity, $C$, such that:
$$C=B \cdot \log_2(1+\frac{S}{N})$$
for bandwidth $B$ and signal-to-noise ratio $\frac{S}{N}$. Typically, transmission occurs over the ISM band, commonly $2.4GHz$.

When data needs to share a medium, [[Multiplexing|multiplexing]] can be implemented.
### Issues
Electromagnetic waves suffer from four main effects which affect signal transmission.
#### Path Attenuation
Primarily, signal strength decreases as a function of distance. A node's transmission range is the specific maximum distance at which the node's receiver is still sensitive enough to receive incoming transmissions.

#### Reflection & Refraction
EM waves bounce (reflect) off of or refract across a medium's boundary. This may change the direction, strength and characteristics of the signal.![[Screenshot 2023-10-05 at 16.34.56.png]]
#### Diffraction
When EM waves propagate through a sharp edge, they may diffract, splitting the signal into several weaker instances of itself.
#### Scattering
EM waves may scatter when incident to a rough surface, splitting and changing direction.![[Screenshot 2023-10-05 at 16.38.52.png]]

#### Doppler Fading
Another well known issue is that of **doppler fading**. Due to the [[Doppler Effect]], moving nodes undergo a shift in frequency. We note that:

- A signal being transmitted over a distance that is shrinking (such as when the objects are moving closer together) will show a relative increase in frequency.
- Conversely, over an increasing distance, we note a relative decrease in frequency.



### Error Detection & Correction
There are two common simple methods of error detection: **Parity bits** and **Checksums**. These both modify the initial data but **do not provide a method of locating or correcting errors**.

To combat these, [[Forward Error Correction]] techniques can be used, as well as [[Spread Spectrum]] techniques.