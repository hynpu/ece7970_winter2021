# Abstract
How to locate an target, from receiving a sound at the beginning, and then accociate the sound with the image, and finally find it?  

In paper, the author proposed a [transformer-based model](https://en.wikipedia.org/wiki/Transformer_(machine_learning_model)) learning the association between how objects look and how they sound to solve this problem. A goal descriptor captures both spatial and semantic properties of the target, and the persistent multimodal memory to reach the goal even when the sound (acoustic event) stops. Then the policy network generate the action based on the output from observation encoderr and goal descriptor.

1. Observation encoder: each time step t, the observation_t has visual, audio, agent pose, action_prev; the CNN encodes the visual and audioi observations, and save the previous t steps observation to the memory M.
2. Goal descriptor network: use another CNN model to predict the L_t (location) and C_t (category) by using the audio information.
3. Policy network: here is the RL policy network. An encoder to accociate the information from the memory M, to see if there is any relation between these inputs: M_e. Then, a decoder network use the M_e, C_t, and L_t input to update the state repensentation s_t for each cell. Then the actor-critic network use the s_t to predict the action distribution and value of the state.


![illustration](https://github.com/hynpu/ece7970_winter2021/blob/main/Week_4/Capture.JPG)

# Spotlight
1. How to train the goal descriptor network: generate ground truth first, including location and category from simulation, and train the network. The category prediction is is supervised and off-policy, and the location prediction is on-policy.
2. To avoid sampling easy episodes, add requirements to the geodesic distance. **But how is geodesic distance used in this research?**

# What to learn
1. encoder *(https://d2l.ai/chapter_recurrent-modern/encoder-decoder.html)
2. actor-critic network
