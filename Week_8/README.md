# The advantage of state-action pair

The advantage A(s, a) is supposed to bridge the gap from A(s) to Q(s, a), as, by definition, Q(s, a) = V(s) + A(s, a). In other words, the advantage A(s, a) is just the delta, saying how much extra reward some particular action from the state brings us.

# The entropy bonus function

In information theory, entropy is a measure of uncertainty in some system. Entropy becomes minimal when our policy has 1 for some action and 0 for all others, which means that the agent is absolutely sure what to do. To prevent our agent from being stuck in the local minimum, we subtract the entropy from the loss function, punishing the agent for being too certain about the action to take.

This function has a minimum when the probability distribution is uniform, so by adding it to the loss function, we push our agent away from being too certain about its actions.

# A2C: the (advantage) Actor-Critic Method

The policy network returns a probability distribution of actions, it is called the actor and tell the system what to implement;

The value network return the as it allows us the value telling us how good our actions were.

![](https://github.com/hynpu/ece7970_winter2021/blob/main/Week_8/Figures/a2c.JPG)
