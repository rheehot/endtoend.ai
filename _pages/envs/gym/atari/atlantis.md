---
layout: page
title: Atari Atlantis Environment
permalink: /envs/gym/atari/atlantis

redirect_from:
 - /envs/gym/atari-2600/atlantis
 - /env/gym/atari/atlantis
 - /env/gym/atari-2600/atlantis

nav:
 - name: Overview
   permalink: '#overview'
 - name: State of the Art
   permalink: '#state-of-the-art'
---


## Overview

<video autoplay muted loop controls>
  <source src="{{ 'assets/_pages/envs/gym/atari/atlantis.mp4' | absolute_url }}" type="video/mp4">
</video>

The player controls the last defenses of the City of Atlantis against the Gorgon invaders. The city has seven bases, which are vulnerable to attack. Three of these have firepower capabilities to destroy the Gorgon ships before they manage to fire death rays at one of the settlements. The gun bases have fixed cannons; the center base fires straight up, while the far left and far right bases fire diagonally upwards across the screen. The center cannon also creates a shield that protects the settlements from the death rays, so once the center cannon is destroyed, the remaining settlements become vulnerable to attack. The enemy ships pass back and forth from left to right four times before they enter firing range, giving an ample opportunity to blow them away. Lost bases can be regained by destroying enough Gorgon ships.

*Description from [Wikipedia](https://en.wikipedia.org/wiki/Atlantis_%28video_game%29)*


## State of the Art

### Human Starts

| Result | Method | Type | Score from |
|--------|--------|------|------------|
| 918714.5 | ApeX DQN | DQN | [Distributed Prioritized Experience Replay](https://arxiv.org/abs/1803.00933) |
| 911091.0 | A3C FF (4 days) | PG | [Asynchronous Methods for Deep Learning](https://arxiv.org/abs/1602.01783) |
| 875822.0 | A3C LSTM | PG | [Asynchronous Methods for Deep Learning](https://arxiv.org/abs/1602.01783) |
| 814684.0 | RainbowDQN | DQN | [Rainbow: Combining Improvements in Deep Reinforcement Learning](https://arxiv.org/abs/1710.02298) |
| 772392.0 | A3C FF (1 day) | PG | [Asynchronous Methods for Deep Learning](https://arxiv.org/abs/1602.01783) |
| 629166.5 | GorilaDQN | DQN | [Massively Parallel Methods for Deep Reinforcement Learning](https://arxiv.org/abs/1507.04296) |
| 593642.0 | PERDDQN (prop) | DQN | [Prioritized Experience Replay](https://arxiv.org/abs/1511.05952) |
| 445360.0 | DuelingDDQN | DQN | [Dueling Network Architectures for Deep Reinforcement Learning](https://arxiv.org/abs/1511.06581) |
| 423252.0 | DuelingPERDQN | DQN | [Dueling Network Architectures for Deep Reinforcement Learning](https://arxiv.org/abs/1511.06581) |
| 330647.0 | PERDDQN (rank) | DQN | [Prioritized Experience Replay](https://arxiv.org/abs/1511.05952) |
| 319688.0 | DDQN | DQN | [Deep Reinforcement Learning with Double Q-learning](https://arxiv.org/abs/1509.06461) |
| 303666.5 | NoisyNetDQN | DQN | [Rainbow: Combining Improvements in Deep Reinforcement Learning](https://arxiv.org/abs/1710.02298) |
| 292491.0 | DQN2015 | DQN | [Dueling Network Architectures for Deep Reinforcement Learning](https://arxiv.org/abs/1511.06581) |
| 289803.0 | DistributionalDQN | DQN | [Rainbow: Combining Improvements in Deep Reinforcement Learning](https://arxiv.org/abs/1710.02298) |
| 207526.0 | PERDQN (rank) | DQN | [Prioritized Experience Replay](https://arxiv.org/abs/1511.05952) |
| 76108.0 | DQN2015 | DQN | [Massively Parallel Methods for Deep Reinforcement Learning](https://arxiv.org/abs/1507.04296) |
| **26575.0** | **Human** | Human | [Massively Parallel Methods for Deep Reinforcement Learning](https://arxiv.org/abs/1507.04296) |
| **13463.0** | **Random** | Random | [Massively Parallel Methods for Deep Reinforcement Learning](https://arxiv.org/abs/1507.04296) |

### No-op Starts

| Result | Method | Type | Score from |
|--------|--------|------|------------|
| 3433182.0 | ACKTR | PG | [Scalable trust-region method for deep reinforcement learning using Kronecker-factored approximation](https://arxiv.org/abs/1708.05144) |
| 972175.0 | NoisyNet-DuelingDQN | DQN | [Noisy Networks for Exploration](https://arxiv.org/abs/1706.10295) |
| 944497.5 | ApeX DQN | DQN | [Distributed Prioritized Experience Replay](https://arxiv.org/abs/1803.00933) |
| 923733.0 | NoisyNet-DQN | DQN | [Noisy Networks for Exploration](https://arxiv.org/abs/1706.10295) |
| 920213.9 | DQfD | Imitation | [Deep Q-Learning from Demonstrations](https://arxiv.org/abs/1704.03732) |
| 902742.0 | DuelingDQN | DQN | [Noisy Networks for Exploration](https://arxiv.org/abs/1706.10295) |
| 876000.0 | DQN | DQN | [Noisy Networks for Exploration](https://arxiv.org/abs/1706.10295) |
| 841075.0 | C51 | Misc | [A Distributional Perspective on Reinforcement Learning](https://arxiv.org/abs/1707.06887) |
| 826659.5 | RainbowDQN | DQN | [Rainbow: Combining Improvements in Deep Reinforcement Learning](https://arxiv.org/abs/1710.02298) |
| 465700.0 | NoisyNet-A3C | PG | [Noisy Networks for Exploration](https://arxiv.org/abs/1706.10295) |
| 427658.0 | PERDDQN (prop) | DQN | [Rainbow: Combining Improvements in Deep Reinforcement Learning](https://arxiv.org/abs/1710.02298) |
| 422700.0 | A3C | PG | [Noisy Networks for Exploration](https://arxiv.org/abs/1706.10295) |
| 395762.0 | DuelingPERDQN | DQN | [Dueling Network Architectures for Deep Reinforcement Learning](https://arxiv.org/abs/1511.06581) |
| 382572.0 | DuelingDDQN | DQN | [Dueling Network Architectures for Deep Reinforcement Learning](https://arxiv.org/abs/1511.06581) |
| 357324.0 | PER | DQN | [Scalable trust-region method for deep reinforcement learning using Kronecker-factored approximation](https://arxiv.org/abs/1708.05144) |
| 357324.0 | PERDDQN (rank) | DQN | [Dueling Network Architectures for Deep Reinforcement Learning](https://arxiv.org/abs/1511.06581) |
| 340076.0 | DDQN+PopArt | DQN | [Learning values across many orders of magnitude](https://arxiv.org/abs/1602.07714) |
| 329010.0 | NoisyNetDQN | DQN | [Rainbow: Combining Improvements in Deep Reinforcement Learning](https://arxiv.org/abs/1710.02298) |
| 303374.8 | DuelingPERDDQN | DQN | [Deep Q-Learning from Demonstrations](https://arxiv.org/abs/1704.03732) |
| 279987.0 | DQN2015 | DQN | [Dueling Network Architectures for Deep Reinforcement Learning](https://arxiv.org/abs/1511.06581) |
| 273895.0 | DistributionalDQN | DQN | [Rainbow: Combining Improvements in Deep Reinforcement Learning](https://arxiv.org/abs/1710.02298) |
| 106056.0 | DDQN | DQN | [Dueling Network Architectures for Deep Reinforcement Learning](https://arxiv.org/abs/1511.06581) |
| 100069.16 | GorilaDQN | DQN | [Massively Parallel Methods for Deep Reinforcement Learning](https://arxiv.org/abs/1507.04296) |
| 85950.0 | DQN2015 | DQN | [Massively Parallel Methods for Deep Reinforcement Learning](https://arxiv.org/abs/1507.04296) |
| 85641 | DQN2015 | DQN | [Human-level control through deep reinforcement learning](https://storage.googleapis.com/deepmind-media/dqn/DQNNaturePaper.pdf) |
| 64758.0 | DDQN | DQN | [Deep Reinforcement Learning with Double Q-learning](https://arxiv.org/abs/1509.06461) |
| 62687 | Linear | Misc | [Human-level control through deep reinforcement learning](https://storage.googleapis.com/deepmind-media/dqn/DQNNaturePaper.pdf) |
| **29028** | **Human** | Human | [Human-level control through deep reinforcement learning](https://storage.googleapis.com/deepmind-media/dqn/DQNNaturePaper.pdf) |
| **12850** | **Random** | Random | [Human-level control through deep reinforcement learning](https://storage.googleapis.com/deepmind-media/dqn/DQNNaturePaper.pdf) |
| **12580.0** | **Random** | Random | [Noisy Networks for Exploration](https://arxiv.org/abs/1706.10295) |
| 852.9 | Contingency | Misc | [Human-level control through deep reinforcement learning](https://storage.googleapis.com/deepmind-media/dqn/DQNNaturePaper.pdf) |

### Normal Starts

| Result | Method | Type | Score from |
|--------|--------|------|------------|
| 2311815.0 | PPO | PG | [Proximal Policy Optimization Algorithms](https://arxiv.org/abs/1707.06347) |
| 1841376.0 | ACER | PG | [Proximal Policy Optimization Algorithms](https://arxiv.org/abs/1707.06347) |
| 729265.3 | A2C | PG | [Proximal Policy Optimization Algorithms](https://arxiv.org/abs/1707.06347) |

