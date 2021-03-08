# logit function

Policy distribution could be either logits (unnormalized) or a normalized distribution. In practice, you should always use logits to improve the numeric stability of the training process.

# The DNQ looks like an infinite repetition of this:

1. Call buffer.populate(1) to get a fresh sample from the environment 
2. batch = buffer.sample(BATCH_SIZE) to get the batch from the buffer 
3. Calculate the loss on the sampled batch 
4. Backpropagate 
5. Repeat until convergence (hopefully)

# Ornstein–Uhlenbeck process

# pytorch.gather

torch.gather creates a new tensor from the input tensor by taking the values from each row along the input dimension dim. The values in torch.LongTensor, passed as index, specify which value to take from each 'row'. The dimension of the output tensor is same as the dimension of index tensor. Following illustration from the official docs explains it more clearly:

```
q_v = q_v.gather(1, actions_v.unsqueeze(-1)).squeeze(-1)
```

(gather figure)[]

In the preceding line, we pass observations to the first model and extract the specific Q-values for the taken actions using the gather() tensor operation. The first argument to the gather() call is a dimension index that we want to perform gathering on (in our case, it is equal to 1, which corresponds to actions).

The second argument is a tensor of indices of elements to be chosen. Extra unsqueeze() and squeeze() calls are required to compute the index argument for the gather functions, and to get rid of the extra dimensions that we created, respectively. (The index should have the same number of dimensions as the data we are processing.) In Figure 6.3, you can see an illustration of what gather() does on the example case, with a batch of six entries and four actions:

Keep in mind that the result of gather() applied to tensors is a differentiable operation that will keep all gradients with respect to the final loss value.

# N step DQN

Pros: speed up the process speed, because the correct value could be passed back to (up to) N steps ahead of the current state

But, for example, at the beginning of the training, when our agent acted randomly? In that case, our calculated value for Q_st_at may be smaller than the optimal value of the state; the more steps on which we unroll the Bellman equation, the more incorrect our update could be.

# The simple DQN is off-policy (different with SARSA)

The reason that Q-learning is off-policy is that it updates its Q-values using the Q-value of the next state s′ and the greedy action a′. In other words, it estimates the return (total discounted future reward) for state-action pairs assuming a greedy policy were followed despite the fact that it's not following a greedy policy. Even if action a_t was sampled randomly, it doesn't matter because for this particular action a_t in the state s_t, our update will be correct. That's why in off-policy methods, we can use a very large experience buffer to make our data closer to being independent and identically distributed (i.i.d)

On the other hand, on-policy methods heavily depend on the training data to be sampled according to the current policy that we are updating. That happens because on-policy methods are trying to improve the current policy indirectly (as in the previous n-step DQN) or directly (all of part three of the book is devoted to such methods). The reason that SARSA is on-policy is that it updates its Q-values using the Q-value of the next state s′ and the current policy's action a′′. It estimates the return for state-action pairs assuming the current policy continues to be followed.

The distinction disappears if the current policy is a greedy policy. However, such an agent would not be good since it never explores.


# Relation between off policy and on policy, offline and online

This is a very good explanation 
[What is the relation between online (or offline) learning and on-policy (or off-policy) algorithms?](https://ai.stackexchange.com/questions/10474/what-is-the-relation-between-online-or-offline-learning-and-on-policy-or-off)

[Off-policy vs On-Policy vs Offline Reinforcement Learning Demystified!](https://kowshikchilamkurthy.medium.com/off-policy-vs-on-policy-vs-offline-reinforcement-learning-demystified-f7f87e275b48)

## Online vs Offline
These concepts are not specific to RL, many learning systems can be categorised as online or offline (or somewhere in-between).

Online learning algorithms work with data as it is made available. Strictly online algorithms improve incrementally from each piece of new data as it arrives, then discard that data and do not use it again. It is not a requirement, but it is commonly desirable for an online algorithm to forget older examples over time, so that it can adapt to non-stationary populations. Stochastic gradient descent with back-propagation - as used in neural networks - is an example.

Offline learning algorithms work with data in bulk, from a dataset. Strictly offline learning algorithms need to be re-run from scratch in order to learn from changed data. Support vector machines and random forests are strictly offline algorithms (although researchers have constructed online variants of them).

Of the two types, online algorithms are more general in that you can easily construct an offline algorithm from a strictly online one plus a stored dataset, but the opposite is not true for a strictly offline algorithm. However, this does not necessarily make them superior - often compromises are made in terms of sample efficiency, CPU cost or accuracy when using an online algorithm. Approaches such as mini-batches in neural network training can be viewed as attempts to find a middle ground between online and offline algorithms.

Experience replay, a common RL technique, used in Deep Q Networks amongst others, is another in-between approach. Although you could store all the experience necessary to fully train an agent in theory, typically you store a rolling history and sample from it. It's possible to argue semantics about this, but I view the approach as being a kind of "buffered online", as it requires low-level components that can work online (e.g. neural networks for DQN).

## On-policy vs Off-Policy
These are more specific to control systems and RL. Despite the similarities in name between these concepts and online/offline, they refer to a different part of the problem.

On-policy algorithms work with a single policy, often symbolised as π, and require any observations (state, action, reward, next state) to have been generated using that policy.

Off-policy algorithms work with two policies (sometimes effectively more, though never more than two per step). These are a policy being learned, called the target policy (usually shown as π), and the policy being followed that generates the observations, called the behaviour policy (called various things in the literature - μ, β, Sutton and Barto call it b in the latest edition).

A very common scenario for off-policy learning is to learn about best guess at optimal policy from an exploring policy, but that is not the definition of off-policy.
The primary difference between observations generated by b and the target policy π is which actions are selected on each time step. There is also a secondary difference which can be important: The population distribution of both states and actions in the observations can be different between b and π - this can have an impact for function approximation, as cost functions (for e.g. NNs) are usually optimised over a population of data.
In both cases, there is no requirement for the observations to be processed strictly online or offline.

In contrast to the relationship between online and offline learning, off-policy is always a strict generalisation of on-policy. You can make any off-policy algorithm into an equivalent on-policy one by setting π=b. There is a sense in which you can do this by degrees, by making b closer to π (for instance, reducing ϵ in an ϵ-greedy behaviour policy for b where π is the fully greedy policy). This can be desirable, as off-policy agents do still need to observe states and actions that occur under the target policy - if that happens rarely because of differences between b and π, then learning about the target policy will happen slowly.


# Noisy Networks
By adding noise to the fully connected layer, so that the action can be either exploration or exploite.