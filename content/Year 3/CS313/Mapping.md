> Mapping is the process of forming a map of an unknown environment based on a [[robot]]'s sensor observations.

The difficulty of the 'mapping problem' is dependent on:
- Environment size
- Perceptual ambiguity (do different places look similar?)
- Existence of cycles in the environment ([[Loop Closure|closing cycles]] are difficult)

There are two general types of maps that can be generated, namely:
- **Metric Maps** - these aim to generate the geometry of the environment (which is particularly useful for obstacle avoidance).
	- A specific type of the metric map is a **Feature-Based Metric Map**, which represents the scene as a set of landmarks.
- **Topologic Maps** represent the space as a graph with adjacent nodes representing reachability between distinct locations.

## Occupancy Grid Mapping
> The general idea here is to map occupancy as a set of binary random variables when considering the environment as a discrete map of cells.

We assume:
1. A cell is represented as either fully free or occupied (binary)
2. The environment is always static (does not change)
3. Cells are independent of each other

We can use the **inverse sensor model** to generate occupancy maps given a sensor observation.

Before a reading, we initialise every cell's probability of occupation, $p(m_{i,j}) = 0.5$, which we will designate as the prior.

When measuring a sensor reading, we can assume:
1. At $d < \text{reflection}$, there is likely free space.
2. At $d \approx \text{reflection}$, there is likely an occupied space.
3. At $d > \text{reflection}$, we must use the prior, as we have no knowledge of the space beyond.

Hence, we can use a filter to adjust our estimate of the prior:

![[Screenshot 2024-03-12 at 10.09.56.png|300]]

Doing this repeatedly and rounding all probability values can result in a good estimate of the environment's map (called the **Maximum Likelihood Map**), assuming accurate robot pose information:

![[Screenshot 2024-03-12 at 10.17.07.png|300]]