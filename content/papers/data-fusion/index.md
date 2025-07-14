---
title: "Data Fusion Algorithms to Improve Test Range Sensors Accuracy and Precision"
authors:
- Alessandro Urru
- Davide Piras
- admin
author_notes:
date: "2019-02-15T00:00:00Z"
doi: "https://doi.org/10.1109/ICORT46471.2019.9069667"

# Publication type.
# Accepts a single type but formatted as a YAML list (for Hugo requirements).
# Enter a publication type from the CSL standard.
publication_types: ["paper-conference"]

# Publication name and optional abbreviated publication name.
publication: "*2019 International Conference on Range Technology (ICORT)*"
publication_short: "*2019 International Conference on Range Technology (ICORT)*"

abstract: "Data fusion technology is used in many research areas, such as image processing, automotive, robotics, defense and aerospace. The need to fuse data from different sensors reflects the demand for enhanced measurements precision. Every sensor has pro and cons, data fusion technology for tracking purposes in a test range is supposed to leverage the highest quality features of each sensor to obtain a better position estimation. This paper presents NT multi-sensor tracking algorithm, it is developed to receive target position information from different tracking sensors, radar and electro-optical, and use data fusion technology to obtain better quality data compared to the one provided by a single sensor alone. The algorithm uses a fusion technique which permits a huge performance boost: it associates a weight to every sensor calculated using Kalman filters, properly modeled, to estimate sensor measurements deviations from the estimated target position. These weights help the algorithm understanding which sensor is more reliable and to estimate the best possible position, which is very close to the real target position. Real case tracking scenarios are presented, where the algorithm is tested and compared with reference trajectory data to estimate its accuracy."

# Summary. An optional shortened abstract.
#summary: Lorem ipsum dolor sit amet, consectetur adipiscing elit. Duis posuere tellus ac convallis placerat. Proin tincidunt magna sed ex sollicitudin condimentum.

tags:
 - Data Integration
 - Sensor Fusion
 - Trajectory
 - Radar Tracking
 - Covariance Matrices
 - Real-Time

featured: false

# links:
# - name: ""
#   url: ""
url_pdf: https://ieeexplore.ieee.org/document/9069667
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
  caption: 'Error probability distribution - Three radars scenario'
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