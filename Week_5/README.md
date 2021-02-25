# SGD optimization: Stochastic gradient descent
one of the fundamental requirements for SGD optimization is that the training data is independent and identically distributed, but in RL:
1. samples are not independent
2. training data distribution won't be identical

To deal with this problem, **replay buffer** which stores past experience will be the sampling pool.

# Epsilon-greedy method

