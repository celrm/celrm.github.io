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

{% assign first_author_published = site.data.research.list | where_exp: "item", "item.preprint != true and item.first_author == true" %}
{% assign coauthor_published = site.data.research.list | where_exp: "item", "item.preprint != true and item.first_author != true" %}
{% assign preprints = site.data.research.list | where_exp: "item", "item.preprint == true" %}

{% for entry in first_author_published %}
<li>
{% include bib.html %}
</li>
{% endfor %}

{% if coauthor_published.size > 0 %}
<h3>Co-authored</h3>
{% for entry in coauthor_published %}
<li>
{% include bib.html %}
</li>
{% endfor %}
{% endif %}

{% if preprints.size > 0 %}
<h3>Pre-prints</h3>
{% for entry in preprints %}
<li>
{% include bib.html %}
</li>
{% endfor %}
{% endif %}

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

<script>
function image(img) {
    window.open(img.src,'targetWindow', 'toolbar=no, location=no, status=no, menubar=no, scrollbars=yes, resizable=yes, width=600px, height=600px, top=50px left=250px');
}
</script>
