---
layout: default
title: Research
titlealt: Publications
permalink: /research/
order: 2
---

<p id="filter">Filter by category:
<select id="choosecategory">
  <option value="">All papers</option>{% for category in site.data.research.categories %}{% for attribute in category 
  %}<option value="{{ attribute[0] }}">{{ attribute[1] }}</option>{% endfor %}{% endfor %}
</select></p>

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
