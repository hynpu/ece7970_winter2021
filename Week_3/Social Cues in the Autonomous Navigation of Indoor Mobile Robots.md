
# Citation
Reddy, A. K., Malviya, V., & Kala, R. (2020). Social Cues in the Autonomous Navigation of Indoor Mobile Robots. International Journal of Social Robotics, (October). https://doi.org/10.1007/s12369-020-00721-1


# Abstract
This paper introduces several methods to plan a trajectory following social cues in crowds. What he proposed is a model called social force model, and also incorporates the social cues by adding new social forces.
Social cues mean passing on the left/right.

	1. Geometry-Based Approaches: simply find the path to follow the gap, such as VFH method, which calculates the obstable density, and choose the least densed area to pass. A* or other graph theory search algo can be used;
	2. Potential based approaches: imagine that there are virtual forces from each object (attractive or repulsive)

# Spotlight
	1. Definition of virtual force field
	2. Orthogonal force is the main force to help robot avoid collision, which is perpendicular to the line of robot-human;
	3. Compute the gap, and find the mean of the gap (kind of like the center of the gap);
	4. Find the best route: prioritize the goal (which has the most attractive force), and use the "sub-goal" for the current stage, which is selected considering the angle of the goal as well as the angle of gaps' mean

# What to learn
NA
