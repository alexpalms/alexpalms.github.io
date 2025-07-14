---
title: "Deep Learning Computer Vision Algorithms for Real-time UAVs On-board Camera Image Processing"
authors:
- admin
- Pietro Andronico
author_notes:
date: "2022-04-26T00:00:00Z"
doi: "https://doi.org/10.48550/arXiv.2211.01037"

# Publication type.
# Accepts a single type but formatted as a YAML list (for Hugo requirements).
# Enter a publication type from the CSL standard.
publication_types: ["paper-conference"]

# Publication name and optional abbreviated publication name.
publication: "*NATO AVT-353 Research Workshop \"Artificial Intelligence in Cockpits for UAVs\", Turin, Italy, 26 April 2022*"
publication_short: "*NATO AVT-353 Research Workshop \"Artificial Intelligence in Cockpits for UAVs\"*"

abstract: "This paper describes how advanced deep learning based computer vision algorithms are applied to enable real-time on-board sensor processing for small UAVs. Four use cases are considered: target detection, classification and localization, road segmentation for autonomous navigation in GNSS-denied zones, human body segmentation, and human action recognition. All algorithms have been developed using state-of-the-art image processing methods based on deep neural networks. Acquisition campaigns have been carried out to collect custom datasets reflecting typical operational scenarios, where the peculiar point of view of a multi-rotor UAV is replicated. Algorithms architectures and trained models performances are reported, showing high levels of both accuracy and inference speed. Output examples and on-field videos are presented, demonstrating models operation when deployed on a GPU-powered commercial embedded device (NVIDIA Jetson Xavier) mounted on board of a custom quad-rotor, paving the way to enabling high level autonomy."

# Summary. An optional shortened abstract.
#summary: Lorem ipsum dolor sit amet, consectetur adipiscing elit. Duis posuere tellus ac convallis placerat. Proin tincidunt magna sed ex sollicitudin condimentum.

tags:
 - Computer Vision
 - Object Detection Classification and Localization
 - Semantic Segmentation
 - Human Action Recognition
 - UAV
featured: false

# links:
# - name: ""
#   url: ""
url_pdf: https://arxiv.org/pdf/2211.01037
url_code: ''
url_dataset: ''
url_poster: ''
url_project: ''
url_slides: ''
url_source: ''
url_video: 'https://www.youtube.com/watch?v=AObXkNNc-ps'

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
image:
  caption: 'Layer freezing for transfer learning and fine-tuning'
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