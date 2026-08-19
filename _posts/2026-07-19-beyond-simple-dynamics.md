---
layout: exploration
title: "Leveling up simple dynamics"
description: "Gradually moving toward increasingly complex dynamical systems."
date: 2026-07-19
# reading_time: "1 min read"
linkedin_url: "https://www.linkedin.com/in/sepideh-fouladzadeh/"
permalink: /research/rl-vs-control/beyond-simple-dynamics/
back_url: /research/rl-vs-control/
back_text: Back to where this began
---

  <section class="exploration-intro"> 
    <p> After CartPole, I was curious to explore other default Gymnasium environments that introduce different control challenges, including continuous actions, momentum building, underactuation, larger state spaces, and coordinated movement. 
    </p>

    <p> I compared shorter and longer training runs to see when additional experience improves performance, when learning begins to plateau, and when the choice of algorithm, reward structure, or training setup matters more than training duration alone. 
    </p> 
  </section>

  <!-- =========================================================
      PENDULUM
  ========================================================== -->

  <section class="artifact-section">

    <div class="artifact-section-heading">
      <h2>Pendulum</h2>
  <p>
    Pendulum replaces CartPole's discrete left-or-right pushes with a
    continuous torque to swing the pendulum toward the
    upright position and stabilize it.
  </p>

    </div>

    <details class="dynamics-card">
      <summary>
        <div>
          <strong>Behind the environment</strong>
        </div>
      </summary>

  <div class="dynamics-content">
    <p>
      The state represents the pendulum's angle and angular velocity. The
      action is a continuous torque applied at the joint. Gravity pulls the pendulum downward, while the applied torque changes its angular acceleration.
    </p>

    <div class="state-equation">
      \[
      s =
      \begin{bmatrix}
      \cos\theta \\
      \sin\theta \\
      \dot{\theta}
      \end{bmatrix},
      \qquad
      u = \tau
      \]
    </div>

  </div>

    </details>

    <div class="artifact-gallery">

  <div class="artifact-card">
    <video controls>
      <source
        src="/assets/videos/rl-video-episode-0-pendulum-shorter-training-time.mp4"
        type="video/mp4">
    </video>

    <h4>PPO · Shorter Training Run</h4>

    <p>
      An early PPO policy after a relatively short training run. The controller hasn't yet fully learned to use opposing torques to swing up and settle near the upright position.
    </p>
  </div>

  <div class="artifact-card">
    <video controls>
      <source
        src="/assets/videos/rl-video-episode-0-pendulum-longer-training-time.mp4"
        type="video/mp4">
    </video>

    <h4>PPO · Longer Training Run</h4>

    <p>
      Longer training alone in this case clearly resulted in a better policy and more successful control.
    </p>
  </div>

    </div>
  </section>

  <!-- =========================================================
      ACROBOT
  ========================================================== -->

  <section class="artifact-section">

    <div class="artifact-section-heading">
      <h2>Acrobot</h2>

  <p>
    This one is an underactuated system with two connected links but
    only one actuated joint, so the controller can't directly command the
    entire mechanism. Instead, it must exploit the coupled dynamics of the two links to build and redirect momentum rather than an immediate
      correction toward the target until the
    end of the outer link reaches the target height.
  </p>

    </div>

    <details class="dynamics-card">
      <summary>
        <div>
          <strong>Behind the environment</strong>
        </div>
      </summary>

  <div class="dynamics-content">
    <p>
      The state contains the angles and angular velocities of two connected
      links. Torque is applied only at the joint between them.
    </p>

    <div class="state-equation">
      \[
      s =
      \begin{bmatrix}
      \cos\theta_1 \\
      \sin\theta_1 \\
      \cos\theta_2 \\
      \sin\theta_2 \\
      \dot{\theta}_1 \\
      \dot{\theta}_2
      \end{bmatrix}
      \]
    </div>

  </div>

    </details>

    <div class="artifact-gallery">

  <div class="artifact-card">
    <video controls>
      <source
        src="/assets/videos/rl-video-episode-0-acrobat-ppo-shorter.mp4"
        type="video/mp4">
    </video>

    <h4>PPO · Shorter Training Run</h4>

    <p>
    Reaching the goal needs accumulating energy over time and the early PPO policy hasn't yet discovered a
      reliable momentum-building strategy.
    </p>
  </div>

  <div class="artifact-card">
    <video controls>
      <source
        src="/assets/videos/rl-video-episode-0-acrobat-ppo-longer.mp4"
        type="video/mp4">
    </video>

    <h4>PPO · Longer Training Run</h4>

    <p>
      Any improvement with simply longer training of PPO was limited, suggesting
      that training duration was not the only bottleneck and that algorithm
      settings or reward-guided exploration may need attention.
    </p>
  </div>

  <div class="artifact-card">
    <video controls>
      <source
        src="/assets/videos/rl-video-episode-0-acrobat-dqn.mp4"
        type="video/mp4">
    </video>

    <h4>DQN · Training Comparison</h4>

    <p>
      Also tested DQN as Acrobot has a discrete action space. The
      shorter and longer runs produced similarly unsuccesful behavior in this
      experiment, showing that simply increasing training time
      does not necessarily resolve the issue.
    </p>
  </div>

    </div>
  </section>

  <!-- =========================================================
      BIPEDAL WALKER
  ========================================================== -->

  <section class="artifact-section">

    <div class="artifact-section-heading">
      <h2>BipedalWalker</h2>

  <p>
    Compared with the previous environments, this one has much more complex dynamics. The policy must continuously control several
    joints, maintain balance, and move forward without
    falling. The dynamics also change whenever a foot makes or loses contact with the ground making it a more challenging control problem. 
  </p>

    </div>

    <details class="dynamics-card">
      <summary>
        <div>
          <strong>Behind the environment</strong>
        </div>
      </summary>

  <div class="dynamics-content">
    <p>
      Will investigate later :)
    </p>

  </div>

    </details>

    <div class="artifact-gallery">

  <div class="artifact-card">
    <video controls>
      <source
        src="/assets/videos/rl-video-episode-0-bipedal-ppo-shorter.mp4"
        type="video/mp4">
    </video>

    <h4>PPO · Shorter Training Run</h4>

    <p>
      The early PPO policy has not yet learned a stable strategy for balancing and moving forward.
    </p>
  </div>

  <div class="artifact-card">
    <video controls>
      <source
        src="/assets/videos/rl-video-episode-0-bipedal-ppo-longer.mp4"
        type="video/mp4">
    </video>

    <h4>PPO · Longer Training Run</h4>

    <p>
      More training of PPO improved balance, alternating
      leg motion, and forward progression.
    </p>
  </div>

  <div class="artifact-card">
    <video controls>
      <source
        src="/assets/videos/rl-video-episode-0-bipedal-sac-shorter.mp4"
        type="video/mp4">
    </video>

    <h4>SAC · Shorter Training Run</h4>

    <p>
      Also tested SAC as another continuous-control algorithm. This early run
      was similarly unsuccessful as PPO's short run.
    </p>
  </div>

  <div class="artifact-card">
    <video controls>
      <source
        src="/assets/videos/rl-video-episode-0-bipedal-sac-longer.mp4"
        type="video/mp4">
    </video>

    <h4>SAC · Longer Training Run</h4>

    <p>
    The longer SAC run was also moderately successful. Interestingly, it had learned a different strategy for moving forward than PPO. I also noticed that SAC took considerably longer to train, making it an interesting comparison between learning behavior and computational cost.
    </p>
  </div>

    </div>
  </section>

  <!-- =========================================================
      MOUNTAIN CAR
  ========================================================== -->

  <section class="artifact-section">

    <div class="artifact-section-heading">
      <h2>MountainCar</h2>

  <p>
    MountainCar looks simple at first, but the engine is intentionally too weak to drive directly up the hill. The controller must first move away from the goal, build momentum by oscillating between the slopes, and accumulate enough energy to eventually climb the hill. Tried a couple of things but couldn't make it work! Will revisit this one later!
  </p>

    </div>

    <details class="dynamics-card">
      <summary>
        <div>
          <strong>Behind the environment</strong>
        </div>
      </summary>

  <div class="dynamics-content">
    <p>
      The state includes only the car's position and velocity. However,
      the action has both an immediate effect from the engine and a
      position-dependent effect from the slope.
    </p>

    <div class="state-equation">
      \[
      s =
      \begin{bmatrix}
      x \\
      \dot{x}
      \end{bmatrix}
      \]
    </div>

  </div>

    </details>

    <div class="artifact-gallery">

  <div class="artifact-card">
    <video controls>
      <source
        src="/assets/videos/rl-video-episode-0-mountaincar-ppo-shorter.mp4"
        type="video/mp4">
    </video>

    <h4>PPO · Shorter Training Run</h4>

    <p>
      Unsuccessful!
    </p>
  </div>

  <div class="artifact-card">
    <video controls>
      <source
        src="/assets/videos/rl-video-episode-0-mountaincar-ppo-longer.mp4"
        type="video/mp4">
    </video>

    <h4>PPO · Longer Training Run</h4>

    <p>
      Still unsuccessful!
    </p>
  </div>

  <div class="artifact-card">
    <video controls>
      <source
        src="/assets/videos/rl-video-episode-0-mountaincar-dqn-shorter.mp4"
        type="video/mp4">
    </video>

    <h4>DQN · Shorter Training Run</h4>

    <p>
      Unsuccessful!
    </p>
  </div>

  <div class="artifact-card">
    <video controls>
      <source
        src="/assets/videos/rl-video-episode-0-mountaincar-dqn-longer.mp4"
        type="video/mp4">
    </video>

    <h4>DQN · Longer Training Run</h4>

    <p>
      Still unsuccessful!
    </p>
  </div>

    </div>
  </section>
