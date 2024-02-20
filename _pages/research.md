---
layout: default
title: Research
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


