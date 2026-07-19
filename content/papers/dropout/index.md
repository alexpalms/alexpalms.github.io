---
title: "Language Models Recognize Dropout and Gaussian Noise Applied to Their Activations"
authors:
- Damiano Fornasiere
- Mirko Bronzi
- Spencer Kitts
- admin
- Yoshua Bengio
- Oliver Richardson
author_notes:
date: "2026-04-19T00:00:00Z"
doi: "https://doi.org/10.48550/arXiv.2604.17465"

# Publication type.
# Accepts a single type but formatted as a YAML list (for Hugo requirements).
# Enter a publication type from the CSL standard.
publication_types: ["article"]

# Publication name and optional abbreviated publication name.
publication: "*arXiv preprint (cs.AI)*"
publication_short: "*arXiv preprint (cs.AI)*"

abstract: |
  We provide evidence that language models can detect, localize and, to a certain degree, verbalize the difference between perturbations applied to their activations. More precisely, we either (a) mask activations, simulating dropout, or (b) add Gaussian noise to them, at a target sentence. We then ask a multiple-choice question such as "Which of the previous sentences was perturbed?" or "Which of the two perturbations was applied?".

  We test models from the Llama, Olmo, and Qwen families, with sizes between 8B and 32B, all of which can easily detect and localize the perturbations, often with perfect accuracy. These models can also learn, when taught in context, to distinguish between dropout and Gaussian noise. Notably, Qwen3-32B's zero-shot accuracy in identifying which perturbation was applied improves as a function of the perturbation strength and, moreover, decreases if the in-context labels are flipped, suggesting a prior for the correct ones—even modulo controls.

  Because dropout has been used as a training-regularization technique, while Gaussian noise is sometimes added during inference, we discuss the possibility of a data-agnostic "training awareness" signal and the implications for AI safety.

# Summary. An optional shortened abstract.
#summary: Lorem ipsum dolor sit amet, consectetur adipiscing elit. Duis posuere tellus ac convallis placerat. Proin tincidunt magna sed ex sollicitudin condimentum.

tags:
- Introspection
- Dropout
- Gaussian Noise
- Language Models
- AI Safety
- Mechanistic Interpretability

featured: false

links:
- name: 'Project'
  url: 'https://saifh-github.github.io/llm-dropout-noise-recognition/'
url_pdf: https://arxiv.org/pdf/2604.17465
url_code: 'https://github.com/saifh-github/llm-dropout-noise-recognition'
url_dataset: ''
url_project: ''
url_slides: ''
url_source: ''
url_video: ''

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
image:
  caption: ''
  focal_point: ""
  preview_only: false

# Associated Projects (optional).
#   Associate this publication with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `internal-project` references `content/project/internal-project/index.md`.
#   Otherwise, set `projects: []`.
projects: []

# Slides (optional).
#   Associate this publication with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides: "example"` references `content/slides/example/index.md`.
#   Otherwise, set `slides: ""`.
#slides: example
---
