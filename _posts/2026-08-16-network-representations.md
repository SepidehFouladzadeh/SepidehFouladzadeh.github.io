---
layout: exploration
title: "A rabbit hole into understanding how measurements become network representations."
description: "Curious how different computational methods transform measurements into graphs and networks."
date: 2026-08-16
# reading_time: "1 min read"
linkedin_url: "https://www.linkedin.com/in/sepideh-fouladzadeh/"
permalink: /research/bio-network/network-representations/
back_url: /research/bio-network/
back_text: Back to where this began
---

<p class="flow-instruction">
  Hover over for a few more details ;)
</p>

<div class="flow thought-flow">

  <div class="thought-step">
    <button class="flow-node thought-trigger" type="button">
      <h3>
        What information can I extract from a perturbation–response dataset?
      </h3>
      <p>
      Perturbations applied to melanoma cells together with molecular and phenotypic responses.
      </p>
    </button>

    <div class="thought-cloud">
      <h3>The dataset</h3>

      <p>
          A set of perturbation experiments paired with molecular and phenotypic measurements. Nice playground for exploring different computational methods for understanding biological systems.

      </p>
      
    </div>
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
          <h3>What can I learn from the response measurements alone?</h3>
          <p> Finding patterns in the outputs (with minimal prior assumptions).
          </p>
        </button>

        <div class="thought-cloud thought-cloud-left">
          <h3>Exploratory data analysis, representation learning, and network reconstruction</h3>
          <p class="thought-evidence">
            ✓ Which proteins change the most across conditions?<br>
            ✓ Are there low-dimensional representations?<br>
            ✓ Can interactions or causal structures be inferred?<br>
        </p>
        </div>
      </div>

    </div>
    <!-- Middle BRANCH -->
        <div class="branch">

      <div class="branch-line"></div>

      <div class="thought-step">
        <button class="flow-node thought-trigger" type="button">
          <h3>What if I use both perturbations and responses?</h3>
          <p> Learn mappings from inputs to outputs.
          </p>
        </button>

        <div class="thought-cloud thought-cloud-middle">
          <h3>Supervised learning</h3>

          <p class="thought-evidence">
          ✓ Per protein predictions?<br>
          ✓ Per phenotype predictions?<br>
          ✓ Most predictive features?<br>
      </p>

        </div>
      </div>

    </div>


    <!-- RIGHT BRANCH -->
    <div class="branch">

      <div class="branch-line"></div>

      <div class="thought-step">
        <button class="flow-node thought-trigger" type="button">
          <h3>What if I incorporate prior biological knowledge?</h3>
          <p>Constrain learning with biological knowledge.
          </p>
        </button>

        <div class="thought-cloud">
          <h3>Knowledge-based models</h3>

          <p class="thought-evidence">
          ✓ Does it improve prediction?<br>
          ✓ Does it produce more interpretable models?<br>
          ✓ Does it help evaluate purely data-driven methods?<br>
      </p>

        </div>
      </div>

    </div>
    </div>
</div>

<section class="artifacts">

  <h2>Artifacts from this exploration</h2>

  <div class="artifact-gallery">

  <div class="artifact-card">
  <img src="/assets/images/proteins_correlation_network.png"
     alt="proteins_correlation_network">
    <h4>proteins_correlation_network</h4>

      <p>
        ...
      </p>
  </div>

  <div class="artifact-card">
  <img src="/assets/images/proteins_correlation_heatmap.png"
     alt="proteins_correlation_heatmap">
    <h4>proteins_correlation_heatmap</h4>

      <p>
        ...
      </p>
  </div>

  <div class="artifact-card">
  <img src="/assets/images/expanded_correlation_network.png"
     alt="expanded_correlation_network">
    <h4>expanded_correlation_network</h4>

      <p>
        ...
      </p>
  </div>

  <div class="artifact-card">
  <img src="/assets/images/expanded_correlation_heatmap.png"
     alt="expanded_correlation_heatmap">
    <h4>expanded_correlation_heatmap</h4>

      <p>
        ...
      </p>
  </div>

  <h2>Artifacts from this exploration</h2>

  <div class="artifact-card">
  <img src="/assets/images/proteins_graphical_lasso_network.png"
     alt="proteins_graphical_lasso_network">
    <h4>proteins_graphical_lasso_network</h4>

      <p>
        ...
      </p>
  </div>

  <div class="artifact-card">
  <img src="/assets/images/expanded_graphical_lasso_network.png"
     alt="expanded_graphical_lasso_network">
    <h4>expanded_graphical_lasso_network</h4>

      <p>
        ...
      </p>
  </div>

</div>

</section>


<section class="artifacts">

  <h2>Artifacts from this exploration</h2>

  <div class="artifact-figure">
    <img
      src="/assets/images/proteins_bic_mle_numbered_dag.png"
      alt="proteins_bic_mle_numbered_dag"
    >

    <p class="artifact-caption">
      <strong>proteins_bic_mle_numbered_dag</strong>
      ...
    </p>
  </div>

  <div class="artifact-figure">
    <img
      src="/assets/images/proteins_aic_mle_numbered_dag.png"
      alt="proteins_aic_mle_numbered_dag"
    >

    <p class="artifact-caption">
      <strong>proteins_aic_mle_numbered_dag</strong>
      ...
    </p>
  </div>

  <div class="artifact-figure">
    <img
      src="/assets/images/expanded_hillclimb_bic_network.png"
      alt="expanded_hillclimb_bic_network"
    >

    <p class="artifact-caption">
      <strong>expanded_hillclimb_bic_network</strong>
      ...
    </p>
  </div>

  <div class="artifact-figure">
    <img
      src="/assets/images/expanded_hillclimb_aic_network.png"
      alt="expanded_hillclimb_aic_network"
    >

    <p class="artifact-caption">
      <strong>expanded_hillclimb_aic_network</strong>
      ...
    </p>
  </div>

</section>

<section class="artifacts">

  <h2>Artifacts from this exploration</h2>

  <div class="artifact-gallery">

  <div class="artifact-card">
  <img src="/assets/images/proteins_pc_network.png"
     alt="proteins_pc_network">
    <h4>proteins_pc_network</h4>

      <p>
        ...
      </p>
  </div>

  <div class="artifact-card">
  <img src="/assets/images/expanded_pc_network.png"
     alt="expanded_pc_network">
    <h4>expanded_pc_network</h4>

      <p>
        ...
      </p>
  </div>

</div>

</section>