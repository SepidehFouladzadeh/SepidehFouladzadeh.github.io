---
layout: exploration
title: "Playing with predictive models and learning from input–output perturbation responses"
description: "Exploring mappings from perturbations to biological responses across different generalization regimes."
date: 2026-08-21
# reading_time: "1 min read"
linkedin_url: "https://www.linkedin.com/in/sepideh-fouladzadeh/"
permalink: /research/bio-network/prediction/
back_url: /research/bio-network/
back_text: Back to where this began
---

<section class="artifacts">

  <!-- <h2>DAGs</h2> -->

  <div class="artifact-figure">
    <img
      src="/assets/images/generalization_comparison_phenotype.png"
      alt="generalization_comparison_phenotype"
    >

    <p class="artifact-caption">
      Starting with the phenotypes, I was curious how the same predictive
      models would hold up as I changed what it meant for a test example
      to be unseen: from held-out conditions, to unseen combinations,
      to an entirely unseen perturbation.
    </p>
  </div>

  <div class="artifact-figure">
    <img
      src="/assets/images/generalization_comparison_protein.png"
      alt="generalization_comparison_protein"
    >

    <p class="artifact-caption">
      Looking at the protein responses separately to see whether the same
      patterns of generalization show up at the molecular-response level.
    </p>
  </div>

</section>

<section class="artifacts">
  <!-- <h2>Conditional associations</h2> -->
  <div class="artifact-gallery">

  <div class="artifact-card">
  <img src="/assets/images/leave_one_out_phenotype_pearson-flat_distribution.png"
     alt="leave_one_out_phenotype_pearson-flat_distribution">

      <p>
        Looking at Pearson correlation after prediction error, to see how well the predicted pattern of phenotype responses follows the observed one across different held-out perturbations.
      </p>
  </div>

  <div class="artifact-card">
  <img src="/assets/images/leave_one_out_protein_pearson-flat_distribution.png"
     alt="leave_one_out_protein_pearson-flat_distribution">

      <p>
        Looking into the extent of agreement between predicted and observed response patterns based on left out perturbations, this time for protein responses.
      </p>
  </div>

  <div class="artifact-card">
  <img src="/assets/images/leave_one_out_phenotype_rmse_heatmap.png"
     alt="leave_one_out_phenotype_rmse_heatmap">

      <p>
        Exploring which unseen perturbations are easier or harder for each model when predicting phenotypes.
      </p>
  </div>

  <div class="artifact-card">
  <img src="/assets/images/leave_one_out_protein_rmse_heatmap.png"
     alt="leave_one_out_protein_rmse_heatmap">

      <p>
        This time looking for dependence of prediction on the perturbation for protein responses.
      </p>
  </div>

  <div class="artifact-card">
  <img src="/assets/images/leave_one_perturbation_out_deep_mlp_training_history.png"
     alt="leave_one_perturbation_out_deep_mlp_training_history">

      <p>
        A quick look inside the training process to make sure optimization continues to improve the training fit, and whether validation follows along.
      </p>
  </div>

  <div class="artifact-card">
  <img src="/assets/images/leave_one_perturbation_out_shallow_mlp_training_history.png"
     alt="leave_one_perturbation_out_shallow_mlp_training_history">

      <p>
        Comparing the learning behavior of a much simpler network.
      </p>
  </div>

  </div>
</section>

<section class="artifacts">

  <!-- <h2>DAGs</h2> -->

  <div class="artifact-figure">
    <img
      src="/assets/images/leave_one_perturbation_out_observed_vs_predicted.png"
      alt="leave_one_perturbation_out_observed_vs_predicted"
    >

    <p class="artifact-caption">
      Looking at predicted protein and phenotype responses vs. actual observations.
    </p>
  </div>

</section>