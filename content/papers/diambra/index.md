---
title: "DIAMBRA Arena: a New Reinforcement Learning Platform for Research and Experimentation"
authors:
- admin
author_notes:
date: "2022-10-19T00:00:00Z"
doi: "https://doi.org/10.48550/arXiv.2210.10595"

# Publication type.
# Accepts a single type but formatted as a YAML list (for Hugo requirements).
# Enter a publication type from the CSL standard.
publication_types: ["article"]

# Publication name and optional abbreviated publication name.
publication: "*arXiv preprint (cs.LG)*"
publication_short: "*arXiv preprint (cs.LG)*"

abstract: |
  The recent advances in reinforcement learning have led to effective methods able to obtain above human-level performances in very complex environments. However, once solved, these environments become less valuable, and new challenges with different or more complex scenarios are needed to support research advances.

  This work presents DIAMBRA Arena, a new platform for reinforcement learning research and experimentation, featuring a collection of high-quality environments exposing a Python API fully compliant with OpenAI Gym standard. They are episodic tasks with discrete actions and observations composed by raw pixels plus additional numerical values, all supporting both single player and two players mode, allowing to work on standard reinforcement learning, competitive multi-agent, human-agent competition, self-play, human-in-the-loop training and imitation learning. Software capabilities are demonstrated by successfully training multiple deep reinforcement learning agents with proximal policy optimization obtaining human-like behavior.

  Results confirm the utility of DIAMBRA Arena as a reinforcement learning research tool, providing environments designed to study some of the most challenging topics in the field.

# Summary. An optional shortened abstract.
#summary: Lorem ipsum dolor sit amet, consectetur adipiscing elit. Duis posuere tellus ac convallis placerat. Proin tincidunt magna sed ex sollicitudin condimentum.

tags:
- Reinforcement Learning
- Transfer Learning
- Multi-agent
- Games
featured: false

links:
- name: 'Project'
  url: '/projects/01-diambra'
url_pdf: https://arxiv.org/pdf/2210.10595
url_code: 'https://github.com/diambra'
url_dataset: ''
url_poster: ''
url_project: ''
url_slides: ''
url_source: ''
url_video: 'https://www.youtube.com/watch?v=dw72POyqcqk'

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
image:
  caption: 'Model architecture scheme'
  focal_point: ""
  preview_only: false

# Associated Projects (optional).
#   Associate this publication with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `internal-project` references `content/project/internal-project/index.md`.
#   Otherwise, set `projects: []`.
projects: [01-diambra]

# Slides (optional).
#   Associate this publication with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides: "example"` references `content/slides/example/index.md`.
#   Otherwise, set `slides: ""`.
#slides: example
---