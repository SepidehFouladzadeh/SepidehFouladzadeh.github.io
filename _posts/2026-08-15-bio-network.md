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

  <p>
    Experimental rows:       89<br>
    Total nodes:             99<br>
    Protein nodes:           82<br>
    Phenotype nodes:         5<br>
    Perturbation nodes:      12<br>
  </p>
  <p>
    Phenotypes:<br>
    - G2M<br>
    - G1arrest<br>
    - G2arrest<br>
    - Sarrest<br>
    - cellviab<br>
  <p>
  <p>
    Perturbations:<br>
    - aMEK<br>
    - aAKT<br>
    - aHDAC<br>
    - aMDM2<br>
    - aJAK<br>
    - aBRAFm<br>
    - aPKC<br>
    - aSTAT3<br>
    - amTOR<br>
    - aPI3K<br>
    - aCDK4<br>
    - aSRC<br>
  <p>

</details>

<section class="related-explorations">

  <h2>Other explorations inspired by this train of thought</h2>

  <div class="related-exploration-list">

    <article class="related-exploration-item">
      <h3>Extracting the Most from Measured Outputs</h3>

      <p>
        Learning What Can Be Learned from Molecular and Phenotypic Measurements. 
      </p>

      <a href="/research/bio-network/measurements">
        See my train of thought →
      </a>
    </article>

  </div>

</section>