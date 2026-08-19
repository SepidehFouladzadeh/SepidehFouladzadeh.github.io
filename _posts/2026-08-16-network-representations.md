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
      <strong>proteins_bic_mle_numbered_dag</strong>
      This was my first attempt at moving beyond undirected association networks toward directed graphical models. While a learned Bayesian network is not automatically causal, it gives a good starting point that can later be combined with prior knowledge and causal assumptions. Parameters were estimated using Gaussian maximum likelihood after learning the structure with the BIC score.
    </p>
  </div>

  <div class="artifact-figure">
    <img
      src="/assets/images/proteins_aic_mle_numbered_dag.png"
      alt="proteins_aic_mle_numbered_dag"
    >

    <p class="artifact-caption">
      <strong>proteins_aic_mle_numbered_dag</strong>
      As expected, AIC retured a denser graph than BIC as it less penalizes complexity. An interesting follow-up would be to compare directions and the parameter estimates for edges shared by both networks and investigate how sensitive they are to the choice of scoring criterion.
    </p>
  </div>

  <div class="artifact-figure">
    <img
      src="/assets/images/expanded_hillclimb_bic_network.png"
      alt="expanded_hillclimb_bic_network"
    >

    <p class="artifact-caption">
      <strong>expanded_hillclimb_bic_network</strong>
      Expanded the node space from just proteins to phenotypes and activity nodes, which quickly highlighted the importance of incorporating prior knowledge. Without that, it also learns some obviouly wrong edges (for example edges from phenotype to proteins). Here, I've only constrained phenotypes to be terminal nodes, but other obvious forbidden edges should probably be included.
      
    </p>
  </div>

  <div class="artifact-figure">
    <img
      src="/assets/images/expanded_hillclimb_aic_network.png"
      alt="expanded_hillclimb_aic_network"
    >

    <p class="artifact-caption">
      <strong>expanded_hillclimb_aic_network</strong>
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