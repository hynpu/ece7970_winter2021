
# Citation
Chen, Y. F., Everett, M., Liu, M., & How, J. P. (2017). Socially aware motion planning with deep reinforcement learning. IEEE International Conference on Intelligent Robots and Systems, 2017-Septe, 1343–1350. https://doi.org/10.1109/IROS.2017.8202312


# Abstract
Social navigation can be classified as model-based and learning-based. This paper introduced several popular model based methods, including their pros and cons. For learning based, it specifically mentioned that using Inverse RL to learn from human demonstration.
Then it detailed introduced the states including observable and unobservable, robot itself and its surrounding agents. Then, a value function is defined in continues time (why continues rather than discontinuous?)
Also, compared with giving the comprehensive definition of social norms, it will be easier to define what is not acceptable in social interaction. For this research problem, it will be a union of passing/overtaking/crossing uncomfortable zones.
Also, details about training multiagent value network are also given: feed the robot & nearby agents' states to a neural network (rectified linear unit (ReLU)) , which will generate value funciton (need to confirm with Dr. Louie), and then the value fucntion will be compenstated with penalty rewards (unacceptable social norms, or say, uncomfortable zone).

# Spotlight
Details about how to incorporate neural network with RL.

# What to learn
+ ReLU

+ Pooling layer

+ How to generate the value function? Because the inputs are states (position, velocity and other values), how to convert these states to a value function? How to tune the coefficients? Using ReLU? If so, which means the value function is computed/estimated from the neural network, and the RL will be used for path planning only ( to select a trajectory with best value in the next N horizons).
