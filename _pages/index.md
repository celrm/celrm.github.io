---
layout: default
title: Home
titlealt: About me
permalink: /
order: 1
---

I am a PhD candidate at the [Relational ML Lab](https://relationalml.github.io) since 2023, supervised by [Dr. Rebekka Burkholz](https://sites.google.com/view/rebekkaburkholz/) at the [CISPA](https://cispa.de) Helmholtz Center for Information Security in Saarland, Germany.

My <a href="/research/" target="_self">research</a> addresses generalization challenges in graph learning, particularly by studying the dual role of input graphs as both data and computation structures, and the effects of modifying them under different criteria. The work has been published at [NeurIPS](https://openreview.net/forum?id=EMkrwJY2de) and [ICLR](https://openreview.net/forum?id=g6v09VxgFw), and presented at multiple <a href="/talks/" target="_self">talks</a>.

### Background

I hold degrees in Mathematics and Computer Science from Universidad Complutense de Madrid, and I received the prestigious [postgraduate fellowship](https://becarios.fundacionlacaixa.org/en/celia-rubio-madrigal-B005794) from la Caixa Foundation in 2022. This allowed me to study a master's at Strathclyde in the UK, where I was awarded the Best Overall Performance Prize. 
I have been featured in the [Nova 111 Student List 2023](https://www.novatalent.com/111/spain/student-list/2023) (top 10 under 25 in Computer Science in Spain) and selected for the [9th Heidelberg Laureate Forum](https://scilogs.spektrum.de/hlf/hlff-spotlight-9th-hlf/) 2022, where I was also interviewed.
Beyond research, I annually contribute to the European Girls' Mathematical Olympiad ([EGMO](https://www.egmo.org/person933/)) as a permanent member of the IT team. I also developed the LaTeX package [ddphonism](https://ctan.org/pkg/ddphonism), which is included in MikTeX and the TeXLive Music bundle.

You can read my full [CV](/assets/pdf/RubioMadrigalCelia_cv.pdf), or explore a <a href="/timeline/" target="_self">timeline</a> of my past activities.

## News

{% for milestone in site.data.news.list %}
{% for item in milestone.details %}
{% if item.new %}
* {{ item.date }}｜{{ item.description | markdownify | remove: '<p>' | remove: '</p>' }}
{% endif %}
{% endfor %}
{% endfor %}
