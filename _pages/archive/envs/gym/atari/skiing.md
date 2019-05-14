---
layout: page
title: Atari Skiing Environment
permalink: /envs/gym/atari/skiing/

redirect_from:
 - /envs/gym/atari-2600/skiing/
 - /env/gym/atari/skiing/
 - /env/gym/atari-2600/skiing/

nav:
 - name: Overview
   permalink: '#overview'
 - name: Performances
   permalink: '#performances'
---


## Overview

<video autoplay muted loop controls>
  <source src="{{ 'assets/_pages/envs/gym/atari/skiing.mp4' | absolute_url }}" type="video/mp4">
</video>

Skiing is a single player only game, in which the player uses the joystick to control the direction and speed of a stationary skier at the top of the screen, while the background graphics scroll upwards, thus giving the illusion the skier is moving. The player must avoid obstacles, such as trees and moguls. The game cartridge contains five variations each of two principal games.

In the downhill mode, the player's goal is to reach the bottom of the ski course as rapidly as possible, while a timer records his relative success.

In the slalom mode, the player must similarly reach the end of the course as rapidly as he can, but must at the same time pass through a series of gates (indicated by a pair of closely spaced flagpoles). Each gate missed counts as a penalty against the player's time.

*Description from [Wikipedia](https://en.wikipedia.org/wiki/Skiing_%28Atari_2600%29)*


## Performances of RL Agents {#performances}

We list various reinforcement learning algorithms that were tested in this environment. These results are from [RL Database](https://github.com/seungjaeryanlee/rldb). If this page was helpful, please consider giving a star!

<!-- Place this tag where you want the button to render. -->
<a class="github-button" href="https://github.com/seungjaeryanlee/rldb" data-icon="octicon-star" data-size="large" data-show-count="true" aria-label="Star seungjaeryanlee/rldb on GitHub">Star</a>
<!-- Place this tag in your head or just before your close body tag. -->
<script async defer src="https://buttons.github.io/buttons.js"></script>

### Human Starts

| Result | Algorithm | Source |
|--------|-----------|--------|
| -3686.6 | **Human** | Deep Reinforcement Learning with Double Q-learning |
| -3686.6 | **Human** | Dueling Network Architectures for Deep Reinforcement Learning |
| -10169.1 | Prioritized DDQN (rank, tuned) | Prioritized Experience Replay |
| -10852.8 | Prioritized DDQN (prop, tuned) | Prioritized Experience Replay |
| -10911.1 | A3C FF | Asynchronous Methods for Deep Reinforcement Learning |
| -11490.4 | DDQN (tuned) | Deep Reinforcement Learning with Double Q-learning |
| -11685.8 | Rainbow | Rainbow: Combining Improvements in Deep Reinforcement Learning |
| -11928.0 | DuDQN | Dueling Network Architectures for Deep Reinforcement Learning |
| -12142.1 | DQN | Rainbow: Combining Improvements in Deep Reinforcement Learning |
| -13247.7 | Distributional DQN | Rainbow: Combining Improvements in Deep Reinforcement Learning |
| -13700.0 | A3C FF 1 day | Asynchronous Methods for Deep Reinforcement Learning |
| -14863.8 | A3C LSTM | Asynchronous Methods for Deep Reinforcement Learning |
| -15287.4 | **Random** | Deep Reinforcement Learning with Double Q-learning |
| -18955.8 | PDD DQN | Dueling Network Architectures for Deep Reinforcement Learning |
| -29404.3 | DDQN | Deep Reinforcement Learning with Double Q-learning |
| -29404.3 | Prioritized DQN (rank) | Prioritized Experience Replay |


### No-op Starts

| Result | Algorithm | Source |
|--------|-----------|--------|
| -4336.9 | **Human** | Dueling Network Architectures for Deep Reinforcement Learning |
| -7550 | NoisyNet DuDQN | Noisy Networks for Exploration |
| -7989 | DuDQN | Noisy Networks for Exploration |
| -8857.4 | DDQN | A Distributional Perspective on Reinforcement Learning |
| -8857.4 | DuDQN | Dueling Network Architectures for Deep Reinforcement Learning |
| -8988.0 | IMPALA (deep, multitask) | IMPALA: Scalable Distributed Deep-RL with Importance Weighted Actor-Learner Architectures |
| -9163 | QR-DQN-0 | Distributional Reinforcement Learning with Quantile Regression |
| -9289 | IQN | Implicit Quantile Networks for Distributional Reinforcement Learning |
| -9324 | QR-DQN-1 | Distributional Reinforcement Learning with Quantile Regression |
| -10180.38 | IMPALA (deep) | IMPALA: Scalable Distributed Deep-RL with Importance Weighted Actor-Learner Architectures |
| -10632.9 | Reactor ND | The Reactor: A fast and sample-efficient Actor-Critic agent for Reinforcement Learning |
| -10753.4 | Reactor | The Reactor: A fast and sample-efficient Actor-Critic agent for Reinforcement Learning |
| -10870.6 | Reactor | The Reactor: A fast and sample-efficient Actor-Critic agent for Reinforcement Learning |
| -12630 | DQN | Noisy Networks for Exploration |
| -12957.8 | Rainbow | Rainbow: Combining Improvements in Deep Reinforcement Learning |
| -12972 | A3C | Noisy Networks for Exploration |
| -13062.3 | DQN | A Distributional Perspective on Reinforcement Learning |
| -13062.3 | DQN | Rainbow: Combining Improvements in Deep Reinforcement Learning |
| -13901 | C51 | A Distributional Perspective on Reinforcement Learning |
| -14763 | NoisyNet DQN | Noisy Networks for Exploration |
| -14959.8 | Distributional DQN | Rainbow: Combining Improvements in Deep Reinforcement Learning |
| -15970 | NoisyNet A3C | Noisy Networks for Exploration |
| -17098.1 | **Random** | Dueling Network Architectures for Deep Reinforcement Learning |
| -19949.9 | PDD DQN | Dueling Network Architectures for Deep Reinforcement Learning |
| -29975.0 | IMPALA (shallow) | IMPALA: Scalable Distributed Deep-RL with Importance Weighted Actor-Learner Architectures |


### Normal Starts

| Result | Algorithm | Source |
|--------|-----------|--------|

