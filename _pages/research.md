---
layout: default
title: Research
titlealt: List of publications
permalink: /research/
order: 2
---

Filter by category:
<select id="choosecategory">
  <option value="">All papers</option>{% for category in site.data.research.categories %}{% for attribute in category 
  %}<option value="{{ attribute[0] }}">{{ attribute[1] }}</option>{% endfor %}{% endfor %}
</select>

<ol class="bibliography">
{% for entry in site.data.research.list %}
<li>
{% include bib.html %}
</li>
{% endfor %}
</ol>

<script>
document.addEventListener('DOMContentLoaded', function() {
    var selector = document.getElementById('choosecategory');
    if (selector) {
        selector.addEventListener('change', function() {
            var selected = this.value;
            var entries = document.querySelectorAll('.row');
            entries.forEach(function(entry) {
                if (entry.id.includes('bib')) {
                    var categories = entry.getAttribute('categories');
                    if (categories.includes(selected)) {
                        entry.style.display = 'flex';
                    } else {
                        entry.style.display = 'none';
                    }
                }
            });
        });
    }
});
</script>

# List of talks and posters

<ul style="list-style-type: none; padding-inline-start: 0em;">
{% for item in site.data.talks.list %}
<li style="margin-block-start: 1em; margin-block-end: 1em;">{% for type in item.type %}{% 
for legenditem in site.data.talks.legend %}{% 
if type == legenditem.name 
%}<span style="border: 1px solid var(--color-text); padding: 4px; border-radius: 5px; font-size: 0.6em; 
vertical-align: middle; min-width: 13px; text-align: center;" class="{{ legenditem.icon }}"></span>{% 
endif %}{% 
endfor %}
{% endfor %}<div style="display: inline">
{{ item.date }}:
{{ item.title | markdownify | remove: '<p>' | remove: '</p>' }}  {% if item.pdf %}
   [<a href="/assets/pdf/{{ item.pdf }}">Poster</a>]
{% endif %}</div>
<div style="padding-inline-start: 1.75em; "
>{{ item.event | markdownify | remove: '<p>' | remove: '</p>'  }}</div>
</li>
{% endfor %}
</ul>