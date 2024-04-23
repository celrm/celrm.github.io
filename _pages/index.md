---
layout: default
title: Home
titlealt: About me
permalink: /
order: 1
---

I am a PhD candidate at the [Relational ML Lab](https://relationalml.github.io), supervised by [Dr. Rebekka Burkholz](https://sites.google.com/view/rebekkaburkholz/), at the CISPA Helmholtz Center for Information Security in Saarland, Germany. I am interested in the theory of machine learning, with a recent focus on addressing the challenges of generalization in graph learning.

You can find my CV [here](/assets/RubioMadrigalCelia_cv.pdf).

## News

{% for milestone in site.data.news.list %}
{% for item in milestone.details %}
{% if item.new %}
* {{ item.date }}: {{ item.event | markdownify | remove: '<p>' | remove: '</p>' }}
{% endif %}
{% endfor %}
{% endfor %}
