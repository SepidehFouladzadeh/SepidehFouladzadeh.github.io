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
            <span>↑ Knowledge</span>
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
        <h3>State and observation</h3>

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
       HYPOTHESIS / CAUSAL STRUCTURE
  ========================================================== -->

  <section class="artifact-section">

    <div class="section-heading">
        <div>
        <h3>Assumptions defining the environment</h3>

        <p>
            Transition equations describing how the current state and weekly effort allocation are assumed to shape the following week.
        <p>
        <p>
            x<sub>t+1</sub> = f(x<sub>t</sub>, a<sub>t</sub>, noise)
        </p>
        <p>
        where <em>x</em> represents the research state and <em>a</em>
        represents the weekly effort allocation.
        </p>


    <div class="assumption-list">

        <!-- EFFECTIVE CAPACITY -->

        <article class="assumption-card">

        <div class="assumption-heading">

            <div>
            <h4>Effective capacity</h4>
            <p>
                Energy, health, and life stability jointly determine how
                effectively effort can be converted into work.
            </p>
            </div>
        </div>

        <div class="assumption-equation">
            capacity
            =
            energy
            ×
            health
            ×
            (1 − life uncertainty)
        </div>

        <div class="assumption-meaning">
            <strong>Assumption</strong>

            <p>
            Low energy, reduced health, or greater life uncertainty lowers
            the effectiveness of all research activities, even when the same
            amount of effort is allocated.
            </p>
        </div>

        </article>


        <!-- DIRECTION QUALITY -->

        <article class="assumption-card">

        <div class="assumption-heading">

            <div>
            <h4>Research direction quality</h4>
            <p>
                Knowledge, feedback, and lower uncertainty are assumed to make
                research effort better directed.
            </p>
            </div>
        </div>


        <div class="assumption-equation">
            direction quality
            =
            knowledge
            × feedback clarity
            × (1 − research uncertainty)
        </div>

        <div class="assumption-meaning">
            <strong>Assumption</strong>

            <p>
            Implementation is more productive when the researcher has more
            relevant knowledge, clearer feedback, and less uncertainty about
            the research direction.
            </p>
        </div>

        </article>


        <!-- KNOWLEDGE -->

        <article class="assumption-card">

        <div class="assumption-heading">

            <div>
            <h4>Knowledge development</h4>
            <p>
                Literature review converts effort and capacity into additional
                knowledge.
            </p>
            </div>
        </div>

        <div class="assumption-equation">

            knowledge next week
            =
            knowledge this week
            +
            literature effort
            × effective capacity
            × (1 − current knowledge)
        </div>

        <div class="assumption-meaning">
            <strong>Assumption</strong>

            <p>
            Literature review increases knowledge, but the gain gradually
            saturates as knowledge becomes higher. Random variation represents
            differences in the usefulness of what is read each week.
            </p>
        </div>

        </article>


        <!-- IMPLEMENTATION AND PROGRESS -->

        <article class="assumption-card">

        <div class="assumption-heading">

            <div>
            <h4>Research progress</h4>
            <p>
                Implementation converts effort, capacity, and direction quality
                into progress.
            </p>
            </div>
        </div>

        <div class="assumption-equation">

            research progress next week
            =
            research progress this week
            +
            implementation effort
            × effective capacity
            × direction quality
        </div>

        <div class="assumption-meaning">
            <strong>Assumption</strong>

            <p>
            The same implementation effort produces less progress when
            capacity is limited or the research direction is unclear.
            </p>
        </div>

        </article>


        <!-- RESULTS -->

        <article class="assumption-card">

        <div class="assumption-heading">

            <div>
            <h4>Available results</h4>
            <p>
                Implementation generates results, while analysis consumes them.
            </p>
            </div>
        </div>

        <div class="assumption-equation">
            R<sub>t+1</sub>
            =
            R<sub>t</sub>
            +
            γ ·
            a<sup>implementation</sup><sub>t</sub>
            · C<sub>t</sub>
            −
            δ ·
            a<sup>analysis</sup><sub>t</sub>
        </div>

        <div class="assumption-meaning">
            <strong>Assumption</strong>

            <p>
            Implementation produces material that can later be analyzed.
            Analysis is only productive when sufficient results are available.
            </p>
        </div>

        </article>


        <!-- INFORMATION -->

        <article class="assumption-card">

        <div class="assumption-heading">

            <div>
            <h4>Information gain through analysis</h4>
            <p>
                Analysis converts available results into interpretable
                information.
            </p>
            </div>
        </div>

        <div class="assumption-equation">
            information gain
            =
            analyzed results
            × knowledge
            × research uncertainty
            × random effectiveness
        </div>

        <div class="assumption-meaning">
            <strong>Assumption</strong>

            <p>
            Information gain is constrained by both the available results and
            the effort allocated to analysis. Greater knowledge improves the
            ability to interpret those results.
            </p>
        </div>

        </article>


        <!-- RESEARCH UNCERTAINTY -->

        <article class="assumption-card">

        <div class="assumption-heading">

            <div>
            <h4>Research uncertainty</h4>
            <p>
                Reading, analysis, and communication may reduce uncertainty,
                while poorly directed implementation may increase it.
            </p>
            </div>
        </div>

        <div class="assumption-equation">
            U<sup>research</sup><sub>t+1</sub>
            =
            U<sup>research</sup><sub>t</sub>
            −
            λ<sub>1</sub>I<sub>t</sub>
            −
            λ<sub>2</sub>a<sup>literature</sup><sub>t</sub>
            −
            λ<sub>3</sub>a<sup>communication</sup><sub>t</sub>
            +
            λ<sub>4</sub>Confusion<sub>t</sub>
        </div>

        <div class="assumption-meaning">
            <strong>Assumption</strong>

            <p>
            Research uncertainty falls through useful information and external
            feedback, but implementation undertaken with insufficient knowledge
            or direction may generate additional confusion.
            </p>
        </div>

        </article>


        <!-- COMMUNICATION -->

        <article class="assumption-card">

        <div class="assumption-heading">

            <div>
            <h4>Communication and feedback</h4>
            <p>
                Communicating sufficiently developed work is assumed to increase
                feedback clarity and professional support.
            </p>
            </div>
        </div>

        <div class="assumption-equation">
            F<sub>t+1</sub>
            =
            F<sub>t</sub>
            +
            μ ·
            a<sup>communication</sup><sub>t</sub>
            · Readiness<sub>t</sub>
        </div>

        <div class="assumption-equation assumption-equation-secondary">
            Readiness<sub>t</sub>
            =
            f(
            P<sub>t</sub>,
            K<sub>t</sub>,
            1 − U<sup>research</sup><sub>t</sub>
            )
        </div>

        <div class="assumption-meaning">
            <strong>Assumption</strong>

            <p>
            Communication is more useful after sufficient progress and
            understanding have developed. Premature communication produces
            less useful feedback.
            </p>
        </div>

        </article>


        <!-- ENERGY -->

        <article class="assumption-card">

        <div class="assumption-heading">
            <span class="assumption-number">09</span>

            <div>
            <h4>Energy dynamics</h4>
            <p>
                Research effort consumes energy, while recovery restores it.
            </p>
            </div>
        </div>

        <div class="assumption-equation">
            energy next week
            =
            energy this week
            −
            workload
            +
            recovery effort
            × health
            × (1 − life uncertainty)
        </div>

        <div class="assumption-meaning">
            <strong>Assumption</strong>

            <p>
            Recovery replenishes energy, but it is less effective when health
            is poor or life uncertainty is high.
            </p>
        </div>

        </article>


        <!-- HEALTH -->

        <article class="assumption-card">

        <div class="assumption-heading">
            <span class="assumption-number">10</span>

            <div>
            <h4>Health dynamics</h4>
            <p>
                Sustained overload may reduce health, while recovery supports
                gradual restoration.
            </p>
            </div>
        </div>

        <div class="assumption-equation">
            health next week
            =
            health this week
            − overload damage
            + recovery gain
        </div>

        <div class="assumption-meaning">
            <strong>Assumption</strong>

            <p>
            Health changes more slowly than energy. Occasional demanding weeks
            may be manageable, but repeated overload without recovery produces
            cumulative deterioration.
            </p>
        </div>

        </article>


        <!-- DEADLINE -->

        <article class="assumption-card">

        <div class="assumption-heading">

            <div>
            <h4>Deadline pressure</h4>
            <p>
                Pressure grows as time passes while meaningful progress remains
                incomplete.
            </p>
            </div>
        </div>

        <div class="assumption-equation">
            deadline pressure
            =
            elapsed time
            × incomplete progress
        </div>

        <div class="assumption-meaning">
            <strong>Assumption</strong>

            <p>
            Deadline pressure is highest when little time remains and research
            progress is still low.
            </p>
        </div>

        </article>

    </div>

</section>


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