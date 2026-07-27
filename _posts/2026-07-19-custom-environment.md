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

A hypothetical environment in which a researcher allocates weekly effort among literature review, implementation, result analysis, result communication, and recovery while optimizing for meaningful and sustainable research development :)

Below you can see how the research process evolves alongside weekly effort allocation over one year.

  <div class="artifact-video">
    <video controls preload="metadata">
      <source
        src="/assets/videos/phd_env.mp4"
        type="video/mp4"
      >

      Your browser does not support the video element.
    </video>

  </div>

  For simplicity, activities outside research are not modeled explicitly. Instead, their overall influence is approximated through the recovery action, assuming the primary focus during this simulated period is research :)

  <!-- =========================================================
       REWARD
  ========================================================== -->

  <section class="artifact-section">

    <div class="equation-card">
      <p class="equation-title">My Conceptual Reward</p>

      <div class="reward-equation">

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
      <h4>Reward priorities</h4>

      <p>
        Weights expressing the relative values encoded in the
        environment (not literal percentages of the reward
        received during every week because each reward component also
        has its own scale and condition)
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
        The desirable outcome is research progress, but not through health collapse or chronically unsustainable effort. Rewarding meaningful and sustainable research development rather than progress alone :)
    </blockquote>
  </section>

  <!-- =========================================================
       HYPOTHESIS / CAUSAL STRUCTURE
  ========================================================== -->

  <section class="artifact-section">
    <p>
    Below are my assumtions about the world through the transition equations describing the environment that agent learns within. (simply a hypothesis about the underlying causal relationships and not based established empirical fact)
    </p>

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

      <div>
        <h3>Actions</h3>

        <p>
          Along with the relationships encoded in the
          environment.
        </p>
      </div>
    </div>


    <div class="action-assumptions">

      <!-- Literature -->

      <details class="action-detail">
        <summary>

          <span class="action-summary-text">
            <strong>Literature review</strong>
            <small>
              Builds knowledge and changes perceived uncertainty about the project
            </small>
          </span>

          <span class="detail-icon" aria-hidden="true">+</span>
        </summary>

        <div class="action-content">
          <div class="action-effects">
            <span>↑ Gained knowledge</span>
            <span>↓ Research uncertainty</span>
            <span>↑ Newly revealed unknowns</span>
          </div>

          <p>
            Literature review is assumed to increase knowledge,
            particularly when knowledge is still limited (early stages of the research). It can reduce
            research uncertainty, but in early stages it may also reveal
            more unknown layers of complexity and temporarily make the project feel less
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

      <div>
        <h3>Observations</h3>

        <p>
          Normalized state values between
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
          The understanding available to guide research work.
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
          The fraction of the simulated time remaining.
        </p>
      </div>

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
        definitions chosen for the simulation.
      </p>

      <p>
        The purpose is to make those assumptions inspectable and to
        explore what kinds of behavior they produce.
      </p>
    </div>

  </section>