---
layout: default
title: Home
titlealt: About me
permalink: /
order: 1
---

I am a PhD candidate at the [Relational ML Lab](https://relationalml.github.io), under the supervision of [Dr. Rebekka Burkholz](https://sites.google.com/view/rebekkaburkholz/), at the CISPA Helmholtz Center for Information Security in Saarland, Germany.

I am interested in the theory of machine learning, with a focus on addressing the challenges of generalization in graph learning. Most recently, I have been looking into the dual role of input graphs as both data and computational models in graph neural networks, and the implications of rewiring them under different criteria.

You can read my CV [here](/assets/pdf/RubioMadrigalCelia_cv.pdf).

## News

{% for milestone in site.data.news.list %}
{% for item in milestone.details %}
{% if item.new %}
* {{ item.date }}: {{ item.description | markdownify | remove: '<p>' | remove: '</p>' }}
{% endif %}
{% endfor %}
{% endfor %}
