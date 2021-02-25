
# Citation
Chen, Y. F., Liu, M., Everett, M., & How, J. P. (2017). Decentralized non-communicating multiagent collision avoidance with deep reinforcement learning. Proceedings - IEEE International Conference on Robotics and Automation, 285–292. https://doi.org/10.1109/ICRA.2017.7989037

# Abstract
A reliable communication network for broadcasts between agents is not reliable, how to achieve collision free navigation?

The author proposed a Deep RL method to generate path by repeatedly maximizing an one-step lookahead values. 

Firstly, the value function is parametrized by a deep neural network with ReLU layer.

Then, the RL agent can generate a path to its goal by repeatedly maximizing an one-step lookahead value function.

Then, to train the network, the value network is initialized by a supervised training on a generated trajectory set. 

After initialization, the RL algo will refine the policy (value network).

# Spotlight
Value iteration rather than Q iteration: because unlike previous works that focus on discrete, finite action spaces [20], [21], the action space here is continuous and the set of permissible velocity vectors depends on the agent’s state (preferred speed).

# What to learn
freezing robot problem: P. Trautman and A. Krause, “Unfreezing the robot: Navigation in dense, interacting crowds,” in 2010 IEEE/RSJ International Conference on Intelligent Robots and Systems (IROS), Oct. 2010, pp. 797–803.

The use of a filtered velocity addresses a subtle oscillation problem as discussed in [12]: J. Van den Berg, M. Lin, and D. Manocha, “Reciprocal velocity obstacles for real-time multi-agent navigation,” in Proceedings of the 2008 IEEE International Conference on Robotics and Automation (ICRA),

Experience set in RL: it seems that the experience set is the state-value pair set.

![algo illustration](https://github.com/hynpu/ece7970_winter2021/blob/main/Week_5/Figures/init_refine_algo.JPG)

epsilion-greedy method: which just means switching between random and Q policy using the probability hyperparameter \eps
