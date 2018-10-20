---
layout: post
title: "Slow Papers: A Deeper Look at Experience Replay (Zhang and Sutton, 2017)"
author: Seungjae Ryan Lee
permalink: /slowpapers/a-deeper-look-at-experience-replay/

front_image: /assets/blog/slowpapers/a-deeper-look-at-experience-replay/front.png
meta_image: /assets/blog/slowpapers/a-deeper-look-at-experience-replay/front.png
front_image_type: contain
front_text: >
    Recently experience replay is widely used in various deep reinforcement learning (RL) algorithms, in this paper we rethink the utility of experience replay. It introduces a new hyper-parameter, the memory buffer size, which needs carefully tuning. However unfortunately the importance of this new hyper-parameter has been underestimated in the community for a long time. In this paper we did a systematic empirical study of experience replay under various function representations. We showcase that a large replay buffer can significantly hurt the performance. Moreover, we propose a simple O(1) method to remedy the negative influence of a large replay buffer. We showcase its utility in both simple grid world and challenging domains like Atari games.

excerpt: >
    Recently experience replay is widely used in various deep reinforcement learning (RL) algorithms, in this paper we rethink the utility of experience replay. It introduces a new hyper-parameter, the memory buffer size, which needs carefully tuning. However unfortunately the importance of this new hyper-parameter has been underestimated in the community for a long time. In this paper we did a systematic empirical study of experience replay under various function representations. We showcase that a large replay buffer can significantly hurt the performance. Moreover, we propose a simple O(1) method to remedy the negative influence of a large replay buffer. We showcase its utility in both simple grid world and challenging domains like Atari games.

nav:
- name: 1 Introduction
  permalink: '#1-introduction'
- name: 2 Related Work
  permalink: '#2-related-work'
- name: 3 Algorithms
  permalink: '#3-algorithms'
- name: 4 Testbeds
  permalink: '#4-testbeds'
- name: 5 Evaluation
  permalink: '#5-evaluation'
- name: 6 Conclusion
  permalink: '#6-conclusion'

---

![Abstract](../assets/blog/slowpapers/a-deeper-look-at-experience-replay/front.png)

**Title**: A Deeper Look at Experience Replay

**Authors**
<div>
<ul class="slowpapers__authors">
  <li><a href="https://shangtongzhang.github.io/">Shangtong Zhang</a>, Graduate student at University of Oxford</li>
  <li><a href="http://www.incompleteideas.net/">Richard S. Sutton</a>, Professor at University of Alberta</li>
</ul>
</div>

**Prerequisites**
 - *Playing Atari with Deep Reinforcement Learning* (Mnih et al., 2013) [[PDF]](https://arxiv.org/abs/1312.5602)
 - *Human-level control through Deep Reinforcement Learning* (Mnih et al., 2015) [[PDF]](https://storage.googleapis.com/deepmind-media/dqn/DQNNaturePaper.pdf)

**Accompanying Resources**
 - *Self-improving reactive agents based on reinforcement learning, planning and teaching* (Lin, 1992) [[PDF]](http://www.incompleteideas.net/lin-92.pdf)
 - *Prioritized Experience Replay* (Schaul et al., 2015) [[PDF]](https://arxiv.org/abs/1511.05952)
 - *Hindsight Experience Replay* (Andrychowicz et al., 2017) [[PDF]](https://arxiv.org/abs/1707.01495)
 - *The Effects of Memory Replay in Reinforcement Learning* (Liu and Zou, 2017) [[PDF]](https://arxiv.org/abs/1710.06574)
<hr/>


*This is a part of the [**Slow Papers**](/slowpapers) series that peruses each selected paper slowly to gain a deeper understanding of the paper.*


Experience Replay dramatically increases the data efficiency. Furthermore, it is the only method that can generate uncorrelated data for online training without changing the problem setting. Thus, it has been used in many seminal algorithms such as Deep Deterministic Policy Gradient (DDPG), Hindsight Experience Replay (HER) and all Deep Q-Networks (DQN) methods.

Although experience replay has been integrated to widely different algorithms with different neural network architectures that interact with different environments, most experiments were done using the default value of $10^6$. This is not a problem if experience replay is robust under such differences, but in fact, the size of the replay buffer can heavily hurt the training process. When the replay buffer is too small, the replay buffer serves little to no purpose. If the replay buffer is too big, the batched samples are uncorrelated, but the agent will learn from the newest experience a long time after.

Thus, to mitigate this problem, we combine online learning and experience replay into **Combined Experience Replay**. At each timestep, the agent learns from a batch that consists of both the immediate transition $t$ and the sampled minibatch $B$.

![Combined Experience Replay](../assets/blog/slowpapers/a-deeper-look-at-experience-replay/combined_experience_replay.png)

To test the effects of Combined Experience Replay, we combine it with Q-Learning (denoted Combined-Q) and test it against Online Q-Learning method (denoted Online-Q) and Q-Learning with Experience Replay (denoted Buffer-Q). We test it on three popular environments: Gridworld, Lunar Lander, and Atari Pong.

Combined-Q significantly improved the performance for suboptimal replay buffer sizes in these environments:
 * Gridworld with tabular function representation
 * Gridworld with linear function approximator
 * Gridworld with non-linear function approximator

![Gridworld with tabular function approximator](../assets/blog/slowpapers/a-deeper-look-at-experience-replay/gridworld_tabular.png)

![Gridworld with linear function approximator](../assets/blog/slowpapers/a-deeper-look-at-experience-replay/gridworld_linear.png)

![Gridworld with non-linear function approximator](../assets/blog/slowpapers/a-deeper-look-at-experience-replay/gridworld_nonlinear.png)

However, it had little to no impact in these environments:
 * Lunar Lander with non-linear function approximator
 * Pong with non-linear function approximator

![Lunar Lander with non-linear function approximator](../assets/blog/slowpapers/a-deeper-look-at-experience-replay/lunarlander_nonlinear.png)

![Pong with non-linear function approximator](../assets/blog/slowpapers/a-deeper-look-at-experience-replay/pong_nonlinear.png)

As the varied degree of success show, "CER is only a workaround, the idea of experience replay itself is heavily flawed."


<hr/>


## 1 Introduction

[TODO Introduce Experience Replay]

<figure>
  <img src="../assets/blog/slowpapers/a-deeper-look-at-experience-replay/definition-of-er.png" alt="Lin92"/>
  <figcaption>From <em>Self-improving reactive agents based on reinforcement learning, planning and teaching</em> (Lin, 1992)</figcaption>
</figure>

[TODO Uncorrelated data, Data efficiency]

[TODO ER is not perfect]

[TODO Default hyperparameter value]

[TODO Figure of same hyperparmeter value from differnet papers]

<figure>
  <img class="w100" src="../assets/blog/slowpapers/a-deeper-look-at-experience-replay/dqn-param.png" alt="DQN Parameters"/>
  <figcaption>From <em></em> (Mnih et al., 2015)</figcaption>
</figure>
<figure>
  <img class="w80" src="../assets/blog/slowpapers/a-deeper-look-at-experience-replay/ddpg-param.png" alt="DDPG Parameters"/>
  <figcaption>From <em></em> (ASDF et al., 2016)</figcaption>
</figure>
<figure>
  <img class="w80" src="../assets/blog/slowpapers/a-deeper-look-at-experience-replay/her-param.png" alt="HER Parameters"/>
  <figcaption>From <em></em> (ASDF et al., 2017)</figcaption>
</figure>

[TODO List contributions: Evaluate ER, Propose CER]

[TODO Q Learning (Tabular, Approximate)]


<figure>
  <img src="../assets/blog/slowpapers/a-deeper-look-at-experience-replay/Watkins89.png" alt="Watkins89"/>
  <figcaption>From page 96 of <em>Learning from Delayed Rewards</em> (Watkins, 1989)</figcaption>
</figure>

<figure>
  <img src="../assets/blog/slowpapers/a-deeper-look-at-experience-replay/dqn-er.png" alt="Mnih13"/>
  <figcaption>From <em>Playing Atari with Deep Reinforcement Learning</em> (Mnih et al., 2013)</figcaption>
</figure>

![Environment](../assets/blog/slowpapers/a-deeper-look-at-experience-replay/fig1.png)


In Reinforcement Learning, the agent learns to maximize the cumulative reward through interactions with the environment. The most direct way to learn from these interactions is by learning *online*, at every timestep with the latest interaction with the environment. The agent uses transitions $(s, a, r, s')$ to update its value function or policy.

![Online Learning](../assets/blog/slowpapers/a-deeper-look-at-experience-replay/fig1.png)

Although this is a powerful learning method, it suffers from two problems:


To mitigate these problems, many algorithms use **Experience Replay**, a method of storing experience into a *replay buffer*. With this method, instead of learning from the latest transition, the agent learns from a minibatch $B$ sampled from the replay buffer.

![Experience Replay](../assets/blog/slowpapers/a-deeper-look-at-experience-replay/experience_replay.png)

Except using mutiple parallelized workers, there is no other way to generate uncorrelated data. Thus, experience replay has been used in many recent deep reinforcement learning algorithms.



## 2 Related Work

[TODO Compare with PER]

[TODO Liu and Zou 2017]

[TODO ER vs Dyna]

[TODO ER vs A3C]

## 3 Algorithms

[TODO Explain ER and sampling]

[TODO Online-Q, Buffer-Q, Combined-Q (Figures)]

## 4 Testbeds

[TODO Individual Figures]

## 5 Evaluation
## 5.1 Tabular Function Representation
## 5.2 Linear Function Approximation
## 5.3 Non-linear Function Approximation
## 6 Conclusion

[TODO Flaw of ER]

[TODO CER is only a workaround]


<hr/>



## Final Thoughts

**Questions**
 - TBA

**Recommended Next Papers**
 - TBA
