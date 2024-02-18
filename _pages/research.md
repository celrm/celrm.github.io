---
layout: default
title: Research
permalink: /research/
order: 2
---

<ul>
{% for paper in site.data.research %}
    <li>
        <a href="{{ paper.url }}">{{ paper.title }}</a>.
        <i>{% for author in paper.authors %}
            {% if author == site.author %}<u>{{ author }}</u>{% else %}{{ author }}{% endif %}{% if forloop.last == false %}, {% endif %}{%
        endfor %}</i>.
        {% if paper.venue %} {{ paper.venue }}{% endif %}
        {% if paper.date %} ({{ paper.date }}){% endif %}
        {% if paper.award %} <b>{{ paper.award }}</b>{% endif %}
    </li>
{% endfor %}
</ul>
