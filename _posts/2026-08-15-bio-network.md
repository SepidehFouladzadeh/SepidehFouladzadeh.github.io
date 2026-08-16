---
layout: exploration
title: "Expanding on My Input–Output Perspective on Biological Systems"
description: "Cleaning up my mental framework around computational methods through perturbation biology. From classical ML for prediction to causal inference and the integration of biological domain knowledge."
date: 2026-08-15
# reading_time: "1 min read"
linkedin_url: "https://www.linkedin.com/in/sepideh-fouladzadeh/"
permalink: /research/bio-network/
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

<details class="dynamics-card">
  <summary>Getting to Know the Dataset</summary>

  <div class="dataset-matrix-diagram">

  <div class="matrix-title">
    99 measured nodes
  </div>

  <div class="matrix-wrapper">

    <div class="matrix-row-label">
      <strong>89</strong>
      <span>conditions</span>
    </div>

    <div class="matrix">

      <div class="matrix-header">

        <div class="cell">
          <span>proteins</span>
          <strong>82</strong>
        </div>

        <div class="cell">
          <span>phenotypes</span>
          <strong>5</strong>
        </div>

        <div class="cell">
          <span>perturbed nodes</span>
          <strong>12</strong>
        </div>

      </div>

      <div class="matrix-body">
        measured responses
      </div>

    </div>

  </div>

  <div class="matrix-pairing">
    <span>paired by input perturbation matrix</span>
    <div class="pair-arrow">↓</div>
    </div>
  </div>
    <div class="dataset-matrix-diagram">

    <div class="matrix-title">
        99 perturbation nodes
    </div>

    <div class="matrix-wrapper">

        <div class="matrix-row-label">
        <strong>89</strong>
        <span>conditions</span>
        </div>

        <div class="matrix">

        <div class="matrix-header">

            <div class="cell">
            <span>proteins</span>
            <strong>82</strong>
            </div>

            <div class="cell">
            <span>phenotypes</span>
            <strong>5</strong>
            </div>

            <div class="cell">
            <span>perturbed nodes</span>
            <strong>12</strong>
            </div>

        </div>

        <div class="matrix-body perturbation-body">

            <div class="zeros">
            all zeros
            </div>

            <div class="inputs">
            perturbation values
            </div>

        </div>

        </div>

    </div>
    
</div>

  <p>
    <strong>Phenotypes:</strong>
    G2M · G1 arrest · G2 arrest · S arrest · cell viability
    <strong>Perturbations:</strong>
    aMEK · aAKT · aHDAC · aMDM2 · aJAK · aBRAFm ·
    aPKC · aSTAT3 · amTOR · aPI3K · aCDK4 · aSRC
  </p>

</details>


<section class="artifacts">

  <h2>Artifacts from this exploration</h2>

  <div class="artifact-gallery">

  <div class="artifact-card">
  <img src="/assets/images/ranked_protein_variance.png"
     alt="Ranked variance of protein responses across experimental conditions">
    <h4>Which molecular responses vary the most?</h4>

      <p>
        A simple first look at which molecular
        measurements are most responsive across the perturbation dataset,
        without yet asking what drives those changes.
      </p>
  </div>

  <div class="artifact-card">
  <img src="/assets/images/protein_correlation_heatmap.png"
     alt="Correlation heatmap of highly variable protein responses">
    <h4>Which proteins tend to respond together?</h4>

      <p>
        Pairwise correlations giving clues about coordinated biological behavior, but not to distinguish
        direct interactions, shared regulation, or causal relationships.
      </p>
  </div>

  <div class="artifact-card">
  <img src="/assets/images/pca_scree_plot.png"
     alt="PCA scree plot of molecular responses">
    <h4>Can the response space be compressed?</h4>

      <p>
        Checking whether much of the variation across molecular measurements
        can be represented along a smaller number of dimensions.
      </p>
  </div>

  <div class="artifact-card">
  <img src="/assets/images/pc_phenotype_correlation.png"
     alt="Correlations between principal components and measured phenotypes">
    <h4>Do the molecular patterns relate to phenotype?</h4>

      <p>
        Checking whether particular axes of molecular variation are associated
        with phenotypic outcomes.
      </p>
  </div>

  <div class="artifact-card">
  <img src="/assets/images/pca_by_cellviab.png"
     alt="PCA scores colored by measured cell viability">
    <h4>How does cell viability appear in molecular response space?</h4>

      <p>
        Each point represents an experimental condition projected into the
        molecular PCA space, colored according to measured
        cell viability. The gradient suggests that conditions with
        similar viability also occupy similar regions of molecular response
        space.
      </p>
  </div>

  <div class="artifact-card">
  <img src="/assets/images/pca_pc1_loadings.png"
     alt="Largest protein loadings for the first principal component">
    <h4>Which proteins shape PC1?</h4>

      <p>
        PCA loadings showing molecular measurements that contribute most strongly
        to the first principal component. Positive and negative loadings represent
        opposite directions along the same molecular response pattern.
      </p>
  </div>

  <div class="artifact-card">
  <img src="/assets/images/pca_pc2_loadings.png"
     alt="Largest protein loadings for the second principal component">
    <h4>Which proteins shape PC2?</h4>

      <p>
        PCA loadings showing molecular measurements that contribute most strongly
        to the second principal component. Again, positive and negative loadings represent
        opposite directions along the same molecular response pattern.
      </p>
  </div>

</div>

</section>


<section class="related-explorations">

  <h2>Other explorations inspired by this train of thought</h2>

  <div class="related-exploration-list">

    <article class="related-exploration-item">
      <h3>A rabbit hole into understanding how measurements become network representations.</h3>

      <p>
        Curious how different computational methods transform measurements into graphs and networks. 
      </p>

      <a href="/research/bio-network/network-representations">
        See my train of thought →
      </a>
    </article>

  </div>

  <div class="related-exploration-list">

    <article class="related-exploration-item">
      <h3>Picking a Handful of the Most Promising Nodes in Hopes of Understanding the System Behind the Observations</h3>

      <p>
        Exploring alternative ways of selecting informative nodes beyond high variance as a starting point for downstream modeling. 
      </p>

      <a href="/research/bio-network/feature-selection">
        See my train of thought →
      </a>
    </article>

  </div>

</section>