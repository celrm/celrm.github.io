---
layout: default
title: Home
titlealt: About me
permalink: /
order: 1
---

I am a PhD candidate at the [Relational ML Lab](https://relationalml.github.io), supervised by [Dr. Rebekka Burkholz](https://sites.google.com/view/rebekkaburkholz/) at [CISPA Helmholtz Center for Information Security](https://cispa.de) in Saarland, Germany.

My research focuses on machine learning for structured data. I am particularly interested in how input structures shape both data representation and computation, with broader interests in graph learning, generalization trade-offs, and architectural efficiency. My work has been published at [NeurIPS](https://openreview.net/forum?id=EMkrwJY2de), [ICLR](https://openreview.net/forum?id=g6v09VxgFw), and [ICML](https://openreview.net/forum?id=gSZhNPp103), and presented in multiple <a href="/talks/" target="_self">talks and posters</a>.

### Background

I hold degrees in Mathematics and Computer Science from Universidad Complutense de Madrid. In 2022, I received a [postgraduate fellowship](https://becarios.fundacionlacaixa.org/en/celia-rubio-madrigal-B005794) from la Caixa Foundation, which supported my master's studies at the University of Strathclyde in the UK, where I was awarded the Departmental Best Overall Performance Prize.

I was featured on the [Nova 111 Student List 2023](https://www.novatalent.com/111-list/student-spain-2023) as one of the top 10 under 25 in Computer Science in Spain. I have also been selected twice for the Heidelberg Laureate Forum: the 13th edition in 2026 and the [9th edition](https://scilogs.spektrum.de/hlf/hlff-spotlight-9th-hlf/) in 2022, where I was interviewed.

Beyond research, I annually support the European Girls' Mathematical Olympiad ([EGMO](https://www.egmo.org/people/person933/)) as part of the IT team with [Joseph Myers](https://www.polyomino.org.uk/) since 2023. In 2019, I developed [ddphonism](https://ctan.org/pkg/ddphonism), a LaTeX package for twelve-tone music notation.

My CV is available [here](/assets/pdf/RubioMadrigalCelia_cv.pdf).

### Upcoming news

{% for milestone in site.data.news.list %}
{% for item in milestone.details %}
{% if item.new %}
* {{ item.date }}｜{{ item.description | markdownify | remove: '<p>' | remove: '</p>' }}
{% endif %}
{% if item.future %}

### Recent news
{% endif %}
{% endfor %}
{% endfor %}

Older events are shown in the <a href="/timeline/" target="_self">timeline</a>.