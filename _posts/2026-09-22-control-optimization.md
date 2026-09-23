---
layout: exploration
title: "Building an Intuition for the Connection Between Control and Optimization"
description: "Inspired by the idea of reframing optimization as feedback control, here's the path I took to build an intuition for the fundamental concepts connecting the two."
date: 2026-09-22
# reading_time: "1 min read"
linkedin_url: "https://www.linkedin.com/in/sepideh-fouladzadeh/"
permalink: /research/control-optimization/
---

As usual, I started off with one of the simplest systems to first establish the foundation for exploring different concepts in control and optimization. :)
It's the same cartpole system in the previous exploration on Rrinforecemnet learning, but this time I implemented the dynamics manually rarher than a default environment from any package. so it's the same reverse pendulum dynamics, with the only control input as pushing the cart left or right on the x axis.

Below you can see without any control input and with intila condition strating the pendulum from 5 degrees to the right of the upright position, gravity makes it fall.

  <div class="artifact-video">
    <video controls preload="metadata">
      <source
        src="/assets/videos/unstable_animation.mp4"
        type="video/mp4"
      >

      Your browser does not support the video element.
    </video>

  </div>

  The goal is to stabilize this system and keep the pole upright by designing controllers. I was curious to compare ...

  <div class="artifact-video">
    <video controls preload="metadata">
      <source
        src="/assets/videos/controller_comparison.mp4"
        type="video/mp4"
      >

      Your browser does not support the video element.
    </video>

  </div>

  <section class="artifacts">

  <!-- <h2>Artifacts from this exploration</h2> -->

  <div class="artifact-figure">
    <img
      src="/assets/images/force.png"
      alt="Learned weekly allocation"
    >

    <p class="artifact-caption">
      <strong>...</strong>
      ...
    </p>
  </div>

  <div class="artifact-figure">
    <img
      src="/assets/images/recovery.png"
      alt="State evolution"
    >

    <p class="artifact-caption">
      <strong>...</strong>
      ...
    </p>
  </div>

  <div class="artifact-figure">
    <img
      src="/assets/images/reward_components.png"
      alt="Reward components"
    >

    <p class="artifact-caption">
      <strong>Reward components.</strong>
      Weekly contribution of each reward component during evaluation.
    </p>
  </div>

</section>

  <!-- =========================================================
       INTERPRETATION
  ========================================================== -->

<section class="artifact-section">

  <div class="limitations-box">
    <h4>Interpreting the learned policy</h4>
    <p>
      The behavior reflects the transition equations, reward
      priorities, random disturbances, initial conditions, and state
      definitions designed for the environment.
    </p>

    <p>
      The purpose was to make those assumptions inspectable, not to build a sophisticated model of the research process, which might be an interesting direction to explore next! ;)
    </p>
  </div>

</section>

<section class="related-explorations">

  <h2>Other explorations inspired by this train of thought</h2>

  <div class="related-exploration-list">

    <article class="related-exploration-item">
      <h3>Modeling the Research Process</h3>

      <p>
        Exploring related modeling frameworks: What questions can other modeling frameworks answer using the same assumptions?
      </p>

      <a href="/research/rl-vs-control/custom-environment/modeling-research/">
        See my train of thought →
      </a>
    </article>

  </div>

</section>