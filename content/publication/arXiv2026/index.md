---
abstract: Deep generative models are increasingly used as simulators for
  downstream decision-making under data scarcity, but in risk-sensitive
  applications their usefulness depends on rare adverse scenarios rather than
  typical samples. Standard generative objectives prioritize bulk distributional
  fidelity, leaving low-probability tails vulnerable to localized optimization
  noise and making tail-dependent functionals unstable under finite simulation
  budgets. We introduce Diachronic Sample Integration (DSI), a test-time
  inference framework that ensembles generated samples across checkpoints from a
  stochastic training trajectory. DSI targets a checkpoint-mixture distribution
  that averages checkpoint-specific tail fluctuations rather than relying on a
  single brittle endpoint. We formalize this mechanism through a finite-budget
  bias-variance theory. Empirically, across multivariate synthetic processes and
  high-frequency trading data, DSI substantially reduces tail-estimation error
  compared to single-checkpoint baselines under fixed simulation budgets,
  outperforming standard diffusion and state-of-the-art tail-aware baselines
  without modifying the generative objective.
slides: ""
url_pdf: https://arxiv.org/pdf/2607.10810
publication_types:
  - "Preprint"
authors:
  - admin
  - patrick-wong
  - Leran Zhang
  - Xiaolin Hu
author_notes: []
publication: arXiv preprint
summary: ""
url_dataset: ""
url_project: ""
publication_short: ""
url_source: https://arxiv.org/abs/2607.10810
url_video: ""
title: "Diachronic Sample Integration: Robust Tail-Risk Estimation with
  Generative Models"
doi: ""
featured: true
tags:
  - Generative Models
  - Tail Risk
  - Risk Management
  - Diffusion Models
projects: []
image:
  caption: ""
  focal_point: ""
  preview_only: false
date: 2026-07-12T00:00:00.000Z
url_slides: ""
publishDate: 2026-07-12T00:00:00.000Z
url_poster: ""
url_code: ""
---
