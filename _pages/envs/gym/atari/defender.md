---
layout: page
title: Atari Defender Environment
permalink: /envs/gym/atari/defender

redirect_from:
 - /envs/gym/atari-2600/defender
 - /env/gym/atari/defender
 - /env/gym/atari-2600/defender

nav:
 - name: Overview
   permalink: '#overview'
 - name: State of the Art
   permalink: '#state-of-the-art'
---


## Overview

## State of the Art

### Human Starts

| Result | Method | Type | Score from |
|--------|--------|------|------------|
| 399865.3 | ApeX DQN | DQN | [Distributed Prioritized Experience Replay](https://arxiv.org/abs/1803.00933) |
| 233021.5 | A3C LSTM | PG | [Asynchronous Methods for Deep Learning](https://arxiv.org/abs/1602.01783) |
| 56533.0 | A3C FF (4 days) | PG | [Asynchronous Methods for Deep Learning](https://arxiv.org/abs/1602.01783) |
| 47671.3 | RainbowDQN | DQN | [Rainbow: Combining Improvements in Deep Reinforcement Learning](https://arxiv.org/abs/1710.02298) |
| 36242.5 | A3C FF (1 day) | PG | [Asynchronous Methods for Deep Learning](https://arxiv.org/abs/1602.01783) |
| 34415.0 | DuelingPERDQN | DQN | [Dueling Network Architectures for Deep Reinforcement Learning](https://arxiv.org/abs/1511.06581) |
| 33996.0 | DuelingDDQN | DQN | [Dueling Network Architectures for Deep Reinforcement Learning](https://arxiv.org/abs/1511.06581) |
| 32246.0 | DistributionalDQN | DQN | [Rainbow: Combining Improvements in Deep Reinforcement Learning](https://arxiv.org/abs/1710.02298) |
| 27510.0 | DDQN | DQN | [Deep Reinforcement Learning with Double Q-learning](https://arxiv.org/abs/1509.06461) |
| 23666.5 | PERDDQN (rank) | DQN | [Dueling Network Architectures for Deep Reinforcement Learning](https://arxiv.org/abs/1511.06581) |
| 21093.5 | PERDDQN (prop) | DQN | [Prioritized Experience Replay](https://arxiv.org/abs/1511.05952) |
| 20634.0 | PERDQN (rank) | DQN | [Prioritized Experience Replay](https://arxiv.org/abs/1511.05952) |
| 18037.5 | NoisyNetDQN | DQN | [Rainbow: Combining Improvements in Deep Reinforcement Learning](https://arxiv.org/abs/1710.02298) |
| 15917.5 | DQN2015 | DQN | [Dueling Network Architectures for Deep Reinforcement Learning](https://arxiv.org/abs/1511.06581) |
| **14296.0** | **Human** | Human | [Deep Reinforcement Learning with Double Q-learning](https://arxiv.org/abs/1509.06461) |
| **1965.5** | **Random** | Random | [Deep Reinforcement Learning with Double Q-learning](https://arxiv.org/abs/1509.06461) |
| -9001.0 | DQN2015 | DQN | [Asynchronous Methods for Deep Learning](https://arxiv.org/abs/1602.01783) |
| -9001.0 | GorilaDQN | DQN | [Asynchronous Methods for Deep Learning](https://arxiv.org/abs/1602.01783) |

### No-op Starts

| Result | Method | Type | Score from |
|--------|--------|------|------------|
| 411943.5 | ApeX DQN | DQN | [Distributed Prioritized Experience Replay](https://arxiv.org/abs/1803.00933) |
| 55492.0 | NoisyNet-A3C | PG | [Noisy Networks for Exploration](https://arxiv.org/abs/1706.10295) |
| 55105.0 | RainbowDQN | DQN | [Rainbow: Combining Improvements in Deep Reinforcement Learning](https://arxiv.org/abs/1710.02298) |
| 52917.0 | A3C | PG | [Noisy Networks for Exploration](https://arxiv.org/abs/1706.10295) |
| 47092.0 | C51 | Misc | [A Distributional Perspective on Reinforcement Learning](https://arxiv.org/abs/1707.06887) |
| 42253.0 | NoisyNet-DuelingDQN | DQN | [Noisy Networks for Exploration](https://arxiv.org/abs/1706.10295) |
| 42214.0 | DuelingDDQN | DQN | [Dueling Network Architectures for Deep Reinforcement Learning](https://arxiv.org/abs/1511.06581) |
| 41324.5 | DuelingPERDQN | DQN | [Dueling Network Architectures for Deep Reinforcement Learning](https://arxiv.org/abs/1511.06581) |
| 37896.8 | DistributionalDQN | DQN | [Rainbow: Combining Improvements in Deep Reinforcement Learning](https://arxiv.org/abs/1710.02298) |
| 37275.0 | DuelingDQN | DQN | [Noisy Networks for Exploration](https://arxiv.org/abs/1706.10295) |
| 35338.5 | DDQN | DQN | [Dueling Network Architectures for Deep Reinforcement Learning](https://arxiv.org/abs/1511.06581) |
| 31286.5 | PERDDQN (rank) | DQN | [Dueling Network Architectures for Deep Reinforcement Learning](https://arxiv.org/abs/1511.06581) |
| 27951.5 | DQfD | Imitation | [Deep Q-Learning from Demonstrations](https://arxiv.org/abs/1704.03732) |
| 24558.8 | DuelingPERDDQN |  | [Deep Q-Learning from Demonstrations](https://arxiv.org/abs/1704.03732) |
| 24162.5 | PERDDQN (prop) | DQN | [Rainbow: Combining Improvements in Deep Reinforcement Learning](https://arxiv.org/abs/1710.02298) |
| 23633.0 | DQN2015 | DQN | [Dueling Network Architectures for Deep Reinforcement Learning](https://arxiv.org/abs/1511.06581) |
| 23083.0 | NoisyNetDQN | DQN | [Rainbow: Combining Improvements in Deep Reinforcement Learning](https://arxiv.org/abs/1710.02298) |
| 20525.0 | NoisyNet-DQN | DQN | [Noisy Networks for Exploration](https://arxiv.org/abs/1706.10295) |
| **18688.9** | **Human** | Human | [Dueling Network Architectures for Deep Reinforcement Learning](https://arxiv.org/abs/1511.06581) |
| 18303.0 | DQN | DQN | [Noisy Networks for Exploration](https://arxiv.org/abs/1706.10295) |
| 11099.0 | DDQN+PopArt | DQN | [Learning values across many orders of magnitude](https://arxiv.org/abs/1602.07714) |
| **2874.5** | **Random** | Random | [Dueling Network Architectures for Deep Reinforcement Learning](https://arxiv.org/abs/1511.06581) |

