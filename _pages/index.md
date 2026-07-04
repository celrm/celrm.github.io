---
layout: default
title: Home
titlealt: About me
permalink: /
order: 1
---

I am a PhD candidate at the [Relational ML Lab](https://relationalml.github.io), supervised by [Dr. Rebekka Burkholz](https://scholar.google.com/citations?user=vkWBb2wAAAAJ) at [CISPA Helmholtz Center for Information Security](https://cispa.de) in Saarland, Germany.

I study ways to improve the generalization of graph neural networks (GNNs), with a focus on how graph structure and depth affect their behavior in theory and practice. I have worked on directions such as rewiring, tabularization, and knowledge distillation, with an emphasis on empirical evaluation and testing the limits of common assumptions. More broadly, I am interested in developing architectures that balance the trade-offs between expressiveness, efficiency, and generalization; in this regard, I have collaborated on broader topics such as tabular robustness and optimization. My work has been published at NeurIPS, ICLR, and ICML [[1](/research#bib-spectral-graph-pruning), [2](/research#bib-gnns-getting-comfy), [3](/research#bib-fixed-aggregation-features)] and presented in several <a href="/talks/" target="_self">talks and workshops</a>.

### Background

I hold degrees in Mathematics and Computer Science from Universidad Complutense de Madrid. In 2022, I was awarded a [postgraduate fellowship](https://becarios.fundacionlacaixa.org/en/celia-rubio-madrigal-B005794) from la Caixa Foundation, which fully supported my master's studies at the University of Strathclyde in the UK, where I was awarded the Departmental Best Overall Performance Prize. 

I was featured on the [Nova 111 Student List 2023](https://www.novatalent.com/111-list/student-spain-2023) as one of the top 10 under 25 in Computer Science in Spain. I have also been selected twice for the Heidelberg Laureate Forum: the 13th edition in 2026 and the 9th edition in 2022, where I was [interviewed](https://scilogs.spektrum.de/hlf/hlff-spotlight-9th-hlf/). 


Beyond research, I annually attend the European Girls' Mathematical Olympiad ([EGMO](https://www.egmo.org/people/person933/)) as part of the IT team with [Joseph Myers](https://www.polyomino.org.uk/) since 2023. In 2019, I developed a LaTeX/tikz package for twelve-tone music notation called [ddphonism](https://ctan.org/pkg/ddphonism).

My CV is available [here](/assets/pdf/RubioMadrigalCelia_cv.pdf).

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