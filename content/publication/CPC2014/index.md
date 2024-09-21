---
title: "A 1/t algorithm with the density of two states for estimating multidimensional integrals"
authors:
- Wanyok Atisattapong
- admin
date: "2017-11-01T00:00:00Z"
doi: "https://doi.org/10.1016/j.eneco.2024.107724"

# Schedule page publish date (NOT publication's date).
publishDate: "2017-01-01T00:00:00Z"

# Publication type.
# Accepts a single type but formatted as a YAML list (for Hugo requirements).
# Enter a publication type from the CSL standard.
publication_types: ["article-journal"]

# Publication name and optional abbreviated publication name.
publication: "*Computer Physics Communications, 220, 122-128, 2017*"
publication_short: ""

abstract: In this work we developed a 1/t algorithm for numerical integration in high dimensions. A large amount of computation time is wasted when a random walker is unable to reach a rare state at the sharp peak of an integrand, and becomes trapped after falling through that state. In this study, the density of states was divided into only two levels by sampling an arbitrary point in the range of the integrand, rather than into many levels using a fixed bin width (grid discretization on continuous space). The technique is quite straightforward and easy to implement. It avoids the need to determine the exact boundaries of the integrand, which is often a non-trivial task. Simulations show that our method is able to significantly reduce the number of Monte Carlo trials required, and therefore the simulation time. The potential of the proposed method was demonstrated by application to two multidimensional integrals, the Gaussian ring and the setting sun Feynman diagram. The results confirm that the proposed method can be applied to the calculation of multidimensional integrals without error saturation, yielding accurate values in applications where other numerical methods fail.
# Summary. An optional shortened abstract.
summary: 

tags:
- Monte Carlo Method
- Simulation
- Numerical Integration
featured: false
# links:
# - name: ""
#   url: ""
url_pdf: https://www.sciencedirect.com/science/article/abs/pii/S0010465517302060
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





