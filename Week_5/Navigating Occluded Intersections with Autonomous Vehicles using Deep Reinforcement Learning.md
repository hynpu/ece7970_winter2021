# Citation
Isele, David, et al. "Navigating occluded intersections with autonomous vehicles using deep reinforcement learning." 2018 IEEE International Conference on Robotics and Automation (ICRA). IEEE, 2018.

# Abstract
In this paper, the auther mainly described the popular methods used for occuded intersection navigation: 

* Cooperative approaches: requires V2V communication
* Heuristic approaches, and the current state of the art is rule based method based on TTC

The constrains of using TTC: 

1. the TTC models assume constant velocity, which ignores nearly all information concerning driver intent
2. overly cautious, creating unnecessary delays
3. assume full knowledge of their surroundings, requires an engineer to identify and manage a large possible number of scenarios

Several machine learning approaches:

1. imitation learning: the policy is learned from a driver, but behave poor in new envionment
2. online planners: MCP (monte carlo planning
3. offline learning: MDP

Three strategy to take actions:
1. time to go: only 2 actions, which are stop and go. Once go is executed, do not allow to stop agian;
2. sequential actions: given a provided trajectory, accelerate, decelerate, or maintian const speed.
3. creep and go: 3 actions, wait, move forward slowly, and go. It is a compromised strategy between 1 adn 2.

# Spotlight
* Cons of imitation learning: if the agent finds itself in a state that is not part of the training data.
* UGV has a wide variety of state and action representations, and the selection of the representation had a significant impact on the agent’s ability to learn

A very conclusive way to explain DQN:

In Deep Q-learning [15], the optimal value function is approximated with a neural network Q^\*(s; a) Q(s; a; \theta) with parameters \theta. The action value function is learned by iteratively minimizing the error between the expected return and the state-action value predicted by the network

![equ_1](https://github.com/hynpu/ece7970_winter2021/blob/main/Week_5/Figures/equ.JPG)

# What to learn
Monte Carlo Planning:

The focus of MCTS is on the analysis of the most promising moves, expanding the search tree based on random sampling of the search space.

Bouton, Maxime, Akansel Cosgun, and Mykel J. Kochenderfer. "Belief state planning for autonomously navigating urban intersections." 2017 IEEE Intelligent Vehicles Symposium (IV). IEEE, 2017.

https://en.wikipedia.org/wiki/Monte_Carlo_method
