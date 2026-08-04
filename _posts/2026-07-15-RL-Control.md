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

        <div class="thought-cloud thought-cloud-middle">
          <h3>Other standard environments in Gymnasium? </h3>

          <p>
            - Pendulum<br>
            - Mountaincar<br>
            - Acrobot<br>
            - Bipedal
          </p>
          <p class="thought-evidence">

            ✓ What about more complex systems? Beyond physical systems? Biological, psychological, or social systems with no cleanly defined states, inputs, or equations? Partially known dynamics... Internal and external unknowns...<br>
            ✓ How to account for uncertainty? Both in system and the environment. Bayesian framemwork? Robust design?<br>
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
          <h3>Hidden assumptions inside Gymnasium? </h3>

          <p>
            - Dynamics, observations, actions, termination rules, and rewards already defined in Gymnasium? Useful for benchmarking algorithms!<br>
            - Algorithm design focuses only on learning efficiency? What about meaningfully representing the real system?<br>
            - Environment design (modeling choices) itself a fundamental contribution?
          </p>
          <p class="thought-evidence">
          ✓ Reproduce behavior comparable to the ready-made environment<br>
          ✓ Custom environment<br>
          ✓ Designing the agent vs designing the world?<br>
      </p>

        </div>
      </div>

    </div>
    </div>
</div>

</section>

<section class="related-explorations">

  <h2>Other explorations inspired by this train of thought</h2>

  <div class="related-exploration-list">

    <article class="related-exploration-item">
      <h3>Leveling up simple dynamics</h3>

      <p>
        Gradually moving toward increasingly complex dynamical systems. 
      </p>

      <a href="/research/rl-vs-control/beyond-simple-dynamics/">
        See my train of thought →
      </a>
    </article>

    <article class="related-exploration-item">
      <h3>Designing environments for my own curiosity</h3>

      <p>
        Going beyond standard environments in Gymnasium to explore how RL might intersect with problems I'm personally curious about.
      </p>

      <a href="/research/rl-vs-control/custom-environment/">
        See my train of thought →
      </a>
    </article>

    <article class="related-exploration-item">
      <h3>A mini dive into RL algorithms</h3>

      <p>
        Understanding what distinguishes them, and how they relate to other computational methods.
      </p>

      <a href="/research/rl-vs-control/rl-algorithms/">
        See my train of thought →
      </a>
    </article>

  </div>

</section>

<details class="dynamics-card">
  <summary> Behind the environment</summary>

  <p>
    Nonlinear equations of translational motion of the cart and the rotational motion of the pole.<br>
    The applied force changes both the cart's motion and the pole's rotation, while gravity continuously pulls the pole away from the unstable upright equilibrium.
  </p>

  <div class="equation-card">
    \[
    \ddot{x} =
    \frac{F + m_p \sin\theta
    \left(l\dot{\theta}^2 + g\cos\theta\right)}
    {m_c + m_p\sin^2\theta}
    \]
  </div>

  <div class="equation-card">
    \[
    \ddot{\theta} =
    \frac{-F\cos\theta
    -m_p l\dot{\theta}^2\cos\theta\sin\theta
    -(m_c+m_p)g\sin\theta}
    {l\left(m_c+m_p\sin^2\theta\right)}
    \]
  </div>

</details>
<section class="artifacts">

  <h2>Artifacts from this exploration</h2>

  <div class="artifact-gallery">

  <div class="artifact-card">
    <video controls>
      <source src="/assets/videos/cartpole-rl-episode-0.mp4" type="video/mp4">
    </video>
    <h4>PPO Policy Learning</h4>
    <p>
    This was my starting point for understanding how RL discovers a
    control strategy through interaction rather than from an explicit model.
    Trained a MLP policy with PPO for 100,000 timesteps, resulting in a controller that reliably keeps the pole balanced.
    </p>
  </div>

  <div class="artifact-card">
    <video controls>
      <source src="/assets/videos/cartpole-lqr-episode-0.mp4" type="video/mp4">
    </video>
    <h4>How Does LQR Compare?</h4>
    <p>
    Was curious how a classical optimal controller would compare with the
    policy learned by PPO. Using the linearized CartPole dynamics, LQR performed similarly successful. Realized that choosing the cost matrices (<em>Q</em>
    and <em>R</em>) is itself an important design decision, shaping the
    controller's behavior. With my chosen weights, the controller wasn't particularly concerned with keeping the cart close to the center and mainly focused on keeping the pole upright.
    </p>
  </div>

  <div class="artifact-card">
    <video controls>
      <source src="/assets/videos/cartpole-manual-episode-0.mp4" type="video/mp4">
    </video>
    <h4>Can PPO Be Approximated Linearly?</h4>
    <p>Was curious to know if the learned policy from PPO can be approximated by a linear state-feedback controller. Fit a logistic regression to PPO's actions to get a linearized policy, but it was unable to control the CartPole. I suspect because PPO acts in a discrete action space (left or right), the linearization wouldn't recover the continuous control signal of LQR.
    </p>
  </div>

</div>