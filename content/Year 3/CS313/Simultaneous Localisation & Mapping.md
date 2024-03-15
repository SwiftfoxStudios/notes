> **SLAM** is the problem of [[Robot Localisation]] and [[Mapping]] combined. Specifically, building a map of an environment whilst keeping track of the [[robot|robot's]] pose inside it.

This is a joint process of estimating a pose and building a map based upon it, iteratively. It is used when:
- Full autonomy required
- Unknown environment
- Cannot localise within a global reference frame, for example, by using [[GPS]].

## Process
Whilst the process is iterative, it can be divided into the following sections:
### Sensing & Feature Detection
>*See: [[Sensing]], [[Feature (& Corner) Detection]]*.

A robot first uses a sensor to visualise the environment it is in. It can then perform feature detection on the resulting images.

### Place Recognition
> *See: [[Robot Localisation]], [[Visual Place Recognition]]*.

The robot can then identify places based on features.

### Feature Matching
> *See: [[Signature Matching]]*.

The robot can then match features to ones already identified. This allows for [[Loop Closure]] within the environment.

## Representation
As with [[Mapping]], there are two types of maps created by SLAM.

### Metric SLAM
The metric representation (which aims to build a grid of locations), suffers from poor computational performance, feature matching and large uncertainty at greater distances.

### Topological SLAM
![[Screenshot 2024-03-12 at 11.18.30.png|500]]

This is less computationally intensive and simpler; it shows the reachability of visited places, rather than geographical information.

### Topological-Metric SLAM
In practice, we can add metric information to a topological map. 
We do this by modifying edges in the topological map according to motion information. In practice, this may mean edges represent real distances between locations.

