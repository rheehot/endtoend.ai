---
layout: revealjs
title: "Fast Papers"
permalink: /fastpapers2/

image: /assets/fastpapers/fastpapers.png
image_type: contain
excerpt: "Fast Papers is a slideshow where each slide summarizes one paper with few sentences and some graphics."

theme: simple
---



<section class="center" data-markdown><textarea data-template>

<h1 class="title">Fast Papers</h1>

Seungjae Ryan Lee / [endtoendAI](https://www.endtoend.ai)

Each slide summarizes a paper with few sentences and some graphics.

<div class="w60">
  <img style="margin: 0;" src="{{ absolute_url }}/assets/fastpapers/phd092815s.gif" alt="">
  <p style="margin: 0; opacity: 0.5;">"Piled Higher and Deeper" by Jorge Cham www.phdcomics.com</p>
</div>

</textarea></section>



<section id="toc" data-markdown><textarea data-template>

# Table of Contents
1. [Observational Overfitting in Reinforcement Learning](#obs-overfit)

</textarea></section>



<section id="obs-overfit" data-markdown><textarea data-template>

# Observational Overfitting in Reinforcement Learning

Song et al., 2019 | https://arxiv.org/abs/1912.02975

<div class="w60">
  <img src="{{ absolute_url }}/assets/fastpapers/obs-overfit/obs_overfit.png" alt="">
</div>

- Agents can overfit to parts of observation irrelevant to MDP dynamics such as the scoreboard or the background, as they are correlated with progress.
- Observational overfitting hurts agent's generalization.
- Overparametrization can mitigate observational overfitting and improve generalization.



</textarea></section>
