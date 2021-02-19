
# Citation:
Chen, C., Liu, Y., Kreiss, S., & Alahi, A. (2019). Crowd-robot interaction: Crowd-aware robot navigation with attention-based deep reinforcement learning. Proceedings - IEEE International Conference on Robotics and Automation, 2019-May, 6015–6022. https://doi.org/10.1109/ICRA.2019.8794134

# Abstract
Proposed a method to 
1. Forecast future trajectories of all the humans to avoid collisions;

2. The robot not only needs to understand the behavior of humans but also interact with them to obtain high rewards. (penalty is set as the duration when robot-human distance < threshold)

To achieve this, the author extracts features for pair- wise interactions between the robot and each human and captures the interactions among humans via local maps. Then, aggregate the interaction features to infer the relative importance of neighboring humans with respect to their future states.

# Spotlight
1. The number of people around the robot is variant, so feed the states of all humans into an LSTM sequentially with respect to their distance; (M. Everett, Y. F. Chen, and J. P. How, “Motion Planning Among Dy- namic, Decision-Making Agents with Deep Reinforcement Learning,” arXiv:1805.01956 [cs], May 2018, arXiv: 1805.01956.)
2. How to decide the influnce of a nearby human? Not only distance, but also speed and direction: social attention pooling module
3. Use a L*L*3 map tensor to encode the presence and vel of neighbors (why *3?)

# What to learn
1. The RL part is fine, but how to integrate the DL with RL? Need to learn basic concepts of DL, how pooling layer works, and related knowledge.
