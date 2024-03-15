> A **project** is a temporary endeavour undertaken to provide a unique service or result.
## Scope
### Triple Constraint
> The triple constraint demonstrates the three axes of critical project focus in regards to deliverables.

![[Screenshot 2023-10-24 at 11.54.59.png|300]]

It states that changes in one constraint must mean compensation in others. As such, the PM may trade focus between constraints.

**Typically, all three constraints are unattainable for a single project: "Good, fast, cheap. Choose two."**

### Work Breakdown Structure (WBS)
> A project should be broken down into **components**, which is further broken down into **work packages (WP)**

A work package should have minimal horizontal interaction. As such, they should group tasks into relevant chunks. They should be easy to parallelise.

- Smaller **WPs** are more estimable and measurable, but harder to define - risking horizontal overlap.
- Larger **WPs** are easier to manage and are typically more efficient but risks the PM having less control and may overrun.
### Critical Path Method (CPM)
We can draw a **Project Network Diagram** which shows dependencies between tasks within a project. This can be extended to find the **critical path** in a network - this will allow us to detect bottlenecks.

We describe an algorithm to generate the critical path network:

- Start with a **PND**.
 ![[Screenshot 2023-10-24 at 12.27.51.png|400]]
We note every activity has 6 parts.
- We begin the **forward pass**. Starting with the start activity and continuing to the end, we find:
	- $ES = \max\{EF\}_{pred}$
	- $EF = ES + D$
- Then, we complete the **backward pass**. Startting with the end activity and continuing to the start, we find:
	- $LF = \min\{LS\}_{succ}$
	- $LS = LF-D$
- Finally, we may find the *slack* with $TF = LS - ES = LF - EF$.
- We may find the *drag* with $\min\{D, \min\{TF\}_{parallel}\}$.


## Budgeting & Forecasting
> The process of budgeting is creating a cost estimate. This is split into sections.
### Cost Management
> Initially, estimating a cost involves accounting for overspend and uncertainty. This creates the need for reserve funds in an estimate - **contingency funds**.
### Activity Management
> This is the need for a cost estimate for a given activity. This may be, for example, **cost per hour**, for human resource allocation.

AM may also include estimation curves, as used with the PERT method for time management.
Breaking a project down (using a WBS) makes it easier to estimate activity costs.
### Earned Value Analysis
We can use several values to keep track of a project's cost status.
![[Screenshot 2023-11-06 at 16.06.03.png|300]]
We note:
- PV = Budget at time $t$
- AC = Cost, $t_0 \to t$
- EV = $PV_{t} \cdot \%done$
Taking a look at the lines above, we can draw some conclusions:

The gap between EV and AC ($EV - AC$) is the **cost variance**, defined as the magnitude of budget deficit or surplus.
- $(EV - AC) > 0$ implies the project is under budget.

The gap between EV and PV ($EV - PV$) is the **schedule variance**, defined as how delayed or ahead of schedule the project is.
- $(EV - PV) > 0$ implies the project is ahead of schedule.

In terms of a graph, **an ideal scenario is where** $EV > PV$ and $EV > AC$.

To further this, SPI, CPI and CSI can be introduced.
- $SPI = \frac{EV}{PV}$
- $CPI = \frac{EV}{AC}$
- $CSI = SPI \cdot CPI$

SPI is a ratio measure of how on-schedule ($SPI = 1$) a project is.
CPI is a ratio measure of how at-budget ($CPI = 1$) a project is.
As such, CSI is a measure of overall efficiency.
#### Forecasting
> This can also be done with [[#Earned Value Analysis]].

There are several forecasting methods:
- **Estimate at Completion**, ($EAC = \frac{BAC}{CPI}$), estimates total cost based on current progress.
- **Estimate to Complete**, ($ETC = EAC - EC$), estimates the remaining cost of work.
- **Variance at Completion**, ($VAC = BAC - EAC$), is the derivation from budget. 
- **To-Complete Performance Index** is the *cost efficiency* required to achieve the BAC or EAC, below:
$$TCPI_{BAC} = \frac{BAC - EV}{BAC - AC}$$$$TCPI_{EAC} = \frac{BAC - EV}{EAC - AC}$$
