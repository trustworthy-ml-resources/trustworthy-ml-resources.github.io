---
layout: distill
title: conference 1
description: Location
date: 2022-03-01

authors:
  - name: Prof. Dr. Funtimes
    url: "https://en.wikipedia.org/wiki/Albert_Einstein"
    affiliations:
      name: Departement of Jokes, University of Fun Times
  - name: Boris Podolsky
    url: "https://en.wikipedia.org/wiki/Boris_Podolsky"
    affiliations:
      name: Departement of Jokes, University of Fun Times

bibliography: 2022-03-01.bib

# Optionally, you can add a table of contents to your post.
# NOTES:
#   - make sure that TOC names match the actual section names
#     for hyperlinks within the post to work correctly.
#   - we may want to automate TOC generation in the future using
#     jekyll-toc plugin (https://github.com/toshimaru/jekyll-toc).
toc:
  - name: fairness
    # if a section has subsections, you can add them as follows:
    # subsections:
    #   - name: Example Child Subsection 1
    #   - name: Example Child Subsection 2
  - name: robustness
  - name: privacy
  - name: explainability
  - name: causality
  - name: misc

---
## fairness
<div class="publications">

{%- for y in page.years %}
  <h2 class="year">{{y}}</h2>
  {% bibliography -f conferences/conference_1/papers_1 -q @*[year={{y}}]* %}
{% endfor %}

</div>
## robustness
## privacy
## explainability
## causality
## misc