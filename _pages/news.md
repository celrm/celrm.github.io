---
layout: default
title: Timeline
permalink: /timeline/
order: 3
---

{% for milestone in site.data.news.list %}

## {{ milestone.date }}

{{ milestone.description | markdownify }}

<ul style="list-style-type: none; padding-inline-start: 1em;">
{% for item in milestone.details %}
<li style="margin-block-start: 1em; margin-block-end: 1em;">{% for type in item.type %}{% 
for legenditem in site.data.news.legend %}{% if type == legenditem.name 
%}<span style="border: 1px solid var(--color-text); padding: 4px; border-radius: 5px; font-size: 0.6em; 
vertical-align: middle; min-width: 13px; text-align: center;" class="{{ legenditem.icon }}"></span>{% endif %}{% endfor %}{% endfor 
%}&ensp;{% if item.new %}{% endif %}{% if item.date %}{{ item.date }}｜{% endif %}{{ 
  item.description | markdownify | remove: '<p>' | remove: '</p>' }}
</li>
{% endfor %}
</ul>

{% if forloop.last == false %}
<p style="margin-top: 2em;"></p>
<hr>
{% endif %}

{% endfor %}

# Legend

<ul style="list-style: none; padding: 0; margin: 0; display: flex; flex-direction: row; gap: 2em; flex-wrap: wrap;">
{% for legenditem in site.data.news.legend %}
  <li><span style="border: 1px solid var(--color-text); padding: 4px; border-radius: 5px; font-size: 0.6em; 
  vertical-align: middle; min-width: 13px; text-align: center; margin-right: 0.1em;
  " class="{{ legenditem.icon }}"></span>
  {{ legenditem.name | capitalize }}</li>
{% endfor %}
</ul>
