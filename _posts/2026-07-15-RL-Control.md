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
        - Action? Control input?
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
      <h3>Begin </h3>
      <p>How is this different from designing \(u = Kx\)<br>
    </p>
    </button>

    <div class="thought-cloud">
      <h3>Understanding the learned policy</h3>

      <p>
      Comparing with classical control
      </p>

      <div class="thought-evidence">
        - How is this different from designing \(u = Kx\)<br>
        - How do their performance differ with each? <br>
        - Can the learned policy be represented as \(u = Kx\)? Controller identification? <br>
      </div>

    </div>
  </div>

  <div class="flow-arrow"></div>

  <div class="thought-step">
    <button class="flow-node thought-trigger" type="button">
      <h3>Two lines of curiosity</h3>
    </button>

    <div class="thought-cloud">
      <h3>Diving deeper in details of implementation</h3>

      <p>
        Other default environments? More complicated dynamics? 
        Other learning algorithms? 
        <p class="thought-evidence">
        ✓ PPO<br>
        ✓ DQN<br>
        ✓ SAC<br>
        ✓ Discrete and continuous action spaces
      </p>
      
      </p>

      <p>
        Look beneath the defult environments!
      </p>
    </div>
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
            ✓ Discrete and continuous action spaces
        </p>
        </div>
      </div>

    </div>


    <!-- RIGHT BRANCH -->
    <div class="branch">

      <div class="branch-line"></div>

      <div class="thought-step">
        <button class="flow-node thought-trigger" type="button">
          <h3>Environment desing?</h3>
        </button>

        <div class="thought-cloud">
          <h3>What assumptions are already hidden inside Gymnasium? </h3>

          <p>
            Algorithm design often improves learning efficiency. But efficiency
            alone cannot guarantee that the simulated problem meaningfully
            represents the real system.
          </p>
          <p>
            This made me wonder whether environment design can sometimes be the
            more fundamental contribution: deciding what exists, what changes,
            what is observed, and what is rewarded.
        </p>

          <p>
            - Gymnasium makes experimentation easy because the dynamics,
            observations, actions, termination rules, and rewards already exist.<br>
            - useful for benchmarking algorithms, but it also hides many of
            the modeling choices that determine what the agent is actually learning.<br>
            - But what assumptions are already hidden inside the simulator?
          </p>
        </div>
      </div>

      <div class="flow-arrow"></div>

      <div class="thought-step">
        <button class="flow-node thought-trigger" type="button">
          <h3>designing the agent vs designing the
        world</h3>
        </button>

        <div class="thought-cloud">
          <h3>Moving one level lower</h3>

          <p class="thought-evidence">
          ✓reproduce behavior comparable
            to the ready-made environment
        ✓ Custom environment structure<br>
        ✓ State and action spaces<br>
        ✓ Reward function (Designing the reward also led me toward questions about optimal
        control)<br>
        ✓ Environment dynamics
      </p>

        </div>
      </div>

        <div class="flow-arrow"></div>


        <div class="thought-step">
            <button class="flow-node thought-trigger" type="button">
            <h3>What if dynamics are partially known?</h3>
            </button>

            <div class="thought-cloud">
            <h3>Complex systems.</h3>

            <p>
                Complex biological, psychological, or social systems?
            </p>
            </div>
        </div>

        <div class="flow-arrow"></div>


        <div class="thought-step">
            <button class="flow-node thought-trigger" type="button">
            <h3>
                Beyond physical systems? 
            </h3>
            </button>

            <div class="thought-cloud">
            <h3>Internal and external unknowns</h3>

            <p>
                May not have cleanly defined states, inputs, or equations.
            </p>

            </div>
        </div>

        <div class="flow-arrow"></div>


        <div class="thought-step">
            <button class="flow-node thought-trigger" type="button">
            <h3>How should we account for uncertainty?</h3>
            </button>

            <div class="thought-cloud">
            <h3>Uncertainty both about system and environment </h3>

            <p>
                Bayesian framemwork?<br>
                Robust design?
            </p>

            </div>
        </div>

</div>