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

<section class="artifacts">

  <h2>Pairwise associations</h2>

  <div class="artifact-gallery">

  <div class="artifact-card">
  <img src="/assets/images/proteins_correlation_network.png"
     alt="proteins_correlation_network">

      <p>
        Simply a thresholded visualization of the pairwise correlation matrix on the right, using only the measured protein nodes. 
      </p>
  </div>

  <div class="artifact-card">
  <img src="/assets/images/proteins_correlation_heatmap.png"
     alt="proteins_correlation_heatmap">

      <p>
        Analyzing the strongly correlated proteins is something I'd be curious to explore next.
      </p>
  </div>

  <div class="artifact-card">
  <img src="/assets/images/expanded_correlation_network.png"
     alt="expanded_correlation_network">

      <p>
        Was wondering whether computing correlations on the whole node set including activity nodes and phenotypes would be more approprite or interesting. Since these are pairwise correlations, adding more variables doesn't change the existing protein–protein correlations though.
      </p>
  </div>

  <div class="artifact-card">
  <img src="/assets/images/expanded_correlation_heatmap.png"
     alt="expanded_correlation_heatmap">

      <p>
        While the network itself didn't reveal anything interesting at first glance, the heatmap showed that many activity nodes were similarly correlated with one another. Not sure whether this is expected biologically,but something to investigate later.
      </p>
  </div>
  </div>
</section>

<section class="artifacts">
  <h2>Conditional associations</h2>
  <div class="artifact-gallery">

  <div class="artifact-card">
  <img src="/assets/images/proteins_graphical_lasso_network.png"
     alt="proteins_graphical_lasso_network">

      <p>
        This extends the Graphical Lasso analysis on the main research page by repeating it on both the protein-only dataset and the expanded dataset including activity nodes and phenotypes.
      </p>
  </div>

  <div class="artifact-card">
  <img src="/assets/images/expanded_graphical_lasso_network.png"
     alt="expanded_graphical_lasso_network">

      <p>
        Was curious whether the partial correlations would change after including additional variables. Couldnt tell from the graph but wouldn't be suprised if the edges are affected. Since Graphical Lasso conditions on the remaining nodes, I suspect adding variables might change the dependencies even between proteins that were already present.
      </p>
  </div>
  </div>
</section>


<section class="artifacts">

  <h2>Score-based structure learning</h2>

  <div class="artifact-figure">
    <img
      src="/assets/images/proteins_bic_mle_numbered_dag.png"
      alt="proteins_bic_mle_numbered_dag"
    >

    <p class="artifact-caption">
      This was my first attempt at moving beyond undirected association networks toward directed graphical models. While a learned Bayesian network is not automatically causal, it gives a good starting point that can later be combined with prior knowledge and causal assumptions. Parameters were estimated using Gaussian maximum likelihood after learning the structure with the BIC score.
    </p>
  </div>

  <div class="artifact-figure">
    <img
      src="/assets/images/proteins_aic_mle_numbered_dag.png"
      alt="proteins_aic_mle_numbered_dag"
    >

    <p class="artifact-caption">
      As expected, AIC retured a denser graph than BIC as it less penalizes complexity. An interesting follow-up would be to compare directions and the parameter estimates for edges shared by both networks and investigate how sensitive they are to the choice of scoring criterion.
    </p>
  </div>

  <div class="artifact-figure">
    <img
      src="/assets/images/expanded_hillclimb_bic_network.png"
      alt="expanded_hillclimb_bic_network">

    <p class="artifact-caption">
      Expanded the node space from just proteins to phenotypes and activity nodes, which quickly highlighted the importance of incorporating prior knowledge. Without that, it also learns some obviouly wrong edges (for example edges from phenotype to proteins). Here, I've only constrained phenotypes to be terminal nodes, but other obvious forbidden edges should probably be included.
      
    </p>
  </div>

  <div class="artifact-figure">
    <img
      src="/assets/images/expanded_hillclimb_aic_network.png"
      alt="expanded_hillclimb_aic_network">

    <p class="artifact-caption">
      As expected, AIC produced a denser network. Still curious about when the additional complexity is justified and what criteria are most appropriate for choosing between AIC and the more conservative BIC.
    </p>
  </div>
</section>

<section class="artifacts">

  <h2>Constraint-based structure learning</h2>

  <div class="artifact-gallery">

  <div class="artifact-card">
  <img src="/assets/images/proteins_pc_network.png"
     alt="proteins_pc_network">

      <p>
        This was my first exploration of a constraint-based structure learning method. Haven't yet fully investigated the conditional independence tests though. Another question that caught my attention is how PC differs mathematically from Graphical Lasso, since both seem to rely on conditional independence in different ways. Something I'd like to understand better.
      </p>
  </div>

  <div class="artifact-card">
  <img src="/assets/images/expanded_pc_network.png"
     alt="expanded_pc_network">

      <p>
        Interestingly, some edge directions changed after including activity and phenotype nodes, suggesting that expanding the variable set can meaningfully alter the conditional independencies. Couldn't include the same prior constraints into the PC algorithm, which is something I'd like to revisit. 
      </p>
  </div>
  </div>
</section>