This is a problem in wireless networking
> Consider two [[Sensor Node|nodes]], $S_2, S_3$ - which are within each other's transmission range and wish to transmit data - and $A,B$ which receive data.

If $S_2$ is transmitting to $A$ and $S_3$ wishes to transmit to $B$, $S_2$ is left in a busy-wait due to $S_1$'s transmission:

![[Screenshot 2023-10-12 at 11.35.52.png]]