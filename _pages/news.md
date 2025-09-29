---
layout: default
title: Timeline
permalink: /timeline/
order: 3
---

Click on some of the icons to see pictures from the events.

<p id="filter">Filter by category:
<select id="choosenewscategory">
  <option value="">All news</option>{% for category in site.data.news.legend %}<option value="{{ category.name }}">{{ category.name | capitalize }}{% unless category.name contains 'work' or category.name contains 'press' or category.name contains 'leisure' %}s{% endunless %}</option>{% endfor %}
  </select></p>

{% for milestone in site.data.news.list %}

## {{ milestone.date }}

{{ milestone.description | markdownify }}

<ul style="list-style-type: none; padding-inline-start: 1em;">
{% for item in milestone.details %}{% if item.notshow %}{% else %}
<li id="bib-{{forloop.parentloop.index}}-{{forloop.index}}" categories="{% for type in item.type %}{{ type }}{% unless forloop.last %},{% endunless %}{% endfor %}"
style="margin-block-start: 1em; margin-block-end: 1em;">{% for type in item.type %}{% 
for legenditem in site.data.news.legend %}{% if type == legenditem.name 
%}<span onclick="image2(this)" style="{% if item.event_name %} cursor: pointer; {% endif %} border: 1px solid var(--color-text); padding: 4px; border-radius: 5px; font-size: 0.6em; 
vertical-align: middle; min-width: 13px; width: 1em; height: 1em; 
text-align: center;" class="{{ legenditem.icon }}">{% if item.event_name %}<img src="{{ site.url }}{{ site.baseurl }}/assets/img/events/{{ item.event_name }}.jpeg" alt="{{ item.event_name }}" style="display: none; ">{% endif %}</span>{% endif %}{% endfor %}{% endfor 
%}&ensp;{% if item.date %}{{ item.date }}｜{% endif %}{{ 
  item.description | markdownify | remove: '<p>' | remove: '</p>' }}
</li>{% endif %}
{% endfor %}
</ul>

{% endfor %}

# Legend

<ul style="list-style: none; padding: 0; margin: 0; display: flex; flex-direction: row; gap: 2em; flex-wrap: wrap;">
{% for legenditem in site.data.news.legend %}
  <li><span style="border: 1px solid var(--color-text); padding: 4px; border-radius: 5px; font-size: 0.6em; 
  vertical-align: middle; min-width: 13px; width: 1em; height: 1em; text-align: center; margin-right: 0.1em;
  " class="{{ legenditem.icon }}"></span>
  {{ legenditem.name | capitalize }}</li>
{% endfor %}
</ul>

<script>
document.addEventListener('DOMContentLoaded', function() {
    var selector = document.getElementById('choosenewscategory');
    if (selector) {
        selector.addEventListener('change', function() {
            var selected = this.value;
            var entries = document.querySelectorAll('li');
            entries.forEach(function(entry) {
                if (entry.id.includes('bib')) {
                    var categories = entry.getAttribute('categories');
                    if (categories.includes(selected)) {
                        entry.style.display = 'block';
                    } else {
                        entry.style.display = 'none';
                    }
                }
            });
        });
    }
});
</script>
