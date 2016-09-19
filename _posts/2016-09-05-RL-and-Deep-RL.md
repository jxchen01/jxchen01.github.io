---
layout: post
title:  "RL and Deep RL"
date:   2016-09-05
excerpt: "A brief description of Reinforcement Learning (RL) and a high level description of Deep DL"
tag:
- Reinforcement Learning
- Deep Learning Study
comments: true
---


# RL and Deep RL


` RL + Deep Learning = Deep RL `

Reference: [David's tutorial](http://icml.cc/2016/tutorials/deep_rl_tutorial.pdf) 

RL is a framework for decision make (math foundation: [Bellman equation](https://en.wikipedia.org/wiki/Bellman_equation)). The core idea is to select the agent's **action** which is mostly likely to achieve the highest ultimate **reward** according to the current environment **state**.

Deep Learning is a framework for learning representation. The core idea is to automatically learn the representation (usually highly complex) of the raw input, which is required to achieve a given objective. 

Three key components in RL are

* Policy: how to select action in certain state
* Value function: how good the state or the action is
* Model: how to represent the environmet 

Each of these three components can adopt deep learning framework to learn the representation, which will be elaborated below, respectively.

### Policy-based Deep RL

One good introduction of policy-based deep RL is [Karpathy's post](http://karpathy.github.io/2016/05/31/rl/).

Core idea: Use neural netowrk to estimate the policy (input: state, output: the probability of each action)

One policy --> Expected final reward --> The gradient of the expected reward --> Update the policy in the gradient direction. 

Key weapon: [Policy Gradients](http://www.scholarpedia.org/article/Policy_gradient_methods)


### Value-based Deep RL

One good introduction of value-based deep RL is [the post from Nervana](https://www.nervanasys.com/demystifying-deep-reinforcement-learning/)

Core idea: Use neural network to estimate the optimal value function, the maximum value can be achieved under any policy. 

Key weapon: [Q-network](https://www.youtube.com/watch?v=dV80NAlEins)

### Model-based Deep RL

[Tutorial](https://www.bcs.rochester.edu/people/robbie/jacobslab/cheat_sheet/ModelBasedRL.pdf) 

Core idea: Model the environment, plan using the model


