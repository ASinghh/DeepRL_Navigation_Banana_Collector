# DeepRL_Navigation_Banana_Collector
## Introduction
The project is the first one of the three projects required for graduating [Udacity's Deep Reinforcement Learning Nano Degree](https://www.udacity.com/course/deep-reinforcement-learning-nanodegree--nd893). The project is to train an agent based on popular variants of Q learning to solve the Unity ML Banana Collector environment. The base code for implementation is borrowed from [Udacity's implementation of Deep Q Networks](https://github.com/udacity/deep-reinforcement-learning/blob/master/dqn/exercise/Deep_Q_Network.ipynb), which I have modified to add Double Q and Dueling Networks. 


## Project details
### Environment 
The environment under consideration is on of the many [Unity ML-Agents Toolkit's](https://github.com/Unity-Technologies/ml-agents) game environments. These environments enable games and simulations to serve as environments for training intelligent agents. The environment is called the Banana Collector. It is game where a player is supposed to navigate in order to collect yellow bananas and skip blue bananas. A graphic rendering of the environment looks like the following GIF. <br/> <br/> <br/> ![banana collector](Images_GIFs/banana_collector.gif)

#### State Space
The state space has 37 dimensions and contains the agent's velocity, along with ray-based perception of objects around the agent's forward direction. Given this information, the agent has to learn how to best select actions.

#### Action Space
Four discrete actions are available, corresponding to:
```   
       0 - move forward.
       1 - move backward.
       2 - turn left.
       3 - turn right.
```
#### Rewards
A reward of +1 is provided for collecting a yellow banana, and a reward of -1 is provided for collecting a blue banana.

### Completion Criteria
Based on the instructions provided in the study material, in order to consider the environment solved, the agent must get an average score of +13 over 100 consecutive episodes.

