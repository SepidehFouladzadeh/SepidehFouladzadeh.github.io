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

  <section class="model-section">

  <div class="section-heading">
    <h2>How I assume the research process works</h2>

    <p>
      The diagram shows the relationships encoded in the environment.
      Select any card to read the corresponding modeling assumption.
    </p>
  </div>

  <div class="model-diagram" data-model-diagram>

    <!-- SVG connectors -->
    <svg
      class="model-connectors"
      aria-hidden="true"
      preserveAspectRatio="none"
    >
      <defs>
        <marker
          id="arrowhead"
          markerWidth="8"
          markerHeight="8"
          refX="7"
          refY="4"
          orient="auto"
        >
          <path d="M0,0 L8,4 L0,8 Z"></path>
        </marker>
      </defs>

      <path
        data-from="recovery"
        data-to="capacity"
      ></path>

      <path
        data-from="capacity"
        data-to="literature"
      ></path>

      <path
        data-from="capacity"
        data-to="implementation"
      ></path>

      <path
        data-from="literature"
        data-to="knowledge"
      ></path>

      <path
        data-from="knowledge"
        data-to="implementation"
      ></path>

      <path
        data-from="implementation"
        data-to="progress"
      ></path>

      <path
        data-from="progress"
        data-to="communication"
      ></path>

      <path
        data-from="knowledge"
        data-to="communication"
      ></path>

      <path
        data-from="communication"
        data-to="support"
      ></path>

      <path
        data-from="deadline"
        data-to="implementation"
      ></path>

      <path
        data-from="progress"
        data-to="deadline"
        data-direction="reverse"
      ></path>
    </svg>


    <!-- ROW 1 -->

    <article
      class="model-card state-card diagram-deadline"
      id="deadline"
    >
      <button
        class="model-card-trigger"
        type="button"
        aria-expanded="false"
        aria-controls="details-deadline"
      >
        <span class="model-card-type">State</span>

        <strong>Deadline pressure</strong>

        <p>
          Pressure associated with passing time and incomplete work.
        </p>

        <span class="model-card-more">
          View assumption
        </span>
      </button>

      <div
        class="model-card-details"
        id="details-deadline"
        hidden
      >
        <p>
          Deadline pressure grows over time and rises more quickly when
          visible progress remains limited.
        </p>

        <p>
          In the model, pressure can temporarily increase focus on work
          directly related to understanding and completing the project.
        </p>
      </div>
    </article>


    <!-- ROW 2 -->

    <article
      class="model-card action-card diagram-recovery"
      id="recovery"
    >
      <button
        class="model-card-trigger"
        type="button"
        aria-expanded="false"
        aria-controls="details-recovery"
      >
        <span class="model-card-type">Action</span>

        <strong>Recovery</strong>

        <p>
          Effort allocated to restoring sustainable working capacity.
        </p>

        <span class="model-card-more">
          View assumption
        </span>
      </button>

      <div
        class="model-card-details"
        id="details-recovery"
        hidden
      >
        <p>
          Recovery increases capacity with diminishing returns. It does
          not directly produce visible research progress.
        </p>

        <div class="model-equation">
          recovery → higher capacity
        </div>
      </div>
    </article>


    <article
      class="model-card state-card diagram-capacity"
      id="capacity"
    >
      <button
        class="model-card-trigger"
        type="button"
        aria-expanded="false"
        aria-controls="details-capacity"
      >
        <span class="model-card-type">State</span>

        <strong>Capacity</strong>

        <p>
          The ability to work effectively during the current week.
        </p>

        <span class="model-card-more">
          View assumption
        </span>
      </button>

      <div
        class="model-card-details"
        id="details-capacity"
        hidden
      >
        <p>
          Higher capacity makes literature review and implementation
          more effective.
        </p>

        <p>
          Workload only reduces capacity when it exceeds the level
          treated as sustainable in the environment.
        </p>
      </div>
    </article>


    <article
      class="model-card state-card diagram-support"
      id="support"
    >
      <button
        class="model-card-trigger"
        type="button"
        aria-expanded="false"
        aria-controls="details-support"
      >
        <span class="model-card-type">State</span>

        <strong>Support</strong>

        <p>
          Access to professional support and useful external input.
        </p>

        <span class="model-card-more">
          View assumption
        </span>
      </button>

      <div
        class="model-card-details"
        id="details-support"
        hidden
      >
        <p>
          Meaningful result communication is assumed to gradually
          increase professional support.
        </p>

        <p>
          Support also makes a small contribution to learning.
        </p>
      </div>
    </article>


    <!-- ROW 3 -->

    <article
      class="model-card action-card diagram-literature"
      id="literature"
    >
      <button
        class="model-card-trigger"
        type="button"
        aria-expanded="false"
        aria-controls="details-literature"
      >
        <span class="model-card-type">Action</span>

        <strong>Literature review</strong>

        <p>
          Effort allocated to building understanding.
        </p>

        <span class="model-card-more">
          View assumption
        </span>
      </button>

      <div
        class="model-card-details"
        id="details-literature"
        hidden
      >
        <p>
          Literature review increases knowledge. The gain is greater
          when current knowledge is still limited.
        </p>

        <div class="model-equation">
          literature × capacity × remaining learning potential
        </div>
      </div>
    </article>


    <article
      class="model-card state-card diagram-knowledge"
      id="knowledge"
    >
      <button
        class="model-card-trigger"
        type="button"
        aria-expanded="false"
        aria-controls="details-knowledge"
      >
        <span class="model-card-type">State</span>

        <strong>Knowledge</strong>

        <p>
          The understanding available to guide research work.
        </p>

        <span class="model-card-more">
          View assumption
        </span>
      </button>

      <div
        class="model-card-details"
        id="details-knowledge"
        hidden
      >
        <p>
          Knowledge grows through literature review, learning by doing,
          and a smaller contribution from support.
        </p>

        <p>
          Higher knowledge improves the productivity of implementation
          and the readiness to communicate results.
        </p>
      </div>
    </article>


    <article
      class="model-card action-card diagram-implementation"
      id="implementation"
    >
      <button
        class="model-card-trigger"
        type="button"
        aria-expanded="false"
        aria-controls="details-implementation"
      >
        <span class="model-card-type">Action</span>

        <strong>Implementation</strong>

        <p>
          Effort allocated to turning understanding into developed work.
        </p>

        <span class="model-card-more">
          View assumption
        </span>
      </button>

      <div
        class="model-card-details"
        id="details-implementation"
        hidden
      >
        <p>
          Implementation produces more progress when capacity and
          knowledge are higher.
        </p>

        <div class="model-equation">
          implementation × capacity × knowledge → progress
        </div>
      </div>
    </article>


    <!-- ROW 4 -->

    <article
      class="model-card action-card diagram-communication"
      id="communication"
    >
      <button
        class="model-card-trigger"
        type="button"
        aria-expanded="false"
        aria-controls="details-communication"
      >
        <span class="model-card-type">Action</span>

        <strong>Result communication</strong>

        <p>
          Effort allocated to making developed work visible.
        </p>

        <span class="model-card-more">
          View assumption
        </span>
      </button>

      <div
        class="model-card-details"
        id="details-communication"
        hidden
      >
        <p>
          Communication is more effective when sufficient progress and
          knowledge already exist.
        </p>

        <p>
          Meaningful communication can increase support and make some
          developed work more visible.
        </p>
      </div>
    </article>


    <article
      class="model-card state-card diagram-progress"
      id="progress"
    >
      <button
        class="model-card-trigger"
        type="button"
        aria-expanded="false"
        aria-controls="details-progress"
      >
        <span class="model-card-type">State</span>

        <strong>Visible progress</strong>

        <p>
          Tangible development toward completing the research.
        </p>

        <span class="model-card-more">
          View assumption
        </span>
      </button>

      <div
        class="model-card-details"
        id="details-progress"
        hidden
      >
        <p>
          Implementation produces most visible progress. Communication
          provides a smaller visibility gain.
        </p>

        <p>
          Progress gradually saturates as the simulated project approaches
          completion and provides some deadline relief.
        </p>
      </div>
    </article>

  </div>

</section>

<script>
  document.addEventListener("DOMContentLoaded", () => {
    const diagram = document.querySelector("[data-model-diagram]");

    if (!diagram) return;

    const buttons = diagram.querySelectorAll(
      ".model-card-trigger[aria-controls]"
    );

    buttons.forEach((button) => {
      button.addEventListener("click", () => {
        const detailsId = button.getAttribute("aria-controls");
        const details = document.getElementById(detailsId);

        if (!details) return;

        const currentlyOpen =
          button.getAttribute("aria-expanded") === "true";

        button.setAttribute(
          "aria-expanded",
          String(!currentlyOpen)
        );

        details.hidden = currentlyOpen;

        /*
         * Expanding a card changes its position and size,
         * so redraw the arrows afterward.
         */
        requestAnimationFrame(drawModelConnections);
      });
    });
  });
</script>
<script>
  function drawModelConnections() {
    const diagram = document.querySelector("[data-model-diagram]");
    const svg = diagram?.querySelector(".model-connectors");

    if (!diagram || !svg) return;

    const diagramRect = diagram.getBoundingClientRect();

    svg.setAttribute(
      "viewBox",
      `0 0 ${diagramRect.width} ${diagramRect.height}`
    );

    const connections = svg.querySelectorAll(
      "path[data-from][data-to]"
    );

    connections.forEach((path) => {
      const from = document.getElementById(
        path.dataset.from
      );

      const to = document.getElementById(
        path.dataset.to
      );

      if (!from || !to) return;

      const fromRect = from.getBoundingClientRect();
      const toRect = to.getBoundingClientRect();

      const fromCenterX =
        fromRect.left
        - diagramRect.left
        + fromRect.width / 2;

      const fromCenterY =
        fromRect.top
        - diagramRect.top
        + fromRect.height / 2;

      const toCenterX =
        toRect.left
        - diagramRect.left
        + toRect.width / 2;

      const toCenterY =
        toRect.top
        - diagramRect.top
        + toRect.height / 2;

      const horizontalDistance =
        Math.abs(toCenterX - fromCenterX);

      const verticalDistance =
        Math.abs(toCenterY - fromCenterY);

      let startX;
      let startY;
      let endX;
      let endY;

      /*
       * Connect through the closest-facing sides.
       */
      if (horizontalDistance > verticalDistance) {
        const movingRight = toCenterX > fromCenterX;

        startX = movingRight
          ? fromRect.right - diagramRect.left
          : fromRect.left - diagramRect.left;

        endX = movingRight
          ? toRect.left - diagramRect.left
          : toRect.right - diagramRect.left;

        startY = fromCenterY;
        endY = toCenterY;
      } else {
        const movingDown = toCenterY > fromCenterY;

        startX = fromCenterX;
        endX = toCenterX;

        startY = movingDown
          ? fromRect.bottom - diagramRect.top
          : fromRect.top - diagramRect.top;

        endY = movingDown
          ? toRect.top - diagramRect.top
          : toRect.bottom - diagramRect.top;
      }

      const controlX = (startX + endX) / 2;

      path.setAttribute(
        "d",
        [
          `M ${startX} ${startY}`,
          `C ${controlX} ${startY},`,
          `${controlX} ${endY},`,
          `${endX} ${endY}`
        ].join(" ")
      );
    });
  }

  document.addEventListener(
    "DOMContentLoaded",
    drawModelConnections
  );

  window.addEventListener(
    "resize",
    drawModelConnections
  );
</script>


  <!-- =========================================================
       ACTION ASSUMPTIONS
  ========================================================== -->

  <section class="artifact-section">
    <div class="section-heading">

      <div>
        <h3>Actions</h3>

        <p>
          Weekly effort allocation
        </p>
      </div>
    </div>

    <div class="action-assumptions">

        <!-- Literature review -->

        <details class="action-detail">
        <summary>
            <span class="action-summary-text">
            <strong>Literature review</strong>

            <small>
                Develops knowledge and changes research uncertainty
            </small>
            </span>

            <span class="detail-icon" aria-hidden="true">+</span>
        </summary>

        <div class="action-content">
            <div class="action-effects">
            <span>↑ Knowledge</span>
            <span>Usually ↓ research uncertainty</span>
            <span>May temporarily ↑ research uncertainty early on</span>
            </div>

            <p>
            Literature review is assumed to increase knowledge, with larger
            gains when current knowledge is still limited. Its effectiveness
            also depends on energy, health, and life uncertainty.
            </p>

            <p>
            Literature review generally reduces research uncertainty.
            However, when knowledge is still low, reading may reveal
            previously unrecognized complexity and temporarily increase
            research uncertainty.
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
                Converts effort and research direction into progress and results
            </small>
            </span>

            <span class="detail-icon" aria-hidden="true">+</span>
        </summary>

        <div class="action-content">
            <div class="action-effects">
            <span>↑ Research progress</span>
            <span>↑ Available results</span>
            <span>May ↑ research uncertainty when knowledge is low</span>
            </div>

            <p>
            Implementation is assumed to be more productive when effective
            capacity and research direction quality are higher. Direction
            quality depends on knowledge, feedback clarity, and research
            uncertainty.
            </p>

            <p>
            Implementation generates results that can later be analyzed.
            Its contribution gradually saturates as research progress and
            available results approach their maximum values.
            </p>

            <p>
            Implementation undertaken with very limited knowledge may
            increase research uncertainty through poorly directed work or
            difficulty interpreting what should be implemented.
            </p>
        </div>
        </details>


        <!-- Result analysis -->

        <details class="action-detail">
        <summary>
            <span class="action-summary-text">
            <strong>Result analysis</strong>

            <small>
                Converts available results into progress and reduced uncertainty
            </small>
            </span>

            <span class="detail-icon" aria-hidden="true">+</span>
        </summary>

        <div class="action-content">
            <div class="action-effects">
            <span>↑ Research progress</span>
            <span>↑ Knowledge</span>
            <span>↓ Research uncertainty</span>
            <span>↓ Available results</span>
            </div>

            <p>
            Analysis requires available results. The amount analyzed during
            one week is limited by both the analysis allocation and the
            quantity of results currently available.
            </p>

            <p>
            Analysis is assumed to be more productive when effective
            capacity and knowledge are higher. Its informational value is
            also greater when meaningful research uncertainty remains to be
            resolved.
            </p>

            <p>
            Analysis contributes directly to research progress, reduces
            research uncertainty, and provides a smaller contribution to
            knowledge. Analysis effort allocated when few or no results are
            available receives a wasted-effort penalty.
            </p>
        </div>
        </details>


        <!-- Result communication -->

        <details class="action-detail">
        <summary>
            <span class="action-summary-text">
            <strong>Result communication</strong>

            <small>
                Uses developed work to generate feedback, support, and clarification
            </small>
            </span>

            <span class="detail-icon" aria-hidden="true">+</span>
        </summary>

        <div class="action-content">
            <div class="action-effects">
            <span>↑ Feedback clarity</span>
            <span>↑ Professional support</span>
            <span>↓ Research uncertainty</span>
            <span>May change research progress through redirection</span>
            </div>

            <p>
            The effectiveness of communication depends on effective capacity
            and communication readiness. Readiness is higher when research
            progress and knowledge are greater and research uncertainty is
            lower.
            </p>

            <p>
            Communicating sufficiently developed work is assumed to improve
            feedback clarity, reduce research uncertainty, and indirectly
            strengthen professional support. It may also contribute a small
            amount of research progress.
            </p>

            <p>
            Communication can reveal that part of the current direction
            should be revised. In the simulation, this may remove a small
            amount of accumulated progress while also reducing research
            uncertainty.
            </p>

            <p>
            Communication allocated before the work is sufficiently ready
            receives a premature-communication penalty.
            </p>
        </div>
        </details>


        <!-- Recovery -->

        <details class="action-detail">
        <summary>
            <span class="action-summary-text">
            <strong>Recovery</strong>

            <small>
                Restores energy, supports health, and increases sustainable capacity
            </small>
            </span>

            <span class="detail-icon" aria-hidden="true">+</span>
        </summary>

        <div class="action-content">
            <div class="action-effects">
            <span>↑ Energy</span>
            <span>↑ Health</span>
            <span>Raises the workload threshold before overload</span>
            </div>

            <p>
            Recovery does not directly generate research progress. Instead,
            it restores energy, supports gradual health recovery, and makes
            a given research workload less likely to produce overload.
            </p>

            <p>
            Recovery is assumed to be more effective when health is stronger
            and life uncertainty is lower. Energy recovery also gradually
            saturates as energy approaches its maximum value.
            </p>

            <p>
            Recovery does not directly reduce life uncertainty. Life
            uncertainty is modeled separately through external disturbances,
            deadline spillover, and buffering from professional support.
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
          Ten evolving state variables and one deterministic measure of remaining time. All values are normalized between zero and one.
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
                Energy, health, and life stability jointly determine how effectively
                allocated effort can influence the research process.
            </p>
            </div>
        </div>

        <div class="assumption-equation">
            physical capacity
            =
            0.55 × energy
            +
            0.45 × health
        </div>

        <div class="assumption-equation assumption-equation-secondary">
            effective capacity
            =
            physical capacity
            ×
            [0.55 + 0.45 × (1 − life uncertainty)]
        </div>

        <div class="assumption-meaning">
            <strong>Modeling assumption</strong>
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
            0.40 × knowledge
            +
            0.35 × feedback clarity
            +
            0.25 × (1 − research uncertainty)
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
            literature learning
            =
            0.075
            × literature allocation
            × effective capacity
            × (1 − knowledge)
        </div>

        <div class="assumption-equation assumption-equation-secondary">
            knowledge next week
            =
            knowledge this week
            +
            literature learning
            +
            0.30 × information gain
            +
            random literature variation
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
            implementation productivity
            =
            0.070
            × implementation allocation
            × effective capacity
            × (0.25 + 0.75 × direction quality)
            × (1 − research progress)
        </div>

        <div class="assumption-equation assumption-equation-secondary">
            research progress next week
            =
            research progress this week
            +
            implementation productivity
            +
            analysis productivity
            +
            communication progress
            +
            random variation
            −
            possible redirection cost
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
            results generated
            =
            0.13
            × implementation allocation
            × effective capacity
            × (0.30 + 0.70 × knowledge)
            × (1 − available results)
        </div>

        <div class="assumption-equation assumption-equation-secondary">
            analyzable results
            =
            minimum of
            [
            available results,
            0.15 × analysis allocation
            ]
        </div>

        <div class="assumption-equation assumption-equation-secondary">
            available results next week
            =
            available results this week
            +
            results generated
            −
            analyzable results
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
            analysis productivity
            =
            analyzable results
            × effective capacity
            × (0.45 + 0.55 × knowledge)
        </div>

        <div class="assumption-equation assumption-equation-secondary">
            information gain
            =
            0.75
            × analysis productivity
            × (0.40 + 0.60 × research uncertainty)
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
            research uncertainty next week
            =
            research uncertainty this week
            +
            uncertainty revealed or generated
            −
            uncertainty resolved
        </div>

        <div class="assumption-equation assumption-equation-secondary">
            uncertainty revealed or generated
            =
            confusion from implementation with low knowledge
            +
            unknowns revealed by early literature review
            +
            literature overuse effect
        </div>

        <div class="assumption-equation assumption-equation-secondary">
            uncertainty resolved
            =
            literature-based reduction
            +
            information gain from analysis
            +
            communication-based reduction
            +
            information from possible redirection
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
            communication readiness
            =
            0.55 × research progress
            +
            0.30 × knowledge
            +
            0.15 × (1 − research uncertainty)
        </div>

        <div class="assumption-equation assumption-equation-secondary">
            communication quality
            =
            communication allocation
            × effective capacity
            × communication readiness
        </div>

        <div class="assumption-equation assumption-equation-secondary">
            feedback clarity next week
            =
            feedback clarity this week
            +
            0.070
            × communication quality
            × (1 − feedback clarity)
            +
            random feedback variation
        </div>

        <div class="assumption-equation assumption-equation-secondary">
            professional support next week
            =
            professional support this week
            +
            0.020
            × communication quality
            × (1 − professional support)
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
            <div>
            <h4>Energy dynamics</h4>
            <p>
                Different research activities consume different amounts of
                energy, while recovery restores it.
            </p>
            </div>
        </div>

        <div class="assumption-equation">
            research workload
            =
            literature allocation
            +
            1.25 × implementation allocation
            +
            1.10 × analysis allocation
            +
            0.85 × communication allocation
        </div>

        <div class="assumption-equation assumption-equation-secondary">
            energy cost
            =
            0.060
            × research workload
            × (1.10 − 0.25 × health)
        </div>

        <div class="assumption-equation assumption-equation-secondary">
            recovery quality
            =
            0.45
            +
            0.35 × health
            +
            0.20 × (1 − life uncertainty)
        </div>

        <div class="assumption-equation assumption-equation-secondary">
            energy recovery
            =
            0.18
            × recovery allocation
            × recovery quality
            × (1 − energy)
            +
            0.030
            × recovery allocation
            × recovery quality
        </div>

        <div class="assumption-equation assumption-equation-secondary">
            energy next week
            =
            energy this week
            +
            energy recovery
            −
            energy cost
        </div>

        <div class="assumption-meaning">
            <strong>Modeling assumption</strong>

            <p>
            Implementation and analysis are assumed to be more energetically
            demanding than literature review or communication. Recovery becomes
            less effective when health is lower or life uncertainty is higher,
            and its effect gradually saturates as energy approaches its maximum.
            </p>
        </div>

        </article>


        <!-- HEALTH -->

        <article class="assumption-card">

        <div class="assumption-heading">
            <div>
            <h4>Health dynamics</h4>
            <p>
                Health changes more slowly than energy and is affected primarily
                by overload, exhaustion, and recovery.
            </p>
            </div>
        </div>

        <div class="assumption-equation">
            overload
            =
            maximum of
            [
            0,
            research workload
            − 0.82
            − 0.35 × recovery allocation
            ]
        </div>

        <div class="assumption-equation assumption-equation-secondary">
            health loss
            =
            0.040
            × overload
            × (1.15 − energy)
        </div>

        <div class="assumption-equation assumption-equation-secondary">
            health recovery
            =
            0.055
            × recovery allocation
            × recovery quality
            × (1 − health)
        </div>

        <div class="assumption-equation assumption-equation-secondary">
            exhaustion damage
            =
            0.035
            × maximum of
            [
            0,
            0.25 − energy
            ]
        </div>

        <div class="assumption-equation assumption-equation-secondary">
            health next week
            =
            health this week
            +
            health recovery
            −
            health loss
            −
            exhaustion damage
        </div>

        <div class="assumption-meaning">
            <strong>Modeling assumption</strong>

            <p>
            Recovery both supports gradual health restoration and increases the
            amount of workload that can be sustained before overload occurs.
            Overload becomes more damaging when energy is already depleted, and
            critically low energy can reduce health even without additional
            overload.
            </p>
        </div>

        </article>

        <!-- LIFE UNCERTAINTY -->

        <article class="assumption-card">

        <div class="assumption-heading">
            <div>
            <h4>Life uncertainty</h4>
            <p>
                External instability changes independently of research effort,
                while deadlines and professional support influence how it evolves.
            </p>
            </div>
        </div>

        <div class="assumption-equation">
            external life change
            =
            random weekly disturbance
        </div>

        <div class="assumption-equation assumption-equation-secondary">
            deadline spillover
            =
            0.010
            × deadline pressure
            × (1 − professional support)
        </div>

        <div class="assumption-equation assumption-equation-secondary">
            support buffer
            =
            0.008
            × professional support
            × life uncertainty
        </div>

        <div class="assumption-equation assumption-equation-secondary">
            life uncertainty next week
            =
            life uncertainty this week
            +
            external life change
            +
            deadline spillover
            −
            support buffer
        </div>

        <div class="assumption-meaning">
            <strong>Modeling assumption</strong>

            <p>
            Life uncertainty is treated largely as an external process rather
            than something directly solved through research effort. Deadline
            pressure can spill into greater instability, especially when
            professional support is limited, while stronger support provides a
            small buffering effect.
            </p>
        </div>

        </article>


        <!-- DEADLINE PRESSURE -->

        <article class="assumption-card">

        <div class="assumption-heading">
            <div>
            <h4>Deadline pressure</h4>
            <p>
                Deadline pressure accumulates as time passes and work remains
                incomplete, while progress and communication provide some relief.
            </p>
            </div>
        </div>

        <div class="assumption-equation">
            elapsed time fraction
            =
            current week
            ÷ total number of weeks
        </div>

        <div class="assumption-equation assumption-equation-secondary">
            deadline growth
            =
            0.018
            +
            0.030 × elapsed time fraction
            +
            0.020 × (1 − research progress)
        </div>

        <div class="assumption-equation assumption-equation-secondary">
            deadline relief
            =
            0.035
            × maximum of
            [
            0,
            progress gained this week
            ]
            +
            0.018
            × communication quality
        </div>

        <div class="assumption-equation assumption-equation-secondary">
            deadline pressure next week
            =
            deadline pressure this week
            +
            deadline growth
            −
            deadline relief
        </div>

        <div class="assumption-meaning">
            <strong>Modeling assumption</strong>

            <p>
            Deadline pressure has a baseline tendency to grow every week. It
            increases more quickly later in the simulated year and when research
            remains incomplete. Meaningful progress and effective communication
            provide partial relief, but do not necessarily eliminate the
            underlying time pressure.
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
            progress gain
            + knowledge gain
            + research-uncertainty reduction
        </span>

        <span class="equation-negative">
            − health loss
            − critically low energy
            − overload under life uncertainty
            − severe life uncertainty
            − deadline pressure
            − wasted effort
        </span>

        <span class="equation-bonus">
            + completion or final-state bonuses
        </span>
    </div>
    
  </section>

<!-- =========================================================
       Termination
  ========================================================== -->

  <section class="artifact-section">

    <h4>Episode completion and termination</h4>
    <div class="assumption-equation">
        research completed
        =
        research progress ≥ 0.95
        and
        research uncertainty ≤ 0.25
    </div>

    <div class="assumption-equation assumption-equation-secondary">
        health collapse
        =
        health ≤ 0.03
    </div>

    <div class="assumption-equation assumption-equation-secondary">
        unable to continue
        =
        life uncertainty ≥ 0.98
        and
        professional support ≤ 0.05
    </div>

    <div class="assumption-equation assumption-equation-secondary">
        time limit
        =
        52 weeks
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