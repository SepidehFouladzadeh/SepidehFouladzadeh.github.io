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
    <h2>Modeling Assumptions</h2>
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

  The desirable outcome is making research progress, gaining knowledge, and having an effective contribution though meaningful communication but not through health collapse. Rewarding meaningful and sustainable research development rather than progress alone :)

  <!-- =========================================================
       REWARD
  ========================================================== -->

  <section class="artifact-section">

    <div class="equation-card">
      <p class="equation-title">Reward</p>

      <div class="reward-equation">

        <span class="equation-positive">
            + visible progress
            + knowledge gained
            + meaningful communication
        </span>

        <span class="equation-negative">
            − capacity loss
            − critically low capacity
            − wasted effort
        </span>

      </div>
    </div>
    
  </section>


  And ending the episode with: 

  <!-- =========================================================
      EPISODE ENDING
  ========================================================= -->

  <section class="artifact-section">

    <div class="termination-grid">

      <div class="termination-card">
        <strong>Research completed</strong>
        <p>
          Visible progress reaches 0.95.
        </p>
      </div>

      <div class="termination-card">
        <strong>Capacity collapse</strong>
        <p>
          Capacity falls to 0.03 or below.
        </p>
      </div>

      <div class="termination-card">
        <strong>Time limit reached</strong>
        <p>
          The 52-week simulation ends.
        </p>
      </div>

    </div>

  </section>


  Along with an additional bonus for completing the research with more capacity and knowledge!

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

  <section class="artifacts">

  <h2>Artifacts from this exploration</h2>

  <div class="artifact-gallery">

  <div class="artifact-card">
    <img controls>
      <source src="/assets/images/learned_weekly_allocation.png" type="image/png">
    </img>
    <!-- <h4>PPO</h4> -->
    <p>Learned weekly allocation.</p>
  </div>

  <div class="artifact-card">
    <img controls>
      <source src="/assets/images/reward_components.png" type="image/png">
    </img>
    <!-- <h4>LQR</h4> -->
    <p>Reward components.</p>
  </div>

  <div class="artifact-card">
    <img controls>
      <source src="/assets/images/state_evolution.png" type="image/png">
    </img>
    <!-- <h4>Manual State Feedback</h4> -->
    <p>State evolution.</p>
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

      <a href="/research/rl-vs-control/custom-environment/">
        See my train of thought →
      </a>
    </article>

  </div>

</section>