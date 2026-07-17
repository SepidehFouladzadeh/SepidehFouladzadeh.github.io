---
layout: exploration
title: "Understanding Reinforcement Learning Through the lense of Control Theory"
description: "Reinforcement learning seems to have similar concept as control theory. Curious where they overlap and where they fundamentally differ."
date: 2026-07-15
# reading_time: "1 min read"
linkedin_url: "https://www.linkedin.com/in/sepideh-fouladzadeh/"
permalink: /research/rl-vs-control/
---

<p class="flow-instruction">
  Hover over—or tap—each step to see what I explored and what question followed.
</p>

<div class="flow thought-flow">

  <!-- STEP 1 -->
  <div class="thought-step">
    <button class="flow-node thought-trigger" type="button">
      <h3>
        Reinforcement learning seems to pursue a similar goal to control theory.
      </h3>
      <p>
        Where do they overlap—and where do they fundamentally differ?
      </p>
    </button>

    <div class="thought-cloud">
      <h3>The question that started it</h3>

      <p>
        Both reinforcement learning and control theory involve acting on a
        system to influence its behavior.
      </p>

      <p>
        I wanted to understand 
      </p>
    </div>
  </div>

  <div class="flow-arrow"></div>


  <!-- STEP 2 -->
  <div class="thought-step">
    <button class="flow-node thought-trigger" type="button">
      <h3>Start with </h3>
    </button>

    <div class="thought-cloud">
      <h3>Why </h3>

      <p>
        I am
      </p>

      <p>
        Still, I enjoy beginning with 
      </p>
    </div>
  </div>

  <div class="flow-arrow"></div>


  <!-- STEP 3 -->
  <div class="thought-step">
    <button class="flow-node thought-trigger" type="button">
      <h3>Begin </h3>
      <p>Train </p>
    </button>

    <div class="thought-cloud">
      <h3>My first implementation</h3>

      <p>
        I began with 
      </p>

      <div class="thought-evidence">
        ✓ CartPole-v1<br>
        ✓ PPO<br>
      </div>

      <p>
        it did not yet explain
        what the learned policy was actually doing.
      </p>
    </div>
  </div>

  <div class="flow-arrow"></div>


  <!-- STEP 4 -->
  <div class="thought-step">
    <button class="flow-node thought-trigger" type="button">
      <h3>Two lines of curiosity appeared</h3>
    </button>

    <div class="thought-cloud">
      <h3>A natural split</h3>

      <p>
        One direction was to compare 
      </p>

      <p>
        The other was to look beneath
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
          <h3>How is </h3>
        </button>

        <div class="thought-cloud thought-cloud-left">
          <h3>Comparing </h3>

          <p>
            I compared 
          </p>

          <div class="thought-evidence">
            ✓ Angle-based controller<br>
          </div>

          <p>
            A controller may look
          </p>
        </div>
      </div>

      <div class="flow-arrow"></div>

      <div class="thought-step">
        <button class="flow-node thought-trigger" type="button">
          <h3>Can the learned policy </h3>
        </button>

        <div class="thought-cloud thought-cloud-left">
          <h3>Controller</h3>

          <p>
            collected 
          </p>

          <div class="thought-evidence">
            ✓ Policy
          </div>

          <p>
            interpreting what it had learned.
          </p>
        </div>
      </div>

    </div>


    <!-- RIGHT BRANCH -->
    <div class="branch">

      <div class="branch-line"></div>

      <div class="thought-step">
        <button class="flow-node thought-trigger" type="button">
          <h3>What assumptions are already hidden inside Gymnasium?</h3>
        </button>

        <div class="thought-cloud">
          <h3>Looking beneath </h3>

          <p>
            Gymnasium
          </p>

          <p>
            useful for benchmarking 
          </p>
        </div>
      </div>

      <div class="flow-arrow"></div>

      <div class="thought-step">
        <button class="flow-node thought-trigger" type="button">
          <h3>Can I derive and implement the dynamics myself?</h3>
        </button>

        <div class="thought-cloud">
          <h3>Moving one level lower</h3>

          <p>
            I wanted to understand 
          </p>

          <p>
            reproduce behavior comparable
            to the ready-made environment?
          </p>

          <p>
            unfinished
          </p>
        </div>
      </div>

    </div>

  </div>


  <!-- MERGE -->
  <div class="merge-connector">
    <div class="merge-line merge-left"></div>
    <div class="merge-line merge-right"></div>
    <div class="merge-stem"></div>
  </div>

  <div class="flow-merge">
    <div class="thought-step large-step">
      <button class="flow-node large thought-trigger" type="button">
        <h3>
          The problem shifted 
        </h3>
      </button>

      <div class="thought-cloud">
        <h3>A change in perspective</h3>

        <p>
          Algorithm design 
        </p>

        <p>
          The environment defines 
        </p>
      </div>
    </div>
  </div>

  <div class="flow-arrow"></div>


  <!-- STEP 5 -->
  <div class="thought-step">
    <button class="flow-node thought-trigger" type="button">
      <h3>Build a custom Gymnasium environment</h3>
    </button>

    <div class="thought-cloud">
      <h3>What I explored</h3>

      <div class="thought-evidence">
        ✓ Custom environment structure<br>
      </div>

      <p>
        Designing the reward led me toward questions about
      </p>
    </div>
  </div>

  <div class="flow-arrow"></div>


  <!-- STEP 6 -->
  <div class="thought-step">
    <button class="flow-node thought-trigger" type="button">
      <h3>What changes when the dynamics are only partially known?</h3>
    </button>

    <div class="thought-cloud">
      <h3>Beyond CartPole</h3>

      <p>
         mechanics are known.
        Biological systems are rarely so accommodating.
      </p>

      <p>
        In complex systems
      </p>
    </div>
  </div>

  <div class="flow-arrow"></div>


  <!-- STEP 7 -->
  <div class="thought-step">
    <button class="flow-node thought-trigger" type="button">
      <h3>
        What if 
      </h3>
    </button>

    <div class="thought-cloud">
      <h3>Internal and external unknowns</h3>

      <p>
        may not have cleanly defined states,
      </p>

      <p>
        The uncertainty
      </p>
    </div>
  </div>

  <div class="flow-arrow"></div>


  <!-- STEP 8 -->
  <div class="thought-step">
    <button class="flow-node thought-trigger" type="button">
      <h3>How should we reason</h3>
    </button>

    <div class="thought-cloud">
      <h3>Representing uncertainty explicitly</h3>

      <p>
        Rather than pretending the model is exact, one possibility is
      </p>

      <div class="belief-flow">
        <span>Prior beliefs</span>
        <strong>→</strong>
        <span>Observed evidence</span>
        <strong>→</strong>
        <span>Updated beliefs</span>
      </div>

      <p>
        This is where
      </p>
    </div>
  </div>

  <div class="flow-arrow"></div>


  <!-- STEP 9 -->
  <div class="thought-step">
    <button class="flow-node thought-trigger" type="button">
      <h3>
        Or should
      </h3>
    </button>

    <div class="thought-cloud">
      <h3>Robustness</h3>

      <p>
        Another possibility 
      </p>

      <p>
        This naturally brings me back toward 
      </p>
    </div>
  </div>

  <div class="flow-arrow"></div>


  <!-- STEP 10 -->
  <div class="thought-step">
    <button class="flow-node thought-trigger" type="button">
      <h3>
        If RL can 
      </h3>
    </button>

    <div class="thought-cloud">
      <h3>The question I am returning to</h3>

      <p>
        Reinforcement learning can learn 
      </p>

      <p>
        I am curious about 
      </p>
    </div>
  </div>

</div>