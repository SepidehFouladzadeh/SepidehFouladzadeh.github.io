---
layout: exploration
title: "Understanding Reinforcement Learning Through the lense of Control Theory"
description: "Reinforcement learning seems to have similar concept as control theory. Curious where they overlap and where they fundamentally differ."
date: 2026-07-15
# reading_time: "1 min read"
linkedin_url: "https://www.linkedin.com/in/sepideh-fouladzadeh/"
permalink: /research/rl-vs-control/
---

<p class="flow-instruction">
  Hover over for a few more details ;)
</p>

<div class="flow thought-flow">

  <div class="thought-step">
    <button class="flow-node thought-trigger" type="button">
      <h3>
        Can I understand RL from a control theory perspective?
      </h3>
    </button>

    <div class="thought-cloud">
      <h3>Both seem to have the same goal of achieving a desired behaviour in a system, how do they approach it differently then?</h3>

      <p>
        - One model-based, the other data-driven? But no… How about these then? Model-based RL? data-driven control? Model-free control?<br>
        - Is RL just optimal control (approximate optimal control)?
      </p>
      
    </div>
  </div>

  <div class="flow-arrow"></div>

  <div class="thought-step">
    <button class="flow-node thought-trigger" type="button">
      <h3>
        Fundamental building blocks?
      </h3>
    </button>

    <div class="thought-cloud">
      <h3>Language of RL</h3>

      <p>
        - State<br>
        - Observation? Measured output? <br>
        - Environment? Plant/system + context? <br>
        - Action? Control input?<br>
        - Policy? Controller (The rule that determines the control input)?
      </p>
      
    </div>
  </div>

  <div class="flow-arrow"></div>

  <div class="thought-step">
    <button class="flow-node thought-trigger" type="button">
      <h3>First implementation with a simple system</h3>
    </button>

    <div class="thought-cloud">
      <h3>CartPole</h3>

      <p>
        - Gymnasium’s standard CartPole environment<br>
        - States: position, velocity, pole angle, pole angular velocity<br>
        - Discrete actions/control (left/right)<br>
        - PPO + MLP policy
      </p>
    </div>
  </div>

  <div class="flow-arrow"></div>

  <div class="thought-step">
    <button class="flow-node thought-trigger" type="button">
      <h3>Comparing with classical control</h3>
    </button>

    <div class="thought-cloud">
      <h3>Understanding the learned policy</h3>

      <div class="thought-evidence">
        - How is this different from designing \(u = Kx\)<br>
        - How do their performances compare? <br>
        - Can the learned policy be approximated by a linear controller \(u = Kx\)?
      </div>

    </div>
  </div>

  <div class="flow-arrow"></div>

  <div class="thought-step">
    <button class="flow-node thought-trigger" type="button">
      <h3>Different lines of curiosity</h3>
      <p>
        Diving deeper in details 
      </p>
    </button>
  </div>


  <!-- SPLIT -->
  <div class="split-connector">
    <div class="split-horizontal"></div>
  </div>

  <div class="flow-split">

    <!-- LEFT BRANCH -->
    <div class="branch">

      <div class="branch-line"></div>

      <div class="thought-step">
        <button class="flow-node thought-trigger" type="button">
          <h3>Algorithms in greater depth?</h3>
        </button>

        <div class="thought-cloud thought-cloud-left">
          <h3>Comparing algorithms</h3>
          <p class="thought-evidence">
            ✓ PPO<br>
            ✓ DQN<br>
            ✓ SAC<br>
        </p>
        </div>
      </div>

    </div>
    <!-- Middle BRANCH -->
        <div class="branch">

      <div class="branch-line"></div>

      <div class="thought-step">
        <button class="flow-node thought-trigger" type="button">
          <h3>More complex dynamics?</h3>
        </button>

        <div class="thought-cloud thought-cloud-bottom">
          <h3>Other standard environments in Gymnasium? </h3>

          <p>
            - Pendulum<br>
            - Mountaincar<br>
            - Acrobot<br>
            - Bipedal
          </p>
          <p class="thought-evidence">

            ✓ What about more complex systems? Beyond physical systems? Biological, psychological, or social systems with no cleanly defined states, inputs, or equations? Partially known dynamics... Internal and external unknowns...<br>
            ✓ How to account for uncertainty? Both in system and the environment. Bayesian framemwork? Robust design?
      </p>

        </div>
      </div>

    </div>


    <!-- RIGHT BRANCH -->
    <div class="branch">

      <div class="branch-line"></div>

      <div class="thought-step">
        <button class="flow-node thought-trigger" type="button">
          <h3>Environment design?</h3>
          <p>
            Looking beneath the defult environments
          </p>
        </button>

        <div class="thought-cloud">
          <h3>What assumptions are already hidden inside Gymnasium? </h3>

          <p>
            - Dynamics, observations, actions, termination rules, and rewards already defined in Gymnasium? Useful for benchmarking algorithms!<br>
            - Algorithm design focuses only on learning efficiency? What about meaningfully representing the real system?<br>
            - Environment design (modeling choices) itself a fundamental contribution?
          </p>
          <p class="thought-evidence">
          ✓ Reproduce behavior comparable to the ready-made environment<br>
          ✓ Custom environment<br>
          ✓ Designing the agent vs designing the world?
      </p>

        </div>
      </div>

</div>