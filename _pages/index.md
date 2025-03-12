---
layout: default
title: Home
titlealt: About me
permalink: /
order: 1
---

I am a second-year PhD candidate at the [Relational ML Lab](https://relationalml.github.io), supervised by [Dr. Rebekka Burkholz](https://sites.google.com/view/rebekkaburkholz/), at the [CISPA](https://cispa.de) Helmholtz Center for Information Security in Saarland, Germany.

My <a href="/research/" target="_self">research</a> addresses generalization challenges in graph learning, particularly by studying the dual role of input graphs as both data and computation structures, and the effects of modifying them under different criteria. The work has been published at [NeurIPS](https://openreview.net/forum?id=EMkrwJY2de) and [ICLR](https://openreview.net/forum?id=g6v09VxgFw), and presented at multiple <a href="/talks/" target="_self">talks</a>: [HAICON](https://eventclass.it/haic2024/scientific/external-program/session?s=S-05a), [Cohere4AI](https://cohere.com/events/cohere-for-ai-Celia-Rubio-Madrigal-2025), NetSci.

### Background

I hold two degrees in Mathematics and Computer Science from Universidad Complutense de Madrid, and I received the prestigious [postgraduate fellowship](https://becarios.fundacionlacaixa.org/en/celia-rubio-madrigal-B005794) from la Caixa Foundation in 2022. This allowed me to study a master's at Strathclyde in Glasgow, UK, where I was awarded the Best Overall Performance Prize.
I annually participate in organizing the European Girls' Mathematical Olympiad ([EGMO](https://www.egmo.org/person933/)) as part of the IT team. I was featured in the [Nova 111 Student List 2023](https://www.novatalent.com/111/spain/student-list/2023) (top 10 under 25 in Computer Science in Spain). I was selected to attend the [9th Heidelberg Laureate Forum](https://scilogs.spektrum.de/hlf/hlff-spotlight-9th-hlf/) 2022, where I was also personally interviewed. Finally, I once published a LaTeX package, [ddphonism](https://ctan.org/pkg/ddphonism), which is included in MikTeX and the TeXLive Music bundle.

You can also read my full [CV](/assets/pdf/RubioMadrigalCelia_cv.pdf), or see a <a href="/timeline/" target="_self">timeline</a> of my past activities. Feel free to write to me about: complex networks + ML, LaTeX/TikZ figures, mentoring & women in STEM, mathematics olympiads, and Baroque/early music (good taste).

## News

{% for milestone in site.data.news.list %}
{% for item in milestone.details %}
{% if item.new %}
* {{ item.date }}｜{{ item.description | markdownify | remove: '<p>' | remove: '</p>' }}
{% endif %}
{% endfor %}
{% endfor %}
