# Reinforcement Learning

### Introduction

In this project I implemented 3 reinforcement learning algorithms on a Markov Decision Process (MDP). 

Reinforcement Learning Algorithms:
- Value Iteration
- Policy Iteration
- Q-Learning

The MDP I designed is an 11 by 11 gridworld maze with many spaces used as walls blocking the agent's path from the south-west corner (starting point) to the north-east corner (goal).

The full report is available here: [Report](/Analysis.pdf)

#### The Gridworld

![Maze Gridworld](./Images/Maze%20Gridworld.png)

In the image, the gray circle represents the agent’s start position, the black squares represent the walls of the maze, and the blue square represents the terminal/reward state.

This MDP is interesting because it forces an agent to solve a problem that might not be trivial for a person. This is not a challenging maze, but it still takes a couple of seconds to find the answer by sight. A larger maze could be much more complicated. We could generalize the results in this example to see how different algorithms perform against non-trivial problems. 

Transitions in the gridworld are defined probabilistically. If an agent intends to move in a given direction, there is an 80% chance that movement is made in that direction and a 20% chance that movement is made (or attempted, in the presence of a wall) in one of the 3 other cardinal directions.

#### Value Iteration

![Maze Gridworld Value Iteration](./Images/Maze%20Gridworld%20Value%20Iteration.png)

The maze gridworld takes 25 steps to converge with value iteration. The reward value at convergence is 77. The amount of time necessary to converge varies between 96 and 225 milliseconds.

#### Policy Iteration

![Maze Gridworld Policy Iteration](./Images/Maze%20Gridworld%20Policy%20Iteration.png)

The maze gridworld takes 27 steps to converge with policy iteration. The reward value at convergence is 75. The amount of time necessary to converge varies between 68 and 163 milliseconds.

#### Q Learning

![Maze Gridworld Q Learning](./Images/Maze%20Gridworld%20Q%20Learning.png)

The maze gridworld takes 33 steps to converge with Q learning. The reward value at convergence is 69. The amount of time necessary to converge varies between 107 and 118 milliseconds.

#### Summary

Value iteration finds a policy that allows it to converge in 25 steps with a reward of 77. Policy iteration finds a policy that allows it to converge in 27 steps with a reward of 75. The policy iteration algorithm works more quickly. Q learning performed worse than either the value iteration or policy iteration planning algorithms. It took a similar amount of time, but converged to a policy that takes 33 steps to converge with a reward value of 69.

The large number of states caused the algorithms to converge to different results, take longer to complete, and have more variability each run.

The MDP is small enough to map out the optimal policy by hand. We can see that the value iteration and policy iteration planning algorithms provide similar paths, which appears to be the shortest path through the maze. The Q learning algorithm fails to provide a reasonable path that an agent could follow.  