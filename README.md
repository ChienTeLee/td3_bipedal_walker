# Twin-Delayed DDPG (TD3) with Bipedal Walker

## Overview
The objective of this project is to implement Twin-Delayed DDPG (TD3) algorithm for BipedalWalker environment in OpenAi Gym. Twin-Delayed DDPG is an actor-critic framework which achieves state of the art performance for continuous control. While applying two critic networks, TD3 is able to select the smaller of the two predictions as the target q-value, and thus recude the over-estimation of the q-function. Next, TD3 delays the update of actor network to prevent policy function from varying too frequently. TD3 adds gaussian noise in action selection for action exploration during training, and the noise is clipped within boundaries. We also applies tricks such as target networks, huber loss, and soft update for stabilizing the training process.

The BipedalWalker-v3 is a continuous control environment using Box2D. It tests if the agent can successfully drive the Bipedal Walker to walk to the end of the terrain without falling down. The environment is solved when the agent recieves +300 reward within 1600 time step.

(This project is implemented in python 3 and tensorflow 2 and is only for self-practice purpose.)

## Dependencies
1. python 3.6.9
2. tensorflow 2.2.0
3. OpenAI Gym 0.17.2 
4. box2d-py

## How to run
1. Run TD3_BipedalWalker.ipynb
2. After running, the video of trained result will show up in "after_train" folder

## Paper
The implementation is related to the following papers:

1. [Continuous control with deep reinforcement learning](https://arxiv.org/abs/1509.02971)

2. [Addressing Function Approximation Error in Actor-Critic Methods](https://arxiv.org/abs/1802.09477)

## OpenAI Gym environment
OpenAI Gym environment: [BipedalWalker-v3](https://gym.openai.com/envs/BipedalWalker-v2/)
<p align="center">
  <img src="https://github.com/ChienTeLee/td3_bipedal_walker/raw/master/doc/figure0.png" width="50%" height="50%"> 
</p>

## Implementation
1. The Twin-Delayed DDPG is implemented using the following network architecture:
<p align="center">
  <img src="https://github.com/ChienTeLee/td3_bipedal_walker/raw/master/doc/figure2.png" width="60%" height="60%"> 
</p>

2. The network training algorithm is based on the pseudocode:
<p align="center">
  <img src="https://github.com/ChienTeLee/td3_bipedal_walker/raw/master/doc/figure3.png" width="80%" height="80%"> 
</p>

3. The data flow is shown in the following diagram:
 <p align="center">
  <img src="https://github.com/ChienTeLee/td3_bipedal_walker/raw/master/doc/figure4.png" width="80%" height="80%"> 
</p>

## Result
1. The Twin-Delayed DDPG agent after training:
<p align="center">
  <img src="https://github.com/ChienTeLee/td3_bipedal_walker/raw/master/doc/after_train.gif" width="60%" height="60%"> 
</p>

2. Training process:
<p align="center">
  <img src="https://github.com/ChienTeLee/td3_bipedal_walker/raw/master/doc/figure5.png" width="60%" height="55%"> 
</p>

## Slides
[TD3_slides](https://github.com/ChienTeLee/td3_bipedal_walker/blob/master/TD3_slides.pdf)

## Reference
This project is inspired by the following blogs:

1. [Deep Deterministic Policy Gradient](https://spinningup.openai.com/en/latest/algorithms/ddpg.html)

2. [Deep Reinforcement Learning. Deep Deterministic Policy Gradient (DDPG) algorithm](https://medium.com/@markus.x.buchholz/deep-reinforcement-learning-deep-deterministic-policy-gradient-ddpg-algoritm-5a823da91b43)

3. [Deep Deterministic Policy Gradient (DDPG)](https://morvanzhou.github.io/tutorials/machine-learning/reinforcement-learning/6-2-DDPG/)

4. [Twin Delayed DDPG](https://spinningup.openai.com/en/latest/algorithms/ddpg.html)

5. [TD3: Learning To Run With AI](https://towardsdatascience.com/td3-learning-to-run-with-ai-40dfc512f93)

6. [Recurrent Deterministic Policy Gradient Method for BipedalLocomotion on Rough Terrain Challenge](https://arxiv.org/abs/1710.02896)
