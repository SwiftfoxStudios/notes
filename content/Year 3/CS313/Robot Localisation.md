> *Not to be confused with [[Visual Place Recognition]]*.
> 
> **Robot localisation**, or **place recognition**, is the process of determining the pose (namely, position and orientation) of a [[robot]] within a global frame of reference. 

We can use sensor data to get an idea of a robot's pose - this is essentially the first step of the [[particle filter]].

For example, given a sensor reading of $d=20cm, \theta = 45\textdegree$, we may determine the pose as one of the following places:

![[Screenshot 2024-03-12 at 10.29.10.png|300]]

Once a place is recognised, a robot can be trained to be able to [[Signature Matching|remember places]].