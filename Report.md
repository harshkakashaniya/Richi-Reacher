## Report on impelementation of DDPG Reinforcement algorithm for Reacher problem.

Details of environment :
```
Observation space type: continuous
Number of agents : 20
Observation space size (per agent): 33
Action space size (per agent): 4
```

### State Space :

The observation space consists of 33 variables corresponding to position, rotation, velocity, and angular velocities of the arm. 

### Action Space :

Each action is a vector with four numbers, corresponding to torque applicable to two joints.
Every entry in the action vector should be a number between -1 and 1.


### Reward :

In this environment, a double-jointed arm can move to target locations.
A reward of +0.1 is provided for each step that the agent's hand is in the goal location.
Thus, the goal of your agent is to maintain its position at the target location for as many time steps as possible.

## Solving criterias of the problem. 

### Option 1: Solve the First Version
The task is episodic, and in order to solve the environment, your agent must get an average score of +30 over 100 consecutive episodes.

### Option 2: Solve the Second Version
The barrier for solving the second version of the environment is slightly different, to take into account the presence of many agents. In particular, your agents must get an average score of +30 (over 100 consecutive episodes, and over all agents). Specifically,

After each episode, we add up the rewards that each agent received (without discounting), to get a score for each agent. This yields 20 (potentially different) scores. We then take the average of these 20 scores.
This yields an average score for each episode (where the average is over all 20 agents).


### Neural Network details :
![](https://github.com/harshkakashaniya/Richi-Reacher/blob/main/images/Neural_netowork_20.png)

### Agent details :
```
BATCH_SIZE = 128        # minibatch size
BUFFER_SIZE = int(1e5)  # replay buffer size
GAMMA = 0.99            # discount factor
LR_ACTOR = 1e-4         # learning rate of the actor 
LR_CRITIC = 1e-4        # learning rate of the critic
TAU = 1e-3              # for soft update of target parameters
WEIGHT_DECAY = 0        # L2 weight decay

```

1. We have class of Ring buffer with deque of tuple [State , Action , Reward , Next state , Done ]
2. Optimizer used for back propagation is Adams.
3. We are using Relu after every fully connveted layer.
4. We are adding actions in the critic network with the second hidden layer.
5. Two networks are maintained for each Actor and Critic in order to have a smooth learnings.
6. We use Tau parameter to update the network slowly so that we so not overshoot in gradient descent and function learned by the neural network is better.

### DDPG algorithm.
```
number of episodes=1000, 
Maximum time step per episode =1000,
```

## Final Results :

### Results with 20 agents training in centralized learning fashion.

![](https://github.com/harshkakashaniya/Richi-Reacher/blob/main/images/20_agents.png)

**We solved the game with +30 score on an average of 100 episodes in 106 episodes.**


### Ideas to improve on the results.
1.We can try reducing the network height and depth to check if we can solve the problem with less weight hence less data.

2. If we do not have constraint of computation I will also like to try genetic algorithm and see if we can get better results I doubt it will be the case but it is a good idea to try and understand the results.

3. PPO can be tried on this problem and compaired with A2C.

4. This can be a good problem to impelement with standard impelementations for RL algorithms showed in the lectures.
