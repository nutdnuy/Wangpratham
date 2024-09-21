---
title: "Wang–Landau Sampling for Estimation of the Reliability of Physical Networks"
authors:
- Wanyok Atisattapong
- admin
date: "2021-06-24T00:00:00Z"
doi: "https://doi.org/10.1016/j.cpc.2021.107831"


# Publication type.
# Accepts a single type but formatted as a YAML list (for Hugo requirements).
# Enter a publication type from the CSL standard.
publication_types: ["article-journal"]

# Publication name and optional abbreviated publication name.
publication: "*Computer Physics Communications, 262, 2021*"
publication_short: ""

abstract: Modern physical networks, for example in communication and transportation, can be interpreted as directed graphs. Network models are used to identify the probability that given nodes are connected, and therefore the effect of a failure at a given link. This is essential for network design, optimization, and reliability. In this study, we investigated three alternative ensembles for estimating network reliability using the Wang–Landau algorithm. The first performed random walks on a structure function having two possible states, connected and disconnected. The second used random walks on a reliability polynomial. The third combined random walks with the average of connecting probabilities. The accuracy and limitations of the three ensembles were compared by estimating the reliability of three network models a bridge network, a ladder-type network, and a dodecahedron network. The simulation results showed that the use of a random walk on a structure function failed to produce estimates when applied to highly reliable networks in any of the three network types. The other two approaches performed efficiently for bridge or ladder-type networks at any level of network reliability. The random walk on a probability space using the 1/t algorithm was the only ensemble that was able to yield accurate estimates for a dodecahedron network, though even this failed at the highest level of network reliability. The other two methods failed to converge within 108 Monte Carlo trials. The use of the average of connecting probabilities required a shorter computation time when applied to a large network. Methods that can reduce variance for large, highly reliable networks require further investigation.
# Summary. An optional shortened abstract.
summary: 

tags:
- Monte Carlo Method
- Simulation
- Network
featured: false
# links:
# - name: ""
#   url: ""
url_pdf: https://www.sciencedirect.com/science/article/abs/pii/S0010465521000059
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
  caption: 'Image credit: [**Unsplash**](https://unsplash.com/photos/jdD8gXaTZsc)'
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
slides: example
---


