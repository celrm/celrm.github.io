---
layout: default
title: Home
titlealt: About me
permalink: /
order: 1
---

I am a second-year PhD candidate at the [Relational ML Lab](https://relationalml.github.io), under the supervision of [Dr. Rebekka Burkholz](https://sites.google.com/view/rebekkaburkholz/), at the CISPA Helmholtz Center for Information Security in Saarland, Germany. My <a href="/research/" target="_self">research</a> focuses on generalization challenges in graph learning, particularly how input graphs serve as both data and computational models, and the implications of modifying them under different criteria. 

I hold two degrees in Mathematics and Computer Science from Universidad Complutense de Madrid, and have held a [postgraduate fellowship](https://becarios.fundacionlacaixa.org/en/celia-rubio-madrigal-B005794) from la Caixa Foundation. I am actively involved in organizing the European Girls' Mathematical Olympiad ([EGMO](https://www.egmo.org/person933/)) every year as part of the IT team. I have been featured in the Nova 111 Student List 2023 as one of the top 10 under 25 in Computer Science in Spain. I also had the privilege of being selected as a young researcher for the Heidelberg Laureate Forum in 2022. Additionally, I have a passion for music that led to publishing a LaTeX package, 
[ddphonism](https://ctan.org/pkg/ddphonism), which is included in MikTeX and the TeXLive Music bundle.

You can read my full CV [here](/assets/pdf/RubioMadrigalCelia_cv.pdf), or check out a <a href="/timeline/" target="_self">timeline</a> of all my past activities.

## News

{% for milestone in site.data.news.list %}
{% for item in milestone.details %}
{% if item.new %}
* {{ item.date }}｜{{ item.description | markdownify | remove: '<p>' | remove: '</p>' }}
{% endif %}
{% endfor %}
{% endfor %}
