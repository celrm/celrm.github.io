---
layout: default
title: Research
titlealt: List of publications
permalink: /research/
order: 2
---

<ol class="bibliography">
{% for entry in site.data.research %}
<li>
{% include bib.html %}
</li>
{% endfor %}
</ol>


