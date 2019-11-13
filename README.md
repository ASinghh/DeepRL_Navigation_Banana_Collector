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

### Algorithm 
The project includes implementation of Q-Learning and Double Q-Learning with Vanilla and Dueling network architectures.

#### Q-Learning
Q-learning is a model-free reinforcement learning algorithm. The goal of Q-learning is to learn a policy, which tells an agent what action to take under what circumstances. It does not require a model (hence the connotation "model-free") of the environment, and it can handle problems with stochastic transitions and rewards, without requiring adaptations. The weight for a step from a state Δ t {\displaystyle \Delta t} \Delta t steps into the future is calculated as γ Δ t {\displaystyle \gamma ^{\Delta t}} \gamma ^{{\Delta t}}, where γ {\displaystyle \gamma } \gamma (the discount factor) is a number between 0 and 1 ( 0 ≤ γ ≤ 1 {\displaystyle 0\leq \gamma \leq 1} 0\leq \gamma \leq 1) and has the effect of valuing rewards received earlier higher than those received later (reflecting the value of a "good start"). γ {\displaystyle \gamma } \gamma may also be interpreted as the probability to succeed (or survive) at every step Δ t {\displaystyle \Delta t} \Delta t.

The algorithm, therefore, has a function that calculates the quality of a state-action combination: <br/>
    Q:S\times A\to {\mathbb {R}} .

Before learning begins, Q {\displaystyle Q} Q is initialized to a possibly arbitrary fixed value (chosen by the programmer). Then, at each time t {\displaystyle t} t the agent selects an action a t {\displaystyle a_{t}} a_{t}, observes a reward r t {\displaystyle r_{t}} r_{t}, enters a new state s t + 1 {\displaystyle s_{t+1}} s_{t+1} (that may depend on both the previous state s t {\displaystyle s_{t}} s_{t} and the selected action), and Q {\displaystyle Q} Q is updated. The core of the algorithm is a simple value iteration update, using the weighted average of the old value and the new information: 

