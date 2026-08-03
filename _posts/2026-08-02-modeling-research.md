---
layout: exploration
title: "Modeling the Research Process"
description: "Exploring related modeling frameworks: What questions can other modeling frameworks answer using the same assumptions?"
date: 2026-08-02
# reading_time: "1 min read"
linkedin_url: "https://www.linkedin.com/in/sepideh-fouladzadeh/"
permalink: /research/rl-vs-control/custom-environment/modeling-research
back_url: /research/rl-vs-control/custom-environment/
back_text: Back to where this began
---

Coming soon.

<section class="causal-graph-section">

  <div class="section-heading">
    <h2>Dynamic Causal Graph</h2>

    <p>
      The graph shows the direct dependencies encoded in one weekly
      transition of the environment.
    </p>
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