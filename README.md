# Multidimensional Knapsack
### Solution format
Initial solution is
- A zero solution by default (i.e. no items selected in any knapsack)
- A user provided initial solution (assuming it is provided in the right format)

**The program assumes solutions at each step are feasible**, so I make the initial solution feasible (if not already)

### Solution Tweaking
Tweaking phase just performs
- Randomly select/deselect an object from any knapsack

**I found that randomizing the number of selections actually makes solution fitness worse than just doing one in each iteration.**

It also seems that finer techniques (like exponential decay, temperature) make the solution worse instead of better

I also tried adding this step
- Randomly swap two items (taken or not) from two knapsacks

And here is what I found

#### Efficacy of Random Swapping
Simulation results demonstrate that random swapping exhibits dimension-dependent performance characteristics:

##### Empirical Observations:

Random swapping significantly improves solution convergence in high-dimensional problems with multiple knapsacks.

Its impact becomes negligible in low-dimensional problem instances.

##### Analysis:

Random swapping functions as an alternative selection/deselection mechanism that operates through item exchange rather than direct modification. This approach enables enhanced search space exploration in high-dimensional settings, as simultaneous item swaps between knapsacks facilitate access to solution configurations unreachable through standard insert/remove operations. Consequently, the algorithm gains broader neighborhood visibility.

Conversely, in low-dimensional spaces, random swapping reduces to a compressed sequence of select/deselect operations, offering no substantial advantage over simpler operators since the search space remains adequately explorable through conventional moves.

##### Conclusion: 

Random swapping effectiveness scales with problem complexity, serving as a beneficial diversification operator only when dimensionality necessitates more sophisticated exploration mechanisms.

### Solution fitness
The objective is to maximize fitness.

My approach was to give
- Total value in all knapsacks for feasible solution
- Large negative fitness for unfeasible solution (in theory any non positive fitness should work)

### Simulated annealing
To help the program escape from local minima, if the solution is worse than current solution but **still feasible**, then with probability $\epsilon$ accept that solution either way

### Global optimum
Keep track of global optimum to provide best solution found overall in the end.

---

# Disclaimer
I shared some ideas at the start of the lab with
- Davide Carletto s339425
- Michele Carena s349483
