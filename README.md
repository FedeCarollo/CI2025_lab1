# Multidimensional Knapsack
### Solution format
Initial solution is
- A zero solution by default
- A user provided initial solution

**My program assumes solutions at each step are feasible**, so I make the initial solution feasible (if not already)

### Solution Tweaking
Tweaking phase is composed of two steps
- Randomly select/deselect an object from any knapsack
- Randomly swap to items (taken or not) from two knapsacks

### Solution fitness
The objective is to maximize fitness.

My approach was to give
- Total value in all knapsacks for feasible solution
- Negative fitness for unfeasible solution

### Simulated annealing
To help the program escape from local minima, if the solution is worse than current solution but **still feasible**, then with probability $\epsilon$ accept that solution either way

### Global optimum
Keep track of global optimum to provide best solution found overall in the end.

---

# Disclaimer
I shared some ideas at the start of the lab with
- Davide Carletto s339425
- Michele Carena s349483