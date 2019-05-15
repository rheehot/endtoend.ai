---
layout: page
title: Atari Kangaroo Environment
permalink: /envs/gym/atari/kangaroo/

redirect_from:
 - /envs/gym/atari-2600/kangaroo/
 - /env/gym/atari/kangaroo/
 - /env/gym/atari-2600/kangaroo/

nav:
 - name: Overview
   permalink: '#overview'
 - name: Performances
   permalink: '#performances'
---


## Overview

<video autoplay muted loop controls>
  <source src="{{ 'assets/_pages/envs/gym/atari/kangaroo.mp4' | absolute_url }}" type="video/mp4">
</video>

There are four different levels. Each of them consist of the mother kangaroo on the bottom floor trying to reach the top floor where her joey is being held captive by some monkeys. On each of the levels, there are monkeys who are throwing apples at the mother kangaroo. Sometimes the apples are thrown so that she must jump over them and sometimes they are thrown so that she must duck. If she gets face to face with one of the monkeys, she can punch the monkey with a boxing glove. She can also punch and destroy apples if they're thrown in level with her gloves. Also, there are pieces of fruit that she can jump up and get for points. Additionally, there is at least one bell on each level that she can hit so that more fruits will appear. She must be wary of the big Ape, who will occasionally appear and try to take her gloves away from her. The level must be completed before the time runs out, otherwise the player will lose a life.

Levels 1, 2 and 4 consist of different platforms that the mother kangaroo must jump onto or climb onto via a ladder. On the third level, the cage in which the kid kangaroo is imprisoned is held up by an entire troop of monkeys and there is a horde of apples that the monkey will unleash if five of them climb up there. On this level, the mother kangaroo must punch each monkey in the stack several times until the cage is lowered and when the cage has been lowered enough, the mother kangaroo must climb to the next floor to get to the kid kangaroo before the cage is raised again or before the monkeys have an avalanche of apple cores unleashed.

Kangaroo has a number of clearly visible glitches in the graphics, such as sprites briefly flickering.[

*Description from [Wikipedia](https://en.wikipedia.org/wiki/Kangaroo_%28video_game%29)*


## Performances of RL Agents {#performances}

We list various reinforcement learning algorithms that were tested in this environment. These results are from [RL Database](https://github.com/seungjaeryanlee/rldb). If this page was helpful, please consider giving a star!

<!-- Place this tag where you want the button to render. -->
<a class="github-button" href="https://github.com/seungjaeryanlee/rldb" data-icon="octicon-star" data-size="large" data-show-count="true" aria-label="Star seungjaeryanlee/rldb on GitHub">Star</a>
<!-- Place this tag in your head or just before your close body tag. -->
<script async defer src="https://buttons.github.io/buttons.js"></script>

### Human Starts

| Result | Algorithm | Source |
|--------|-----------|--------|
| 12185.0 | Prioritized DDQN (rank, tuned) | [Prioritized Experience Replay](https://arxiv.org/abs/1511.05952) |
| 11204.0 | DDQN (tuned) | [Deep Reinforcement Learning with Double Q-learning](https://arxiv.org/abs/1509.06461) |
| 10841.0 | Rainbow | [Rainbow: Combining Improvements in Deep Reinforcement Learning](https://arxiv.org/abs/1710.02298) |
| 10334.0 | DuDQN | [Dueling Network Architectures for Deep Reinforcement Learning](https://arxiv.org/abs/1511.06581) |
| 10241.0 | Prioritized DDQN (prop, tuned) | [Prioritized Experience Replay](https://arxiv.org/abs/1511.05952) |
| 9555.5 | Distributional DQN | [Rainbow: Combining Improvements in Deep Reinforcement Learning](https://arxiv.org/abs/1710.02298) |
| 9053.0 | Prioritized DQN (rank) | [Prioritized Experience Replay](https://arxiv.org/abs/1511.05952) |
| 6138.0 | DDQN | [Deep Reinforcement Learning with Double Q-learning](https://arxiv.org/abs/1509.06461) |
| 2739.0 | **Human** | [Massively Parallel Methods for Deep Reinforcement Learning](https://arxiv.org/abs/1507.04296) |
| 2696.0 | DQN | [Massively Parallel Methods for Deep Reinforcement Learning](https://arxiv.org/abs/1507.04296) |
| 1431.0 | Gorila DQN | [Massively Parallel Methods for Deep Reinforcement Learning](https://arxiv.org/abs/1507.04296) |
| 861.0 | PDD DQN | [Dueling Network Architectures for Deep Reinforcement Learning](https://arxiv.org/abs/1511.06581) |
| 125.0 | A3C LSTM | [Asynchronous Methods for Deep Reinforcement Learning](https://arxiv.org/abs/1602.01783) |
| 106.0 | A3C FF 1 day | [Asynchronous Methods for Deep Reinforcement Learning](https://arxiv.org/abs/1602.01783) |
| 100.0 | **Random** | [Massively Parallel Methods for Deep Reinforcement Learning](https://arxiv.org/abs/1507.04296) |
| 94.0 | A3C FF | [Asynchronous Methods for Deep Reinforcement Learning](https://arxiv.org/abs/1602.01783) |


### No-op Starts

| Result | Algorithm | Source |
|--------|-----------|--------|
| 15487 | IQN | [Implicit Quantile Networks for Distributional Reinforcement Learning](https://arxiv.org/abs/1806.06923) |
| 15356 | QR-DQN-1 | [Distributional Reinforcement Learning with Quantile Regression](https://arxiv.org/abs/1710.10044) |
| 15227 | NoisyNet DuDQN | [Noisy Networks for Exploration](https://arxiv.org/abs/1706.10295) |
| 14854.0 | DuDQN | [Dueling Network Architectures for Deep Reinforcement Learning](https://arxiv.org/abs/1511.06581) |
| 14847 | DuDQN | [Noisy Networks for Exploration](https://arxiv.org/abs/1706.10295) |
| 14780 | QR-DQN-0 | [Distributional Reinforcement Learning with Quantile Regression](https://arxiv.org/abs/1710.10044) |
| 14637.5 | Rainbow | [Rainbow: Combining Improvements in Deep Reinforcement Learning](https://arxiv.org/abs/1710.02298) |
| 13651.0 | DDQN | [Deep Reinforcement Learning with Double Q-learning](https://arxiv.org/abs/1509.06461) |
| 13349.0 | Reactor ND | [The Reactor: A fast and sample-efficient Actor-Critic agent for Reinforcement Learning](https://arxiv.org/abs/1704.04651) |
| 12992.0 | DDQN | [A Distributional Perspective on Reinforcement Learning](https://arxiv.org/abs/1707.06887) |
| 12909.0 | Distributional DQN | [Rainbow: Combining Improvements in Deep Reinforcement Learning](https://arxiv.org/abs/1710.02298) |
| 12853 | C51 | [A Distributional Perspective on Reinforcement Learning](https://arxiv.org/abs/1707.06887) |
| 11266.5 | Reactor | [The Reactor: A fast and sample-efficient Actor-Critic agent for Reinforcement Learning](https://arxiv.org/abs/1704.04651) |
| 10944 | NoisyNet DQN | [Noisy Networks for Exploration](https://arxiv.org/abs/1706.10295) |
| 10484.5 | Reactor | [The Reactor: A fast and sample-efficient Actor-Critic agent for Reinforcement Learning](https://arxiv.org/abs/1704.04651) |
| 8240.5 | IMPALA (deep, multitask) | [IMPALA: Scalable Distributed Deep-RL with Importance Weighted Actor-Learner Architectures](https://arxiv.org/abs/1802.01561) |
| 8166 | DQN | [Noisy Networks for Exploration](https://arxiv.org/abs/1706.10295) |
| 7259.0 | DQN | [A Distributional Perspective on Reinforcement Learning](https://arxiv.org/abs/1707.06887) |
| 6740 | DQN | [Human-level control through deep reinforcement learning](https://storage.googleapis.com/deepmind-media/dqn/DQNNaturePaper.pdf) |
| 3150.0 | ACKTR | [Scalable trust-region method for deep reinforcement learning using Kronecker-factored approximation](https://arxiv.org/abs/1708.05144) |
| 3035.0 | **Human** | [Dueling Network Architectures for Deep Reinforcement Learning](https://arxiv.org/abs/1511.06581) |
| 3035.0 | **Human** | [Human-level control through deep reinforcement learning](https://storage.googleapis.com/deepmind-media/dqn/DQNNaturePaper.pdf) |
| 2549.16 | Gorila DQN | [Massively Parallel Methods for Deep Reinforcement Learning](https://arxiv.org/abs/1507.04296) |
| 1792.0 | PDD DQN | [Dueling Network Architectures for Deep Reinforcement Learning](https://arxiv.org/abs/1511.06581) |
| 1632.0 | IMPALA (deep) | [IMPALA: Scalable Distributed Deep-RL with Importance Weighted Actor-Learner Architectures](https://arxiv.org/abs/1802.01561) |
| 1622 | Linear | [Human-level control through deep reinforcement learning](https://storage.googleapis.com/deepmind-media/dqn/DQNNaturePaper.pdf) |
| 1604 | NoisyNet A3C | [Noisy Networks for Exploration](https://arxiv.org/abs/1706.10295) |
| 1166 | A3C | [Noisy Networks for Exploration](https://arxiv.org/abs/1706.10295) |
| 52.0 | **Random** | [Human-level control through deep reinforcement learning](https://storage.googleapis.com/deepmind-media/dqn/DQNNaturePaper.pdf) |
| 47.0 | IMPALA (shallow) | [IMPALA: Scalable Distributed Deep-RL with Importance Weighted Actor-Learner Architectures](https://arxiv.org/abs/1802.01561) |
| 8.8 | Contingency | [Human-level control through deep reinforcement learning](https://storage.googleapis.com/deepmind-media/dqn/DQNNaturePaper.pdf) |


### Normal Starts

| Result | Algorithm | Source |
|--------|-----------|--------|
| 9928.7 | PPO | [Proximal Policy Optimization Algorithm](https://arxiv.org/abs/1707.06347) |
| 50.0 | ACER | [Proximal Policy Optimization Algorithm](https://arxiv.org/abs/1707.06347) |
| 45.3 | A2C | [Proximal Policy Optimization Algorithm](https://arxiv.org/abs/1707.06347) |

