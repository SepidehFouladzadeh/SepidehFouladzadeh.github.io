---
layout: exploration
title: "Building an Intuition for the Connection Between Control and Optimization"
description: "Inspired by the idea of reframing optimization as feedback control, here's the path I took to build an intuition for the fundamental concepts connecting the two."
date: 2026-09-22
# reading_time: "1 min read"
linkedin_url: "https://www.linkedin.com/in/sepideh-fouladzadeh/"
permalink: /research/control-optimization/
---

<p>
  As usual, I started with one of the simplest systems I could find to
  establish a foundation before exploring the connections between control,
  dynamical systems, and optimization. :)
</p>

<p>
  This is the same cart-pole system from my previous exploration of
  reinforcement learning, but this time I implemented the dynamics myself
  instead of relying on a prebuilt environment from a package.
</p>

<p>
  The setup is simple: an inverted pendulum is attached to a cart that can
  move along the x-axis. The only control input is a horizontal force that
  pushes the cart left or right.
</p>

<p>
  First, I wanted to see what the system does on its own. Starting the pole
  just 5 degrees to the right of the unstable upright equilibrium, with no
  control input, gravity quickly takes over:
</p>

<details class="dynamics-card">
  <summary> Getting to know the Dynamics</summary>
  <p>
    An intentionally simple model. The cart has mass \(M\), the pole
    is modeled as a massless rigid rod of length \(l\) with a point mass
    \(m\) at its end, a frictionless track, no damping at the pivot, and the only control input \(u\) is a horizontal force
    applied to the cart.
  </p>
  <p>
      The upright position is defined as \(\theta = 0\), with positive
      \(\theta\) corresponding to the pole leaning clockwise / to the right.
    </p>

    <div class="equation-card">
    <h4>The state</h4>

    <p>
      At any instant, the system is described by four state variables:
    </p>

    \[
    \mathbf{z}
    =
    \begin{bmatrix}
      x \\
      \dot{x} \\
      \theta \\
      \dot{\theta}
    \end{bmatrix}
    \]

    <p>
      where \(x\) is the cart position, \(\dot{x}\) its velocity,
      \(\theta\) the pole angle from upright, and \(\dot{\theta}\)
      its angular velocity.
    </p>
  </div>

  <div class="equation-card">
    <h4>Position of the pole mass</h4>

    <p>
      With the pole attached to the cart, the point mass at its end has
      position
    </p>

    \[
    x_p = x + l\sin\theta,
    \qquad
    y_p = l\cos\theta.
    \]

    <p>
      Differentiating gives its velocity:
    </p>

    \[
    \dot{x}_p
    =
    \dot{x}
    +
    l\dot{\theta}\cos\theta,
    \qquad
    \dot{y}_p
    =
    -l\dot{\theta}\sin\theta.
    \]
  </div>

  <div class="equation-card">
    <h4>Energy</h4>

    <p>
      From these velocities, the total kinetic energy is
    </p>

    \[
    T
    =
    \frac{1}{2}(M+m)\dot{x}^{2}
    +
    ml\dot{x}\dot{\theta}\cos\theta
    +
    \frac{1}{2}ml^{2}\dot{\theta}^{2},
    \]

    <p>
      while the gravitational potential energy is
    </p>

    \[
    V = mgl\cos\theta.
    \]

    <p>
      I then used the Lagrangian \(L = T - V\) and the
      Euler–Lagrange equations to obtain the equations of motion.
    </p>
  </div>

  <div class="equation-card">
    <h4>Equations of motion</h4>

    \[
    (M+m)\ddot{x}
    +
    ml\ddot{\theta}\cos\theta
    -
    ml\dot{\theta}^{2}\sin\theta
    =
    u
    \]

    \[
    \ddot{x}\cos\theta
    +
    l\ddot{\theta}
    -
    g\sin\theta
    =
    0.
    \]

    <p>
      These two coupled equations describe how the cart and pole influence
      one another. Solving them for the accelerations gives the form I
      actually use in the simulation.
    </p>
  </div>

  <div class="equation-card">
    <h4>The form used in the simulation</h4>

    \[
    \ddot{x}
    =
    \frac{
      u
      +
      ml\dot{\theta}^{2}\sin\theta
      -
      mg\sin\theta\cos\theta
    }{
      M + m\sin^{2}\theta
    }
    \]

    \[
    \ddot{\theta}
    =
    \frac{
      g\sin\theta
      -
      \ddot{x}\cos\theta
    }{l}.
    \]

    <p>
      Given the current state and control force, these equations give the
      two accelerations. Together with
      \(\dot{x}\) and \(\dot{\theta}\), they define the nonlinear
      state dynamics that I integrate numerically.
    </p>

    \[
    \dot{\mathbf{z}}
    =
    \begin{bmatrix}
      \dot{x} \\
      \ddot{x} \\
      \dot{\theta} \\
      \ddot{\theta}
    \end{bmatrix}
    =
    f(\mathbf{z},u)
    \]
  </div>

</details>

  <div class="artifact-video">
    <video controls preload="metadata">
      <source
        src="/assets/videos/unstable_animation.mp4"
        type="video/mp4"
      >

      Your browser does not support the video element.
    </video>

  </div>

  <p>
  The control problem is straightforward: To apply forces to
  the cart so that the pole returns to and remains near the upright position.
  </p>
 <p>
  I was curious to see how different approaches would solve the same problem,
  so I compared pole placement, LQR, saturated LQR, and MPC:
  </p>

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
      alt="Comparison of pole angle, cart position, and control force for pole placement, LQR, saturated LQR, and MPC"
    >

    <p class="artifact-caption">
      <strong>Same system, different controllers.</strong>
      Intereting to see that stabilization is only part of the story. Different controllers, different transient behavior, and different amounts of control effort.
    </p>
  </div>

  <div class="artifact-figure">
    <img
      src="/assets/images/recovery.png"
      alt="Controller recovery success as the initial pole angle increases"
    >
    <p class="artifact-caption">
      <!-- <strong>How far can I push them?</strong> -->
      Increasing the initial 5 degrees angle to probe where each controller stops being able
      to recover (Stabilize) the system under the conditions I tested.
    </p>
  </div>

</section>

<section class="artifacts">

  <h2>Artifacts from this exploration</h2>

  <div class="artifact-gallery">

  <div class="artifact-card">
  <img src="/assets/images/Eigenvalues.png"
     alt="Eigenvalues of the cart-pole system linearized around the upright equilibrium">
    <h4>Why does the pole fall in the first place?</h4>

      <p>
        Linearizing the nonlinear dynamics around the upright equilibrium
        gives a local linear model with eigenvalues revealing an unstable mode, explaning why the uncontrolled pole falls/is unstable.
      </p>
  </div>

  <div class="artifact-card">
  <img src="/assets/images/region_of_attraction.png"
     alt="Numerical recovery region for saturated LQR over initial pole angle and angular velocity">
    <h4>An empirical 2D slice of the recovery region of saturated LQR</h4>

      <p>
        Not a mathematical proof of the full region of attraction, but varying both the initial pole angle and angular velocity and recording
        whether it recovers the system.
      </p>
  </div>

  <div class="artifact-card">
  <img src="/assets/images/linear_vs_nonlinear.png"
     alt="Comparison between nonlinear cart-pole dynamics and the linearized model">
    <h4>Linear approximation</h4>

      <p>
        Simply showing that linearized and nonlinear models closely agree near the upright equilibrium. That's why it makes sense to design linear controllers around an inherently nonlinear physical system.
      </p>
  </div>

  <div class="artifact-card">
  <img src="/assets/images/limits.png"
     alt="Linearization error as the initial pole angle increases">
    <h4>Local nature of linearization</h4>

      <p>
        Breakdown of linearization by moving farther from the upright equilibrium.
      </p>
  </div>
</div>

</section>

<section class="related-explorations">

  <h2>Other explorations inspired by this train of thought</h2>

  <div class="related-exploration-list">

    <article class="related-exploration-item">
      <h3>Coming soon.</h3>

      <p>
        Coming soon.
      </p>

      <a href="/research/rl-vs-control/custom-environment/modeling-research/">
        See my train of thought →
      </a>
    </article>

  </div>

</section>