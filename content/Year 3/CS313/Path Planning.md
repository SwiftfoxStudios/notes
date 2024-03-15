> **Path planning** is the process of a [[robot]] traversing an environment (therefore, finding an optimal path) to a given goal.

The goal of the **path planning problem** is to:
- Determine a min-cost, collision-free path to the goal state
Given:
- Starting pose
- Desired pose
- Geometric description of the robot
- Geometric description of the environment (a map)

## Process (Representation)
We can define a *[[Configuration Space]]*, which represents all possible configurations of a robot in its environment.

We then discretise the c-space for path planning. There are multiple representations for this:

### Roadmaps
We can form a set of paths based on the positions of obstacles (and the start/goal locations).
There are two main representations here:
#### Reduced Visibility Graph ($O(N^2 \log N)$)
We define the set of nodes as:
- $Q_{start}, Q_{end}$ and the corners of obstacles.
We can then link nodes iff:
- The line connecting them is en edge of an obstacle, **or**,
- The line lies entirely within free space.

We can then reduce this by only considering lines which continue past obstacles.

![[Screenshot 2024-03-12 at 11.57.13.png|400]]
#### Voronoi Diagram ($O(E \log E)$)
The idea here is to maximise the distance between the [[robot]] and obstacles in the environment. It finds the closest obstacle at all points in the environment. As such, it results in a set of edges that can be traversed (where the edges are equidistant from multiple obstacles):

![[Screenshot 2024-03-12 at 12.01.37.png|300]]

### Cell Decomposition
#### Exact Cell Decomposition ($O(N \log N)$)
This is rarely used due to the nontrivial nature of implementation. We can divide the space into a set of cells at points where one of an obstacle's nodes lie (in vertical or horizontal space):

![[Screenshot 2024-03-12 at 12.06.49.png|300]]
Essentially, we are then left with a solution for the path based upon the reachability of cells:

![[Screenshot 2024-03-12 at 12.07.12.png|300]]
#### Approximate Cell Decomposition ($O(N^{dim})$)
As an alternative, we can decompose the space into a grid of occupied, mixed, and free cells. The mixed cells can be further decomposed up to a threshold size.

![[Screenshot 2024-03-12 at 12.11.48.png|300]]
We can then determine reachability using this grid-like representation by creating a connectivity graph.

**This, however, is not complete, as a grid that is not decomposed enough may not ever return a path.**

### Sampling
We can use random sampling to generate paths.
#### Probabilistic Roadmap ($O(N^{dim})$)
We can generate samples that are not within the obstacle space and connect the nearest samples together. This method tends towards completeness at infinite samples.

![[Screenshot 2024-03-12 at 14.23.58.png|300]]
#### Single Query Planning: Rapidly-exploring Random Trees ($O(N^{dim})$)
We can reduce the complexity by only considering the paths between the start and goal, rather than the entire c-space.

We use *rapidly-exploring random trees* - this is based on forming a tree structure from the start and/or goal nodes, based on the random position of subsequent nodes (ignoring nodes that cause collisions).

![[Screenshot 2024-03-12 at 14.23.40.png|300]]
### Potential Field
The potential field model considers the robot being attracted to a goal, whilst being repulsed by obstacles.

We define the active potential, based on some scaling parameter, $k_a$, as:
$$
U_{att}(q) = \frac{1}{2}k_a (q_{start} -q_{goal})^2
$$
We can then differentiate this to get the force, which is negative (attraction):
$$
-\frac{dU_{att}}{dq} = -\frac{1}{2}k_a \cdot 2(q_{start} -q_{goal}) = -k_a(q_{start} -q_{goal})
$$
We also require a repulsive potential for obstacle avoidance. This force will only operate when the robot is within the avoidance radius of the obstacle, $\rho_0$. We can generate this as:
$$
U_{rep}(q) = \frac{1}{2}k_r(\frac{1}{\rho_q}-\frac{1}{\rho_0})^2
$$
With $\rho_q$ being the distance to the obstacle.

This can be summed over all nearby obstacles to generate an overall potential.
We can derive the force vector as:
$$
-\frac{dU_{rep}}{dq} = -k_r(\frac{1}{\rho_q}-\frac{1}{\rho_0}) \cdot \frac{d}{dq}(\frac{1}{\rho_q}) = k_r(\frac{1}{\rho_q}-\frac{1}{\rho_0}) \cdot (\frac{1}{\rho_q^2})
$$
**Note the positive sign in the final value.**

We can then determine a force vector as the sum,
$$
	F(q) = F_{att} + F_{rep}
$$

One issue with this approach is that it is prone to getting trapped in a local minimum, so **is not complete**.

## Process (Searching)
Once a representation is chosen, the space has to be searched for a solution.

When searching, we assume:
- The robot knows where it is
- The map is correct
- The correct motion commands are executed

### Uninformed Search
> We are uninformed if there is no additional information about the goal.

Generally, these search algorithms are the three classical ones:
- BFS (+ Grassfire, a robotics implementation)
- DFS
- Dijkstra's

### Informed Search
> We can implement heuristic functions when the goal state is known, such as the Manhattan distance to the goal.

**Greedy Best First Search (Greedy BeFS)** adds a heuristic to Dijkstra's algorithm; it always takes a path if it the child is lower cost than the parent. This can result in long paths.

[[A*]] is the most common implementation of informed search.

### Local Search
We can ignore the global nature of the pathfinding (if cost-min is less of an issue).