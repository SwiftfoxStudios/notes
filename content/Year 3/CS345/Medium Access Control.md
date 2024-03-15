> **Medium** or **Media Access Control** are a collection of protocols that describe transmission across the [[Sensor Node#Data|data link layer]].
## S-MAC
> Sensor Medium Access Control is based on [[CSMA-CA#Handshaking|Carrier Sensing with Handshaking]]. 
> It is characterised by periods (cycles) of sleeping and listening for data packets.

Nodes exchange schedules with their neighbours before beginning the cycle.
![[Screenshot 2023-10-16 at 14.22.28.png|400]]


## B-MAC
> This is considered an improvement on S-MAC, aiming to remove the need of SYNC packets being exchanged to synchronise transmissions. **In B-MAC, nodes must all have the same cycle length.**

**B-MAC** replaces RTS/CTS handshaking with *clear channel assessment*. There is also no need for synchronisation. 

### Clear Channel Assessment
> CCA relies on generating a noise floor within a signal graph for transmission detection.

![[Screenshot 2023-10-16 at 14.33.52.png|400]]

**N.B. A sample of the channel is taken after packet transmission, where noise is stable, to generate a noise average.**

### Low Power Listening
> In LPL, a preamble is sent before each packet to alert the intended recipient. The length of the preamble must be at least the length of the cycle, $T_p$.

![[Screenshot 2023-10-16 at 15.02.25.png|400]]

## X-MAC
X-MAC reduces energy consumption by reducing the length of the preamble and using **preamble strobing** to keep gaps in transmission such that bidirectional transmission is improved and latency reduced:

![[Screenshot 2023-10-16 at 15.29.12.png]]

An **early acknowledgement** is used to confirm reciept of the preamble.