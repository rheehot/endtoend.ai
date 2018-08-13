---
layout: page
title: Atari Venture Environment
permalink: /envs/gym/atari/venture/

redirect_from:
 - /envs/gym/atari-2600/venture/
 - /env/gym/atari/venture/
 - /env/gym/atari-2600/venture/

nav:
 - name: Overview
   permalink: '#overview'
 - name: State of the Art
   permalink: '#state-of-the-art'
---


## Overview

<video autoplay muted loop controls>
  <source src="{{ 'assets/_pages/envs/gym/atari/venture.mp4' | absolute_url }}" type="video/mp4">
</video>

The goal of Venture is to collect treasure from a dungeon. Winky is equipped with a bow and arrow and explores a dungeon with rooms and hallways. The hallways are patrolled by large, tentacled monsters named Hallmonsters, which cannot be killed, injured, or stopped in any way. Once in a room, Winky may kill monsters, avoid traps and gather treasures. If they stay in any room too long, a Hallmonster will enter the room, chase and kill them. In this way, the Hallmonsters serve the same role as "Evil Otto" in the arcade game Berzerk. The more quickly the player finishes each level, the higher their score.

The goal of each room is only to steal the room's treasure. In most rooms, it is possible (though difficult) to steal the treasure without defeating the monsters within. Some rooms have traps that are only sprung when the player picks up the treasure. For instance, in "The Two-Headed Room", two 2-headed ettins appear the moment the player picks up the prize.

Winky dies if he touches a monster or Hallmonster. Dead monsters decay over time and their corpses may block room exits, delaying Winky and possibly allowing the Hallmonster to enter. Shooting a corpse causes it to regress back to its initial death phase. The monsters themselves move in specific patterns but may deviate to chase the player, and the game's AI allows them to dodge the player's shots with varying degrees of "intelligence" (for example, the snakes of "The Serpent Room" are relatively slow to dodge arrows, the trolls of "The Troll Room" are quite adept at evasion).

The game consists of three different dungeon levels with different rooms. After clearing all the rooms in a level the player advances to the next. After three levels the room pattern and monsters repeat, but at a higher speed and with a different set of treasures.

The different dungeons in each level are as follows:

 * Level 1 - The Wall Room, The Serpent Room, The Skeleton Room, The Goblin Room
 * Level 2 - The Two-Headed Room, The Dragon Room, The Spider Room, The Troll Room
 * Level 3 - The Genie Room, The Demon Room, The Cyclops Room, The Bat Room


*Description from [Wikipedia](https://en.wikipedia.org/wiki/Venture_(video_game))*


## State of the Art

### Human Starts

| Result | Method | Type | Score from |
|--------|--------|------|------------|
| **1039.0** | **Human** | Human | [Massively Parallel Methods for Deep Reinforcement Learning](https://arxiv.org/abs/1507.04296) |
| 935.5 | ApeX DQN | DQN | [Distributed Prioritized Experience Replay](https://arxiv.org/abs/1803.00933) |
| 523.4 | GorilaDQN | DQN | [Massively Parallel Methods for Deep Reinforcement Learning](https://arxiv.org/abs/1507.04296) |
| 462.0 | DistributionalDQN | DQN | [Rainbow: Combining Improvements in Deep Reinforcement Learning](https://arxiv.org/abs/1710.02298) |
| 244.0 | PERDDQN (prop) | DQN | [Prioritized Experience Replay](https://arxiv.org/abs/1511.05952) |
| 200.0 | DuelingDDQN | DQN | [Dueling Network Architectures for Deep Reinforcement Learning](https://arxiv.org/abs/1511.06581) |
| 136.0 | DQN2015 | DQN | [Dueling Network Architectures for Deep Reinforcement Learning](https://arxiv.org/abs/1511.06581) |
| 110.0 | PERDQN (rank) | DQN | [Prioritized Experience Replay](https://arxiv.org/abs/1511.05952) |
| 94.0 | PERDDQN (rank) | DQN | [Prioritized Experience Replay](https://arxiv.org/abs/1511.05952) |
| 54.0 | DQN2015 | DQN | [Massively Parallel Methods for Deep Reinforcement Learning](https://arxiv.org/abs/1507.04296) |
| 45.0 | RainbowDQN | DQN | [Rainbow: Combining Improvements in Deep Reinforcement Learning](https://arxiv.org/abs/1710.02298) |
| 29.0 | DuelingPERDQN | DQN | [Dueling Network Architectures for Deep Reinforcement Learning](https://arxiv.org/abs/1511.06581) |
| 25.0 | A3C LSTM | PG | [Asynchronous Methods for Deep Learning](https://arxiv.org/abs/1602.01783) |
| 23.0 | A3C FF (4 days) | PG | [Asynchronous Methods for Deep Learning](https://arxiv.org/abs/1602.01783) |
| 21.0 | DDQN | DQN | [Deep Reinforcement Learning with Double Q-learning](https://arxiv.org/abs/1509.06461) |
| 19.0 | A3C FF (1 day) | PG | [Asynchronous Methods for Deep Learning](https://arxiv.org/abs/1602.01783) |
| **18.0** | **Random** | Random | [Massively Parallel Methods for Deep Reinforcement Learning](https://arxiv.org/abs/1507.04296) |
| 10.5 | NoisyNetDQN | DQN | [Rainbow: Combining Improvements in Deep Reinforcement Learning](https://arxiv.org/abs/1710.02298) |

### No-op Starts

| Result | Method | Type | Score from |
|--------|--------|------|------------|
| 1813.0 | ApeX DQN | DQN | [Distributed Prioritized Experience Replay](https://arxiv.org/abs/1803.00933) |
| 1520.0 | C51 | Misc | [A Distributional Perspective on Reinforcement Learning](https://arxiv.org/abs/1707.06887) |
| 1433.0 | DuelingDQN | DQN | [Noisy Networks for Exploration](https://arxiv.org/abs/1706.10295) |
| 1245.33 | GorilaDQN | DQN | [Massively Parallel Methods for Deep Reinforcement Learning](https://arxiv.org/abs/1507.04296) |
| **1188** | **Human** | Human | [Human-level control through deep reinforcement learning](https://storage.googleapis.com/deepmind-media/dqn/DQNNaturePaper.pdf) |
| **1187** | **Human** | Human | [RUDDER: Return Decomposition for Delayed Rewards](https://arxiv.org/abs/1806.07857) |
| 1172.0 | DDQN+PopArt | DQN | [Learning values across many orders of magnitude](https://arxiv.org/abs/1602.07714) |
| 1147 | RUDDER | Misc | [RUDDER: Return Decomposition for Delayed Rewards](https://arxiv.org/abs/1806.07857) |
| 1107.0 | DistributionalDQN | DQN | [Rainbow: Combining Improvements in Deep Reinforcement Learning](https://arxiv.org/abs/1710.02298) |
| 863 | PERDDQN | DQN | [RUDDER: Return Decomposition for Delayed Rewards](https://arxiv.org/abs/1806.07857) |
| 863.0 | PERDDQN (prop) | DQN | [Rainbow: Combining Improvements in Deep Reinforcement Learning](https://arxiv.org/abs/1710.02298) |
| 815.0 | NoisyNet-DuelingDQN | DQN | [Noisy Networks for Exploration](https://arxiv.org/abs/1706.10295) |
| 497.0 | DuelingDDQN | DQN | [Dueling Network Architectures for Deep Reinforcement Learning](https://arxiv.org/abs/1511.06581) |
| 380.0 | DQN2015 | DQN | [Human-level control through deep reinforcement learning](https://storage.googleapis.com/deepmind-media/dqn/DQNNaturePaper.pdf) |
| 319.0 | DQN | DQN | [Noisy Networks for Exploration](https://arxiv.org/abs/1706.10295) |
| 163.0 | DQN2015 | DQN | [Dueling Network Architectures for Deep Reinforcement Learning](https://arxiv.org/abs/1511.06581) |
| 163 | DQN | DQN | [RUDDER: Return Decomposition for Delayed Rewards](https://arxiv.org/abs/1806.07857) |
| 98.0 | DDQN | DQN | [Dueling Network Architectures for Deep Reinforcement Learning](https://arxiv.org/abs/1511.06581) |
| 97.0 | NoisyNet-DQN | DQN | [Noisy Networks for Exploration](https://arxiv.org/abs/1706.10295) |
| 93.0 | DDQN | DQN | [Deep Reinforcement Learning with Double Q-learning](https://arxiv.org/abs/1509.06461) |
| 66 | Linear | Misc | [Human-level control through deep reinforcement learning](https://storage.googleapis.com/deepmind-media/dqn/DQNNaturePaper.pdf) |
| 54.0 | PERDDQN (rank) | DQN | [Dueling Network Architectures for Deep Reinforcement Learning](https://arxiv.org/abs/1511.06581) |
| 48.0 | DuelingPERDQN | DQN | [Dueling Network Architectures for Deep Reinforcement Learning](https://arxiv.org/abs/1511.06581) |
| 5.5 | RainbowDQN | DQN | [Rainbow: Combining Improvements in Deep Reinforcement Learning](https://arxiv.org/abs/1710.02298) |
| 0.6 | Contingency | Misc | [Human-level control through deep reinforcement learning](https://storage.googleapis.com/deepmind-media/dqn/DQNNaturePaper.pdf) |
| **0** | **Random** | Random | [Human-level control through deep reinforcement learning](https://storage.googleapis.com/deepmind-media/dqn/DQNNaturePaper.pdf) |
| 0.0 | A3C | PG | [Noisy Networks for Exploration](https://arxiv.org/abs/1706.10295) |
| 0.0 | NoisyNet-A3C | PG | [Noisy Networks for Exploration](https://arxiv.org/abs/1706.10295) |
| 0.0 | NoisyNetDQN | DQN | [Rainbow: Combining Improvements in Deep Reinforcement Learning](https://arxiv.org/abs/1710.02298) |

### Normal Starts

| Result | Method | Type | Score from |
|--------|--------|------|------------|
| 0.0 | A2C | PG | [Proximal Policy Optimization Algorithms](https://arxiv.org/abs/1707.06347) |
| 0.0 | ACER | PG | [Proximal Policy Optimization Algorithms](https://arxiv.org/abs/1707.06347) |
| 0.0 | PPO | PG | [Proximal Policy Optimization Algorithms](https://arxiv.org/abs/1707.06347) |

