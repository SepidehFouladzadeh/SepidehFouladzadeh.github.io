---
layout: exploration
title: "Designing environments for my own curiosity"
description: "Going beyond standard environments in Gymnasium to explore how RL might intersect with problems I'm personally curious about."
date: 2026-07-19
# reading_time: "1 min read"
linkedin_url: "https://www.linkedin.com/in/sepideh-fouladzadeh/"
permalink: /research/rl-vs-control/custom-environment/
back_url: /research/rl-vs-control/
back_text: Back to where this began
---

<section class="artifact-detail">

  <!-- =========================================================
       INTRODUCTION
  ========================================================== -->

  <header class="artifact-introduction">
    <p class="artifact-label">
      Hypothesis simulator · Reinforcement learning
    </p>

    <h2>A PhD Research Allocation Environment</h2>

    <p class="artifact-lead">
      What behavior emerges when an agent is asked to balance
      progress, learning, uncertainty reduction, deadlines,
      health, and recovery?
    </p>

    <p class="artifact-context">
      In this simulation, one step represents one week. A PPO agent
      allocates its weekly effort among literature review,
      implementation, result analysis, result communication,
      and recovery.
    </p>
  </header>


  <!-- =========================================================
       VIDEO
  ========================================================== -->

  <div class="artifact-video">
    <video controls preload="metadata">
      <source
        src="/assets/videos/phd_env.mp4"
        type="video/mp4"
      >

      Your browser does not support the video element.
    </video>

    <p class="artifact-caption">
      One simulated year. The upper chart shows the evolving state
      of the research process, while the lower chart shows the
      agent’s weekly effort allocation.
    </p>
  </div>


  <!-- =========================================================
       IMPORTANT FRAMING
  ========================================================== -->

  <aside class="artifact-note">
    <strong>This is a hypothesis simulator.</strong>

    <p>
      The agent is not learning from real data about PhD students.
      It is learning how to behave inside a simplified environment
      whose relationships, constraints, and values I explicitly
      designed.
    </p>
  </aside>


  <!-- =========================================================
       REWARD
  ========================================================== -->

  <section class="artifact-section">
    <div class="section-heading">
      <p class="section-number">01</p>

      <div>
        <h3>What is the agent optimizing?</h3>

        <p>
          The reward function defines what the environment considers
          a desirable outcome. It rewards meaningful and sustainable
          research development rather than progress alone.
        </p>
      </div>
    </div>


    <div class="reward-summary">

      <div class="reward-column reward-positive">
        <h4>Encouraged</h4>

        <ul>
          <li>Research progress</li>
          <li>Knowledge gain</li>
          <li>Reduction of research uncertainty</li>
          <li>Completion with preserved health and energy</li>
          <li>Useful analysis and communication</li>
        </ul>
      </div>

      <div class="reward-column reward-negative">
        <h4>Discouraged</h4>

        <ul>
          <li>Health deterioration</li>
          <li>Persistently low energy</li>
          <li>Overwork during life instability</li>
          <li>Increasing deadline pressure</li>
          <li>Poorly timed or wasted effort</li>
        </ul>
      </div>

    </div>


    <div class="equation-card">
      <p class="equation-title">Conceptual reward</p>

      <div class="reward-equation">
        <span class="equation-main">
          Reward
        </span>

        <span class="equation-symbol">=</span>

        <span class="equation-positive">
          progress
          + knowledge
          + information
        </span>

        <span class="equation-negative">
          − health damage
          − low energy
          − deadline pressure
          − wasted effort
        </span>

        <span class="equation-bonus">
          + completion bonuses
        </span>
      </div>
    </div>


    <div class="priority-block">
      <h4>Default reward priorities</h4>

      <p>
        These weights express the relative values encoded in the
        environment. They are not literal percentages of the reward
        received during every week because each reward component also
        has its own scale and condition.
      </p>

      <div class="priority-list">

        <div class="priority-item">
          <div class="priority-label">
            <span>Research progress</span>
            <span>30%</span>
          </div>

          <div class="priority-track">
            <div
              class="priority-fill"
              style="width: 30%;"
            ></div>
          </div>
        </div>

        <div class="priority-item">
          <div class="priority-label">
            <span>Health and sustainability</span>
            <span>28%</span>
          </div>

          <div class="priority-track">
            <div
              class="priority-fill"
              style="width: 28%;"
            ></div>
          </div>
        </div>

        <div class="priority-item">
          <div class="priority-label">
            <span>Research information</span>
            <span>20%</span>
          </div>

          <div class="priority-track">
            <div
              class="priority-fill"
              style="width: 20%;"
            ></div>
          </div>
        </div>

        <div class="priority-item">
          <div class="priority-label">
            <span>Knowledge</span>
            <span>12%</span>
          </div>

          <div class="priority-track">
            <div
              class="priority-fill"
              style="width: 12%;"
            ></div>
          </div>
        </div>

        <div class="priority-item">
          <div class="priority-label">
            <span>Deadline responsiveness</span>
            <span>10%</span>
          </div>

          <div class="priority-track">
            <div
              class="priority-fill"
              style="width: 10%;"
            ></div>
          </div>
        </div>

      </div>
    </div>


    <blockquote class="interpretation-quote">
      The reward encodes a value judgment: research progress matters,
      but progress achieved through health collapse or chronically
      unsustainable effort should not be treated as equally successful.
    </blockquote>
  </section>


  <!-- =========================================================
       HYPOTHESIS / CAUSAL STRUCTURE
  ========================================================== -->

  <section class="artifact-section">
    <div class="section-heading">
      <p class="section-number">02</p>

      <div>
        <h3>What hypothesis defines the environment?</h3>

        <p>
          The transition equations describe how the simulated world
          works. Each arrow below represents an assumed influence,
          not an established empirical fact.
        </p>
      </div>
    </div>


    <div class="hypothesis-legend">
      <span>
        <span class="legend-line"></span>
        Assumed influence
      </span>

      <span>
        <span class="legend-node"></span>
        State or process
      </span>
    </div>


    <div class="hypothesis-diagram">

      <!-- Capacity row -->

      <div class="diagram-row diagram-row-three">

        <div class="diagram-node">
          <span class="node-category">State</span>
          <strong>Energy</strong>
        </div>

        <div class="diagram-arrow">
          <span>contributes to</span>
          <span class="arrow-symbol">→</span>
        </div>

        <div class="diagram-node diagram-node-highlight">
          <span class="node-category">Derived condition</span>
          <strong>Effective capacity</strong>
        </div>

      </div>


      <div class="diagram-row diagram-row-three">

        <div class="diagram-node">
          <span class="node-category">State</span>
          <strong>Health</strong>
        </div>

        <div class="diagram-arrow">
          <span>contributes to</span>
          <span class="arrow-symbol">→</span>
        </div>

        <div class="diagram-node diagram-node-highlight">
          <span class="node-category">Moderated by</span>
          <strong>Life stability</strong>
          <small>1 − life uncertainty</small>
        </div>

      </div>


      <!-- Direction quality -->

      <div class="diagram-divider">
        <span>Research direction</span>
      </div>


      <div class="diagram-inputs">

        <div class="diagram-node">
          <span class="node-category">State</span>
          <strong>Knowledge</strong>
        </div>

        <div class="diagram-node">
          <span class="node-category">State</span>
          <strong>Feedback clarity</strong>
        </div>

        <div class="diagram-node">
          <span class="node-category">State</span>
          <strong>Lower research uncertainty</strong>
        </div>

      </div>

      <div class="diagram-down-arrow">
        <span>jointly shape</span>
        <span>↓</span>
      </div>

      <div class="diagram-center-node">
        <div class="diagram-node diagram-node-highlight">
          <span class="node-category">Derived condition</span>
          <strong>Direction quality</strong>
        </div>
      </div>


      <!-- Research pipeline -->

      <div class="diagram-divider">
        <span>Research process</span>
      </div>


      <div class="research-pipeline">

        <div class="pipeline-stage">
          <div class="diagram-node">
            <span class="node-category">Action</span>
            <strong>Literature review</strong>
          </div>

          <span class="pipeline-arrow">→</span>

          <div class="diagram-node">
            <span class="node-category">State change</span>
            <strong>Knowledge</strong>
            <small>and uncertainty</small>
          </div>
        </div>


        <div class="pipeline-stage">
          <div class="diagram-node">
            <span class="node-category">Action</span>
            <strong>Implementation</strong>
          </div>

          <span class="pipeline-arrow">→</span>

          <div class="diagram-node">
            <span class="node-category">State change</span>
            <strong>Available results</strong>
            <small>and progress</small>
          </div>
        </div>


        <div class="pipeline-stage">
          <div class="diagram-node">
            <span class="node-category">Action</span>
            <strong>Result analysis</strong>
          </div>

          <span class="pipeline-arrow">→</span>

          <div class="diagram-node">
            <span class="node-category">State change</span>
            <strong>Information gain</strong>
            <small>and uncertainty reduction</small>
          </div>
        </div>

      </div>


      <!-- Feedback loop -->

      <div class="diagram-divider">
        <span>Communication feedback loop</span>
      </div>


      <div class="feedback-loop">

        <div class="diagram-node">
          <span class="node-category">Readiness</span>
          <strong>
            Progress + knowledge + lower uncertainty
          </strong>
        </div>

        <span class="pipeline-arrow">→</span>

        <div class="diagram-node">
          <span class="node-category">Action</span>
          <strong>Result communication</strong>
        </div>

        <span class="pipeline-arrow">→</span>

        <div class="diagram-node">
          <span class="node-category">Future conditions</span>
          <strong>Clarity and support</strong>
        </div>

      </div>


      <!-- Sustainability loop -->

      <div class="diagram-divider">
        <span>Sustainability feedback loop</span>
      </div>


      <div class="feedback-loop">

        <div class="diagram-node">
          <span class="node-category">Demand</span>
          <strong>Research workload</strong>
        </div>

        <span class="pipeline-arrow">→</span>

        <div class="diagram-node">
          <span class="node-category">Possible cost</span>
          <strong>Energy and health loss</strong>
        </div>

        <span class="pipeline-arrow">↔</span>

        <div class="diagram-node">
          <span class="node-category">Balancing action</span>
          <strong>Recovery</strong>
        </div>

      </div>

    </div>


    <p class="diagram-caption">
      The model assumes that the value of an action depends on context.
      For example, implementation is more productive when the agent has
      sufficient capacity and a clearer research direction, while analysis
      is only useful when results are available.
    </p>
  </section>


  <!-- =========================================================
       ACTION ASSUMPTIONS
  ========================================================== -->

  <section class="artifact-section">
    <div class="section-heading">
      <p class="section-number">03</p>

      <div>
        <h3>What does each action assume?</h3>

        <p>
          Open each action to see the relationships encoded in the
          environment.
        </p>
      </div>
    </div>


    <div class="action-assumptions">

      <!-- Literature -->

      <details class="action-detail">
        <summary>
          <span class="action-number">01</span>

          <span class="action-summary-text">
            <strong>Literature review</strong>
            <small>
              Builds knowledge and changes perceived uncertainty
            </small>
          </span>

          <span class="detail-icon" aria-hidden="true">+</span>
        </summary>

        <div class="action-content">
          <div class="action-effects">
            <span>↑ Knowledge</span>
            <span>↓ Research uncertainty</span>
            <span>↑ Newly revealed unknowns</span>
          </div>

          <p>
            Literature review is assumed to increase knowledge,
            particularly when knowledge is still limited. It can reduce
            research uncertainty, but early reading may also reveal
            unknown unknowns and temporarily make the project feel less
            clear.
          </p>

          <p>
            Allocating more than approximately 65% of weekly effort to
            literature review is treated as possible overuse and receives
            a wasted-effort penalty.
          </p>
        </div>
      </details>


      <!-- Implementation -->

      <details class="action-detail">
        <summary>
          <span class="action-number">02</span>

          <span class="action-summary-text">
            <strong>Implementation</strong>
            <small>
              Converts direction and capacity into progress and results
            </small>
          </span>

          <span class="detail-icon" aria-hidden="true">+</span>
        </summary>

        <div class="action-content">
          <div class="action-effects">
            <span>↑ Research progress</span>
            <span>↑ Available results</span>
            <span>↑ Confusion when underprepared</span>
          </div>

          <p>
            Implementation is assumed to be more productive when the
            agent has sufficient energy, health, knowledge, feedback
            clarity, and a relatively clear research direction.
          </p>

          <p>
            Implementation performed with very limited knowledge can
            increase research uncertainty through confusion or poorly
            directed work.
          </p>
        </div>
      </details>


      <!-- Analysis -->

      <details class="action-detail">
        <summary>
          <span class="action-number">03</span>

          <span class="action-summary-text">
            <strong>Result analysis</strong>
            <small>
              Converts available results into information
            </small>
          </span>

          <span class="detail-icon" aria-hidden="true">+</span>
        </summary>

        <div class="action-content">
          <div class="action-effects">
            <span>↑ Information gain</span>
            <span>↑ Research progress</span>
            <span>↓ Research uncertainty</span>
            <span>↓ Unprocessed results</span>
          </div>

          <p>
            Analysis requires available results. The amount that can be
            analyzed in one week is limited by both the analysis effort
            and the amount of existing results.
          </p>

          <p>
            Analysis becomes more informative when knowledge is higher
            and when there is still meaningful research uncertainty to
            resolve. Analysis effort without sufficient results is
            penalized.
          </p>
        </div>
      </details>


      <!-- Communication -->

      <details class="action-detail">
        <summary>
          <span class="action-number">04</span>

          <span class="action-summary-text">
            <strong>Result communication</strong>
            <small>
              Creates feedback, clarity, support, and possible redirection
            </small>
          </span>

          <span class="detail-icon" aria-hidden="true">+</span>
        </summary>

        <div class="action-content">
          <div class="action-effects">
            <span>↑ Feedback clarity</span>
            <span>↑ Professional support</span>
            <span>↓ Research uncertainty</span>
            <span>↻ Possible redirection</span>
          </div>

          <p>
            Communication readiness depends on research progress,
            knowledge, and uncertainty. Communicating meaningful work is
            assumed to improve clarity and may indirectly strengthen
            professional support.
          </p>

          <p>
            Communication can also reveal that part of the current
            direction should be revised. In the simulation, this may
            reduce a small amount of accumulated progress while producing
            useful information.
          </p>

          <p>
            Communicating before the work is sufficiently ready receives
            a premature-communication penalty.
          </p>
        </div>
      </details>


      <!-- Recovery -->

      <details class="action-detail">
        <summary>
          <span class="action-number">05</span>

          <span class="action-summary-text">
            <strong>Recovery</strong>
            <small>
              Restores the capacity required for future work
            </small>
          </span>

          <span class="detail-icon" aria-hidden="true">+</span>
        </summary>

        <div class="action-content">
          <div class="action-effects">
            <span>↑ Energy</span>
            <span>↑ Health</span>
            <span>↓ Risk of overload</span>
          </div>

          <p>
            Recovery does not directly generate research progress.
            Instead, it restores energy and health and reduces the risk
            that a demanding workload will become damaging.
          </p>

          <p>
            Recovery is assumed to be more effective when baseline
            health is stronger and life uncertainty is lower.
          </p>
        </div>
      </details>

    </div>
  </section>


  <!-- =========================================================
       STATE DEFINITIONS
  ========================================================== -->

  <section class="artifact-section">
    <div class="section-heading">
      <p class="section-number">04</p>

      <div>
        <h3>What can the agent observe?</h3>

        <p>
          The policy receives eleven normalized state values between
          zero and one.
        </p>
      </div>
    </div>


    <div class="state-grid">

      <div class="state-card">
        <strong>Research progress</strong>
        <p>Accumulated development toward the research objective.</p>
      </div>

      <div class="state-card">
        <strong>Knowledge</strong>
        <p>
          The modeled understanding available to guide research work.
        </p>
      </div>

      <div class="state-card">
        <strong>Research uncertainty</strong>
        <p>
          Uncertainty about the project’s direction and interpretation.
        </p>
      </div>

      <div class="state-card">
        <strong>Life uncertainty</strong>
        <p>
          External instability that can reduce effective work capacity.
        </p>
      </div>

      <div class="state-card">
        <strong>Energy</strong>
        <p>
          Shorter-term capacity available for effort during the week.
        </p>
      </div>

      <div class="state-card">
        <strong>Health</strong>
        <p>
          A slower-changing measure of physical sustainability.
        </p>
      </div>

      <div class="state-card">
        <strong>Deadline pressure</strong>
        <p>
          Pressure that grows with time and incomplete progress.
        </p>
      </div>

      <div class="state-card">
        <strong>Feedback clarity</strong>
        <p>
          The degree to which external feedback clarifies direction.
        </p>
      </div>

      <div class="state-card">
        <strong>Professional support</strong>
        <p>
          Access to support that can buffer some uncertainty.
        </p>
      </div>

      <div class="state-card">
        <strong>Available results</strong>
        <p>
          Results that have been generated but remain available for
          analysis.
        </p>
      </div>

      <div class="state-card">
        <strong>Remaining time</strong>
        <p>
          The fraction of the simulated year remaining.
        </p>
      </div>

    </div>
  </section>


  <!-- =========================================================
       INTERPRETATION
  ========================================================== -->

  <section class="artifact-section">
    <div class="section-heading">
      <p class="section-number">05</p>

      <div>
        <h3>How should the result be interpreted?</h3>

        <p>
          The learned policy is a consequence of the model, not an
          independently discovered truth about research.
        </p>
      </div>
    </div>


    <div class="limitations-box">
      <h4>Interpretation boundary</h4>

      <p>
        This environment is not a validated model of doctoral research,
        and its learned policy should not be interpreted as personal or
        professional advice.
      </p>

      <p>
        The behavior reflects the transition equations, reward
        priorities, random disturbances, initial conditions, and state
        definitions chosen for the simulation.
      </p>

      <p>
        Its purpose is to make those assumptions inspectable and to
        explore what kinds of behavior they produce.
      </p>
    </div>


    <div class="interpretation-points">

      <article>
        <h4>Actions represent a fixed effort budget</h4>

        <p>
          The five action values are converted into nonnegative effort
          fractions that sum to one. Increasing effort in one activity
          necessarily reduces the fraction available to the others.
        </p>
      </article>

      <article>
        <h4>Relationships are hypotheses</h4>

        <p>
          Statements such as “knowledge improves implementation” or
          “recovery restores capacity” are modeling assumptions encoded
          in equations, not conclusions learned from empirical data.
        </p>
      </article>

      <article>
        <h4>Randomness represents unmodeled variation</h4>

        <p>
          Literature, implementation, analysis, feedback, redirection,
          and life uncertainty include random variation, so identical
          allocations do not always produce identical trajectories.
        </p>
      </article>

      <article>
        <h4>The objective determines the behavior</h4>

        <p>
          Changing the reward weights or penalties can produce a
          different policy even when the transition equations remain
          unchanged.
        </p>
      </article>

    </div>
  </section>


  <!-- =========================================================
       FINAL FRAMING
  ========================================================== -->

  <footer class="artifact-conclusion">
    <p>
      Rather than asking whether reinforcement learning can discover
      the correct way to conduct a PhD, this exploration asks a different
      question:
    </p>

    <strong>
      What behavior emerges after beliefs about research are translated
      into states, actions, transition equations, and values?
    </strong>
  </footer>

</section>