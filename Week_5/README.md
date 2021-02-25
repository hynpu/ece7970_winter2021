# SGD optimization: Stochastic gradient descent
One of the fundamental requirements for SGD optimization is that the training data is independent and identically distributed, but in RL:
1. samples are not independent
2. training data distribution won't be identical

To deal with this problem, **replay buffer** which stores past experience will be the sampling pool.

# Epsilon-greedy method

# "Convert" POMDP to MDP
The solution is maintaining several observations from the past and using them as a state. In the case of Atari games, we usually stack k subsequent frames together and use them as the observation at every state. 

For instance, we keep the past k steps of previous states, and use these states to infer the current dynamic.

# super() useage in class def
``` 
class FireResetEnv(gym.Wrapper):
    def __init__(self, env=None):
        """For environments where the user need to press FIRE for the game to start."""
        super(FireResetEnv, self).__init__(env)
        assert env.unwrapped.get_action_meanings()[1] == 'FIRE'
        assert len(env.unwrapped.get_action_meanings()) >= 3
```  
A very helpful link: https://realpython.com/python-super/
```
class Cube(Square):
    def surface_area(self):
        face_area = super(Square, self).area()
        return face_area * 6

    def volume(self):
        face_area = super(Square, self).area()
        return face_area * self.length
```
> In this example, you are setting Square as the subclass argument to super(), instead of Cube. This causes super() to start searching for a matching method (in this case, .area()) at one level above Square in the instance hierarchy, in this case Rectangle.

# Other 
Some tricks to fasten the learning rate: such as converting individual lives in the game into separate episodes, performing a random amount of no-op actions in the beginning of the game, making an action decision every K steps (repeating an action for 3-4 time until take the next new action), scaling down the frame, reconstruct the reward in the game...

``` 
self.action_space = spaces.Box( np.array([-1,0,0]), np.array([+1,+1,+1]))  # steer, gas, brake
``` 

Box means that you are dealing with real valued quantities.

The first array np.array([-1,0,0] are the lowest accepted values, and the second np.array([+1,+1,+1]) are the highest accepted values. In this case (using the comment) we see that we have 3 available actions:

Steering: Real valued in [-1, 1]
Gas: Real valued in [0, 1]
Brake: Real valued in [0, 1]
