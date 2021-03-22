# Nouns
policy derivation: deriving policies from demonstration data

Mapping function: demonstration data is used to directly approximate the underlying function mapping from the robot’s state observations to actions

# Citation

Argall, B. D., Chernova, S., Veloso, M., & Browning, B. (2009). A survey of robot learning from demonstration. Robotics and Autonomous Systems, 57(5), 469–483. https://doi.org/10.1016/j.robot.2008.10.024

# Abstract

Design choices:

1. Demonstration approach: 

1.1 The choice of demonstrator: who controls the demonstration, who executes the demonstration

1.2 Demonstration technique: batch learning (pretty much like "off-line training"), and interactive approaches ("on-line training")

___________

2. Problem space continuity: the continuity of the problem space

Discrete or continuous? Also, there are THREE control levels, low level motion control, action primitives, and complex behavioral action, and the contiuity among these three levels can be different

___________

3. Policy derivation: how to get the policy mapping \pi from the given demonstration data set

Mapping function, demonstration data is used to directly approximate the underlying function mappingfrom the robot’s state observations to actions;

System model, demonstration data is used to determine a model of the world dynamics, and combine with a reward function to choose proper policy

Plan: not sure how to implement this method

___________

4. Gathering examples: how to build the dataset?

4.1 correspondence: teleoperation, shadowing, sensors on the teacher, or external observation

Record mapping: from the teacher execution to recorded execution, which means if/how the teacher demonstration can be recorded 

Embodiment mapping: from the recorded execution to the learner (robot), which means if/how to convert the dataset to robot knowledge (policy mapping)

Both can be categorized by fully/partially observable

5. Limitation of demonstration 

How should the robot act when the current state is not associated with a demonstration: 1. generalization from existing demonstrations; 2. ask for teacher's help

How should the robot do when the dataset is very poorly constructed: 1. eliminate the subpotimal dataset; 2. learn from the teacher's evaluation/feedback

# Spotlight


# What to learn

1. Find more papers related to combining RL with LfD

2. Do I need to care about building the entire robot? including the low level (actuation level)? Or is there any existing models already build?

3. Talk with Dr. Louie to get familiar with the robot in teh lab
