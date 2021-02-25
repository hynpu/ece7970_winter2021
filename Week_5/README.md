# SGD optimization: Stochastic gradient descent
One of the fundamental requirements for SGD optimization is that the training data is independent and identically distributed, but in RL:
1. samples are not independent
2. training data distribution won't be identical

To deal with this problem, **replay buffer** which stores past experience will be the sampling pool.

# Epsilon-greedy method

# "Convert" POMDP to MDP
The solution is maintaining several observations from the past and using them as a state. In the case of Atari games, we usually stack k subsequent frames together and use them as the observation at every state. 

For instance, we keep the past k steps of previous states, and use these states to infer the current dynamic.

# Other 
Some tricks to fasten the learning rate: such as converting individual lives in the game into separate episodes, performing a random amount of no-op actions in the beginning of the game, making an action decision every K steps (repeating an action for 3-4 time until take the next new action), scaling down the frame, reconstruct the reward in the game...
