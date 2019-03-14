# Report
---
This project is implemented based on [deep-reinforcement-learning/p2_continuous-control](https://github.com/udacity/deep-reinforcement-learning/tree/master/p2_continuous-control).


## Algorithm

The models are training `ddpg` function in the `Continuous_Control` notebook.
- `first score and its window`
- `initialize the agents`
- `loop over the agents`
- `training the models episodically with limited num of episodes`
- `The training process will stop when score is reached +30`
- `reset the agent in every episode`
- `save the scores in every episode`


The DDPG agent is implemented in `ddpg_agent.py`

### DDPG Hyper Parameters
- `n_episodes=300 or 18000`: maximum number of training episodes,300 for `Reacher` agents and 18000 for `Crawler` agents
- `max_t=1000`: maximum number of timesteps per episode
- `num_agents`: number of agents

### DDPG Agent Hyper Parameters

- `BUFFER_SIZE = int(1e6)`: replay buffer size
- `BATCH_SIZE = 128`: mini batch size
- `GAMMA = 0.99`: discount factor
- `TAU = 1e-3`: for soft update of target parameters
- `LR_ACTOR = 1e-4`: learning rate for optimizer
- `LR_CRITIC = 1e-4`: learning rate for optimizer
- `WEIGHT_DECAY = 0.0`: L2 weight decay
- `N_LEARN_UPDATES = 10`: number of learning updates
- `N_TIME_STEPS = 20`: every n time step do update


### Neural Networks

Actor and Critic network models were defined in `model.py`

The Actor network and critic network setted have three layers.
The first layer is input layer with size as input size.
The second and last layer has 512 and 256 neruals.

## Plot of rewards
![Reward Plot](https://github.com/hortovanyi/DRLND-Continuous-Control/blob/master/output/result.png?raw=true)

```

```

## Ideas for Future Work

Proximal Policy Optimization (PPO) and Distributed Distributional Deterministic Policy Gradients (D4PG) methods could leverage in the future work on this project.

In addition, the neural networks in current model are rather relatively shallow; therefore, we can make it a little more deep.

Lastly, due to the computational resource, the crawler was only trained with score +15. The performance of the controller of the crawler agent probably can been improved if given more time and resources to train.  