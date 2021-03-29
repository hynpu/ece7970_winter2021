# Citation
Louie, W. Y. G., & Nejat, G. (2020). A Social Robot Learning to Facilitate an Assistive Group-Based Activity from Non-expert Caregivers. International Journal of Social Robotics, 12(5), 1159–1176. https://doi.org/10.1007/s12369-020-00621-4

# Abstract
This paper is closely related to the research in the lab. The author developed a task-level learning LfD robot achieved by learning state-action policies by mapping world states to primitive robot actions.

The robot has two sub-modules: Demonstration Sub‑system and Interaction Sub‑system. And the interaction sub-system is used to create the current world state array using user/env/robot sensor, and also IMPLEMENT the LfD activity behavior on the robot.

World state: all the states (e.g. robot state, object state, person state) relevant to a given task

Robot behivor: a set of actions to provide a certain functionality (my understanding), behaviors of the robot modify the world state, and human demonstrated behaviors are often determin- istic with one behavior always being executed in the specific state. A robot behavior could be “Greeting a User” and the behavior policy specifies that the robot should wave its right arm and say “Hi” for this behavior.

Activity learning: activity learning module learns the world state to robot behavior mapping for an activity using the demonstrated trajectory

Activity Trajectory: it is pairs from world state -> robot behavior during a teacher’s demonstration of the activity.

Activity (what is activity itself): activity, A, is defined by the multiple distinct states that it can be in: A = {a1, a2,…,ao}, and each activity state is the combination of user state, robot state, and time step.

# Spotlight


# What to learn 
What is a "self-collision", is this a Gimbal lock?

Forest classifier

Random forests or random decision forests are an ensemble learning method for classification, regression and other tasks that operate by constructing a multitude of decision trees at training time and outputting the class that is the mode of the classes (classification) or mean/average prediction (regression) of the individual trees.[1][2] 

Random decision forests *correct for decision trees' habit of overfitting to their training set*.[3]:587–588 Random forests generally outperform decision trees, but their accuracy is lower than gradient boosted trees. However, data characteristics can affect their performance.[4][5]
[Random forest](https://en.wikipedia.org/wiki/Random_forest)