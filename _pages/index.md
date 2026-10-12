---
layout: default
title: Home
titlealt: About me
permalink: /
order: 1
---

I am a PhD candidate at [CISPA Helmholtz Center for Information Security](https://cispa.de) in Saarland, Germany, supervised by [Dr. Rebekka Burkholz](https://scholar.google.com/citations?user=vkWBb2wAAAAJ) at the [Relational ML Lab](https://relationalml.github.io).

I study ways to improve the generalization of graph neural networks (GNNs), with a focus on how graph structure and depth affect their behavior in theory and practice. I have worked on directions such as rewiring, tabularization, and knowledge distillation, with an emphasis on empirical evaluation and testing the limits of common assumptions. More broadly, I am interested in developing architectures that balance the trade-offs between expressiveness, efficiency, and generalization; in this regard, I have collaborated on broader topics such as tabular model robustness and optimization. My work has been published at NeurIPS, ICLR, and ICML [[1](/research#bib-spectral-graph-pruning), [2](/research#bib-gnns-getting-comfy), [3](/research#bib-fixed-aggregation-features)] and presented in several <a href="/talks/" target="_self">talks and workshops</a>.

My CV is available [here](/assets/pdf/RubioMadrigalCelia_cv.pdf).

### Background

I obtained two undergraduate degrees in Mathematics and Computer Science from Universidad Complutense de Madrid. Afterwards, I was awarded a [postgraduate fellowship](https://becarios.fundacionlacaixa.org/en/celia-rubio-madrigal-B005794) from la Caixa Foundation, which fully supported my master's studies at the University of Strathclyde in the UK, where I was awarded the Departmental Best Overall Performance Prize.

Since 2023, I annually attend the European Girls' Mathematical Olympiad ([EGMO](https://www.egmo.org/people/person933/)) as IT support with [Joseph Myers](https://www.polyomino.org.uk/). I have been selected twice for the Heidelberg Laureate Forum: in 2022 and in 2026. I have also developed two music notation packages for LaTeX: [mousik](https://ctan.org/pkg/mousik) (2026) and [ddphonism](https://ctan.org/pkg/ddphonism) (2019).

### Upcoming

{% for milestone in site.data.news.list %}
{% for item in milestone.details %}
{% if item.new %}
* {{ item.date }}｜{{ item.description | markdownify | remove: '<p>' | remove: '</p>' }}
{% endif %}
{% if item.future %}

### Recent
{% endif %}
{% endfor %}
{% endfor %}

Older events are shown in the <a href="/timeline/" target="_self">timeline</a>.