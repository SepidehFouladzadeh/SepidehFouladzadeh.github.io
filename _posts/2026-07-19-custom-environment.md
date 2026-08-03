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

    <article
      class="model-card state-card diagram-deadline"
      id="deadline"
      style="grid-column: 2; grid-row: 1;"
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
          Pressure associated with limited time and incomplete work.
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
          Deadline pressure builds over time. It grows more quickly as the end of the timeline approaches and when visible progress remains limited. Making progress brings some immediate relief, while a small amount of randomness represents factors not explicitly included in the model. 
        </p>

        <div class="model-equation">
          previous pressure<br>
          + deadline growth<br>
          − progress relief<br>
          + random variation
        </div>
      </div>
    </article>


    <article
      class="model-card state-card diagram-capacity"
      id="capacity"
      style="grid-column: 1; grid-row: 1;"
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
          The ability to work effectively and sustain research activity.
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
          Recovery restores depleted capacity, with smaller gains as capacity approaches its maximum. Research activity can also create momentum, making it easier to continue working. Workload is not treated as inherently harmful, but overload beyond a sustainable threshold reduces capacity, becoming more damaging when capacity is already low.
        </p>

        <div class="model-equation"> 
        previous capacity <br>
        + recovery <br>
        + momentum <br>
        − overload 
        </div>

      </div>
    </article>


    <article
      class="model-card state-card diagram-support"
      id="support"
      style="grid-column: 3; grid-row: 1;"
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
          Access to professional support, feedback, and useful external input.
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
          Support grows gradually through meaningful result communication. Communication is more effective when capacity is higher and less effective when deadline pressure narrows attention toward immediate completion. It is also more useful when there is enough developed work and knowledge to communicate clearly.
        </p>

        <div class="model-equation"> 
        previous support<br>
        + meaningful communication<br>
        + random variation<br>
        </div>
      </div>
    </article>


    <article
      class="model-card state-card diagram-knowledge"
      id="knowledge"
      style="grid-column: 1; grid-row: 2;"
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
          Knowledge grows through literature review, learning by doing, and a smaller contribution from support. Learning is more effective when working capacity is higher, and recovery can improve that capacity during the current week. Knowledge gains become smaller as understanding approaches its maximum, with a playful assumption that deadline pressure can temporarily sharpen focus.
        </p>

        <div class="model-equation"> 
        previous knowledge<br> 
        + literature learning <br> 
        + learning by doing <br> 
        + support-based learning <br> 
        + random variation 
        </div>

      </div>
    </article>


    <article
      class="model-card state-card diagram-progress"
      id="progress"
      style="grid-column: 2; grid-row: 2;"
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
          Visible progress grows mainly through implementation. Implementation is more productive when working capacity and knowledge are higher. Progress becomes harder as the project approaches completion. Meaningful communication makes the developed work more visible.
        </p>
        <div class="model-equation"> 
        previous progress<br>
        + implementation gain<br> 
        + communication visibility<br> 
        + random variation 
        </div>
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
      });
    });
  });
</script>


<section class="causal-graph-section">

  <div class="section-heading">
    <h2>Dynamic Causal Graph</h2>
  </div>

  <figure class="causal-graph-preview">
    <button
      class="graph-open-button"
      type="button"
      aria-label="Open causal graph in a larger view"
      aria-haspopup="dialog"
      aria-controls="graph-modal"
    >
      <img
        src="/assets/images/research_process_causal_graph.png"
        alt="Dynamic causal graph of the research process environment"
      >

      <span>Click to enlarge</span>
    </button>
  </figure>

  <div
    class="graph-modal"
    id="graph-modal"
    role="dialog"
    aria-modal="true"
    aria-label="Expanded dynamic causal graph"
    hidden
  >
    <div class="graph-modal-backdrop" data-close-graph></div>

    <div class="graph-modal-window">
      <button
        class="graph-modal-close"
        type="button"
        aria-label="Close expanded graph"
        data-close-graph
      >
        ×
      </button>

      <div class="graph-modal-image-wrapper">
        <img
          src="/assets/images/research_process_causal_graph.png"
          alt="Expanded dynamic causal graph of the research process environment"
        >
      </div>
    </div>
  </div>

</section>

<script>
  document.addEventListener("DOMContentLoaded", () => {
    const openButton = document.querySelector(".graph-open-button");
    const modal = document.querySelector("#graph-modal");
    const closeButtons = modal?.querySelectorAll("[data-close-graph]");
    const closeButton = modal?.querySelector(".graph-modal-close");

    if (!openButton || !modal) {
      return;
    }

    const openModal = () => {
      modal.hidden = false;
      document.body.classList.add("graph-modal-open");
      closeButton?.focus();
    };

    const closeModal = () => {
      modal.hidden = true;
      document.body.classList.remove("graph-modal-open");
      openButton.focus();
    };

    openButton.addEventListener("click", openModal);

    closeButtons?.forEach((button) => {
      button.addEventListener("click", closeModal);
    });

    document.addEventListener("keydown", (event) => {
      if (event.key === "Escape" && !modal.hidden) {
        closeModal();
      }
    });
  });
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

  <section class="artifacts">

  <h2>Artifacts from this exploration</h2>

  <div class="artifact-figure">
    <img
      src="/assets/images/learned_weekly_allocation.png"
      alt="Learned weekly allocation"
    >

    <p class="artifact-caption">
      <strong>Learned weekly allocation.</strong>
      The policy gradually shifts effort among literature review,
      implementation, communication, and recovery over the simulated year.
    </p>
  </div>

  <div class="artifact-figure">
    <img
      src="/assets/images/state_evolution.png"
      alt="State evolution"
    >

    <p class="artifact-caption">
      <strong>State evolution.</strong>
      Evolution of capacity, deadline pressure, support, knowledge,
      and visible progress under the learned policy.
    </p>
  </div>

  <div class="artifact-figure">
    <img
      src="/assets/images/reward_components.png"
      alt="Reward components"
    >

    <p class="artifact-caption">
      <strong>Reward components.</strong>
      Weekly contribution of each reward component during evaluation.
    </p>
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
      definitions designed for the environment.
    </p>

    <p>
      The purpose was to make those assumptions inspectable, not to build a sophisticated model of the research process, which might be an interesting direction to explore next! ;)
    </p>
  </div>

</section>

<section class="related-explorations">

  <h2>Other explorations inspired by this train of thought</h2>

  <div class="related-exploration-list">

    <article class="related-exploration-item">
      <h3>Modeling the Research Process</h3>

      <p>
        Exploring related modeling frameworks: What questions can other modeling frameworks answer using the same assumptions?
      </p>

      <a href="/research/rl-vs-control/custom-environment/">
        See my train of thought →
      </a>
    </article>

  </div>

</section>