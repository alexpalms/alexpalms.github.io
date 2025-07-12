---
title: "Performance Index of a Network of Ground-Based Optical Sensors for Space Objects Observation and Measurements"
authors:
- Alessandro Urru
- Michele Spanu
- Enrico Congiu
- admin
- Pietro Andronico
author_notes:
date: "2023-08-10T00:00:00Z"
doi: "https://doi.org/10.1016/j.asr.2023.08.013"

# Publication type.
# Accepts a single type but formatted as a YAML list (for Hugo requirements).
# Enter a publication type from the CSL standard.
publication_types: ["article-journal"]

# Publication name and optional abbreviated publication name.
publication: "*Advances in Space Research, Volume 72, Issue 10, 15 November 2023, Pages 4147-4156*"
publication_short: "*Advances in Space Research*"

abstract: The paper proposes an algorithm to estimate the performance of a globally-distributed network of optical assets, equipped with off-the-shelf components, deployed in multiple sites distributed across different locations. The quantitative performance measure is calculated as the portion of total cataloged debris that is visible by the network in a 24 hours time window, considering space objects of size down to 3 cm. The proposed algorithm takes as input all objects of the NORAD catalog, the whole set of objects’ physical data provided by the DISCOS and SATCAT catalogs, and optical and atmospheric data. It then propagates the space object population to obtain their position in the selected time window, filters out all the objects that are not in the ground station network line-of-sight for a sufficient amount of time to guarantee a feasible orbit determination, and on the remaining ones it estimates the signal-to-noise Ratio achievable by the assets, leveraging an advanced algorithm that models their optical performance. These values are directly translated into a probability of detection, thus providing a performance index for the given ground sensor network configuration that can be used as an objective function to be optimized when evaluating different architectures.

# Summary. An optional shortened abstract.
#summary: Lorem ipsum dolor sit amet, consectetur adipiscing elit. Duis posuere tellus ac convallis placerat. Proin tincidunt magna sed ex sollicitudin condimentum.

tags:
- Space situational awareness
- Ground-based telescopes
- Space debris
- Optics system
featured: false

# links:
# - name: ""
#   url: ""
url_pdf: https://www.sciencedirect.com/science/article/abs/pii/S0273117723006324
url_code: ''
url_dataset: ''
url_poster: ''
url_project: ''
url_slides: ''
url_source: ''
url_video: ''

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
image:
  caption: 'Detection probability as a function of orbiting object altitude and size'
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