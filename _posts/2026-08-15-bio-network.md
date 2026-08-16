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
    <image controls>
      <source src="/assets/images/ranked_protein_variance.png" type="image/png">
    </image>
    <h4>ranked_protein_variance</h4>
    <!-- <p>
    This was my starting point for understanding how RL discovers a
    control strategy through interaction rather than from an explicit model.
    Trained a MLP policy with PPO for 100,000 timesteps, resulting in a controller that reliably keeps the pole balanced.
    </p> -->
  </div>

  <div class="artifact-card">
    <images controls>
      <source src="/assets/images/protein_correlation_heatmap.png" type="images/png">
    </images>
    <h4>protein_correlation_heatmap</h4>
    <!-- <p>
    Was curious how a classical optimal controller would compare with the
    policy learned by PPO. Using the linearized CartPole dynamics, LQR performed similarly successful. Realized that choosing the cost matrices (<em>Q</em>
    and <em>R</em>) is itself an important design decision, shaping the
    controller's behavior. With my chosen weights, the controller wasn't particularly concerned with keeping the cart close to the center and mainly focused on keeping the pole upright.
    </p> -->
  </div>

  <div class="artifact-card">
    <images controls>
      <source src="/assets/images/pca_scree_plot.png" type="images/png">
    </images>
    <h4>pca_scree_plot</h4>
    <!-- <p>Was curious to know if the learned policy from PPO can be approximated by a linear state-feedback controller. Fit a logistic regression to PPO's actions to get a linearized policy, but it was unable to control the CartPole. I suspect because PPO acts in a discrete action space (left or right), the linearization wouldn't recover the continuous control signal of LQR.
    </p> -->
  </div>

  <div class="artifact-card">
    <images controls>
      <source src="/assets/images/pc_phenotype_correlation.png" type="images/png">
    </images>
    <h4>pc_phenotype_correlation</h4>
    <!-- <p>Was curious to know if the learned policy from PPO can be approximated by a linear state-feedback controller. Fit a logistic regression to PPO's actions to get a linearized policy, but it was unable to control the CartPole. I suspect because PPO acts in a discrete action space (left or right), the linearization wouldn't recover the continuous control signal of LQR.
    </p> -->
  </div>

  <div class="artifact-card">
    <images controls>
      <source src="/assets/images/pca_by_cellviab.png" type="images/png">
    </images>
    <h4>pca_by_cellviab</h4>
    <!-- <p>Was curious to know if the learned policy from PPO can be approximated by a linear state-feedback controller. Fit a logistic regression to PPO's actions to get a linearized policy, but it was unable to control the CartPole. I suspect because PPO acts in a discrete action space (left or right), the linearization wouldn't recover the continuous control signal of LQR.
    </p> -->
  </div>

  <div class="artifact-card">
    <images controls>
      <source src="/assets/images/pca_pc1_loadings.png" type="images/png">
    </images>
    <h4>pca_pc1_loadings</h4>
    <!-- <p>Was curious to know if the learned policy from PPO can be approximated by a linear state-feedback controller. Fit a logistic regression to PPO's actions to get a linearized policy, but it was unable to control the CartPole. I suspect because PPO acts in a discrete action space (left or right), the linearization wouldn't recover the continuous control signal of LQR.
    </p> -->
  </div>

  <div class="artifact-card">
    <images controls>
      <source src="/assets/images/pca_pc2_loadings.png" type="images/png">
    </images>
    <h4>pca_pc2_loadings</h4>
    <!-- <p>Was curious to know if the learned policy from PPO can be approximated by a linear state-feedback controller. Fit a logistic regression to PPO's actions to get a linearized policy, but it was unable to control the CartPole. I suspect because PPO acts in a discrete action space (left or right), the linearization wouldn't recover the continuous control signal of LQR.
    </p> -->
  </div>

</div>

</section>


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