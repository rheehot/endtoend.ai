---
layout: post
title: "AI for Prosthetics Week 5: Understanding the Rewards"
author: Seungjae Ryan Lee
permalink: /blog/ai-for-prosthetics-5

front_image: /assets/blog/ai-for-prosthetics-5/front.png
front_text: >
    The goal of reinforcement learning is defined by the reward signal - to
    maximize the cumulative reward throughout an episode. In some ways, the
    reward is the most important aspect of the environment for the agent: even
    if it does not know about values of states or actions (like Evolutionary
    Strategies), if it can consistently get high return (cumulative reward), it
    is a great agent.

nav:
- name: Reward
  permalink: '#reward'
- name: osim-rl-helper
  permalink: '#osim-rl-helper'
- name: What's Next?
  permalink: '#whats-next'
---

## Weeks

- [Week 1: Understanding the Challenge](/blog/ai-for-prosthetics-1)
- [Week 2: Understanding the Action Space](/blog/ai-for-prosthetics-2)
- [Week 3-4: Understanding the Observation Space](/blog/ai-for-prosthetics-3)
- **Week 5: Understanding the Reward**



## Reward

The goal of reinforcement learning is defined by the reward signal - to maximize the cumulative reward throughout an episode. In some ways, the reward is the most important aspect of the environment for the agent: even if it does not know about values of states or actions (like Evolutionary Strategies), if it can consistently get high return (cumulative reward), it is a great agent.



### Reward Calculation

In Round 1, the goal of the agent is to run at a constant speed of 3 meters per second. This is shown by the calculation of reward:

$$ r_t := 9 - \left| 3 - v_t \right|^2 $$

where $v$ is the horizontal velocity vector of the pelvis. In other words,

```python
reward = 9 - abs(3 - obs['body_vel']['pelvis']) ** 2
```

Note that if $\mid 3 - v_t \mid > 3$, then the reward $r_t$ is negative. This is true if the velocity of the pelvis is too fast ($v_t > 3$) or if the velocity is negative ($v_t < 0$). Of course, once the episode is terminated, no more reward can be accumulated.

Now, let's compare two possible ways of going 1 meter: going 1 m/s for 100 steps (1 second) or going 3 m/s for 33 steps (0.33 seconds). For simplicity, let's assume that these are the only rewards the agent receives. Then, the return for the first method is:
$$
\sum^{100}_{k=1} (9 - \left| 3 - 1\right|^2) = 100 \times 5 = 500
$$
In comparison, the return for the second method is:
$$
\sum^{33}_{k=1} (9 - \left| 3 - 3 \right|^2) = 33 \times 9 = 297
$$
There is a surprising amount of difference between the two methods. Of course, the second method is more advantageous if the agent can consistently maintain that velocity, since that will generate the maximum return of 2700. However, if such policy results in a premature termination, slowly accumulating rewards might result in a higher return.

 

### Reward Modification

Recently, there have been great successes on reinforcement learning methods that modify the reward signal. Two noteworthy papers are [Playing hard exploration games by watching YouTube](https://arxiv.org/abs/1805.11592) and [RUDDER: Return Decomposition for Delayed Rewards](https://arxiv.org/abs/1806.07857). The exemplary environment used in these papers are *Montezuma's Revenge* and *Bowling* from Atari 2600. Both games have sparse rewards (few nonzero rewards), so the agent must explore for a long time before discerning good or bad actions. In these games, the state-of-the-art (SotA) methods are one that reshape the reward ([*Bowling* SotA](/envs/gym/atari/bowling), [*Montezuma's Revenge* SotA](/envs/gym/atari/montezumas-revenge)).

The Prosthetics environment has a dense reward function: there is a nonzero reward at every step. Thus, the agent can be trained without modifying the reward in any way. However, that does not prohibit us from modifying the reward signal. Therefore, complex modifications like Imitation Learning (DQfD or YouTube) might not be needed, but the environment could benefit from a reward signal that is more insightful.

Note that this is a somewhat dangerous approach. We are attempting to inject our prior knowledge to the agent through the reward. In general, the reward signal should communicate the agent *what* its goal is, not *how* it should achieve that goal. A better place to use prior knowledge is initial policy or value function (Sutton and Barto, 2018). One way to address this problem would be to fine-train the agent without the reward modification once it performs reasonably well.

If it is not obvious how the reward signal should be modified, it is helpful to compare successful and unsuccessful agents. Here are three top-performing agents by *nskiran*, *lijun*, and *rl_agent*, each with the score of 2240.904, 2230.505, and 2192.552.

<video width="50%" autoplay mute loop><source type="video/mp4" src='{{ "/assets/blog/ai-for-prosthetics-5/high1.mp4" | absolute_url }}'></video>

<video width="50%" autoplay mute loop><source type="video/mp4" src='{{ "/assets/blog/ai-for-prosthetics-5/high2.mp4" | absolute_url }}'></video>

<video width="50%" autoplay mute loop><source type="video/mp4" src='{{ "/assets/blog/ai-for-prosthetics-5/high3.mp4" | absolute_url }}'></video>

For comparison, here are 3 agents in the 700~800 range:

<video width="50%" autoplay mute loop><source type="video/mp4" src='{{ "/assets/blog/ai-for-prosthetics-5/med1.mp4" | absolute_url }}'></video>

<video width="50%" autoplay mute loop><source type="video/mp4" src='{{ "/assets/blog/ai-for-prosthetics-5/med2.mp4" | absolute_url }}'></video>

<video width="50%" autoplay mute loop><source type="video/mp4" src='{{ "/assets/blog/ai-for-prosthetics-5/med3.mp4" | absolute_url }}'></video>

Finally, here are 3 agents in the 150~400 range:

<video width="50%" autoplay mute loop><source type="video/mp4" src='{{ "/assets/blog/ai-for-prosthetics-5/low1.mp4" | absolute_url }}'></video>

<video width="50%" autoplay mute loop><source type="video/mp4" src='{{ "/assets/blog/ai-for-prosthetics-5/low2.mp4" | absolute_url }}'></video>

<video width="50%" autoplay mute loop><source type="video/mp4" src='{{ "/assets/blog/ai-for-prosthetics-5/low3.mp4" | absolute_url }}'></video>



#### Stayin' Alive

One of the noticeable difference between the agents is that the high performing agents have longer episodes. This is somewhat obvious, you cannot expect the agent to score above 2000 if it cannot stay alive for more than 222 steps. Thus, a good way to train the agent could be to first train it to "stay alive," giving little or no weight to the actual reward distribution. This can be done via a simple reward function:
$$
r_t = 1
$$
This is the exact opposite of other environment settings such as maze-solving where the agent's goal is to have shorter episodes.



#### Stay Somewhat Upright

Now, let's see how the episode gets terminated. The termination switch is the height of the pelvis falling below 0.6 meters, but it seems like the primary cause of all premature termination is the upper body swaying too much. There is a fine line: most top-performing agents also sway their body, perhaps due to the prosthetics making the model fundamentally unbalanced. To inject this knowledge, some fine tuning might be necessary.

Note that this is somewhat similar to the Lean Forward approach used by participants in the last competition. In the last year's competition, there was no $z$-axis, and the model was symmetric, so the upper body was either in front of or behind the body. Thus, the obvious conclusion was to keep the upper body leaning forward, so the reward was shaped to promote this behavior.



## osim-rl-helper

I have refactored the agents and the environment wrappers to give a more consistent experience to those who might be using the `osim-rl-helper` package.



### TensorforcePPOAgent

I created a brand new agent that uses Proximal Policy Optimization Algorithms (PPO) by [Schulman et al. (2017)](https://arxiv.org/abs/1707.06347) and the `tensorforce` package. Most top-performing agents in the last year's Learning to Run contest used either the DDPG algorithm or the PPO algorithm, so try experimenting with both!



## What's Next?

I misinterpreted the text about Round 1 and Round 2. It has been clarified that Round 1 will continue until September 16th, and once it is over, Round 2 will be held until September 30th (tentative). Round 1 is the current round where the agent needs to follow a constant velocity vector $(3, 0, 0)$ as described above. In contrast, for Round 2, the target velocity vector will be time-dependent. More information should be available soon.

Meanwhile, congratulations to the AI for Prosthetics team for having Google Cloud Platform to sponsor! **Top 400 teams with positive points will be awarded $250 cloud credits.** Hope this encourages many of you to participate, since there are currently less than 200 people in the leaderboard.

