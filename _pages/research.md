---
layout: default
title: Research
titlealt: Publications
permalink: /research/
order: 2
---

Click on the image previews for larger versions.

<p id="filter">Filter by category:
<select id="choosecategory">
  <option value="">All papers</option>{% for category in site.data.research.categories %}{% for attribute in category 
  %}<option value="{{ attribute[0] }}">{{ attribute[1] }}</option>{% endfor %}{% endfor %}
</select></p>

<ol class="bibliography">

{% assign not_preprints = site.data.research.list | where: "preprint", nil %}
{% assign first_author_published = not_preprints | where: "first_author", true %}
{% for entry in first_author_published %}
{% unless entry.preprint %}
<li>
{% include bib.html %}
</li>
{% endunless %}
{% endfor %}

{% assign has_coauthors = false %}
{% for entry in not_preprints %}
  {% unless entry.first_author or entry.preprint %}
    {% assign has_coauthors = true %}
  {% endunless %}
{% endfor %}
{% if has_coauthors %}
<h3>Co-authored</h3>
{% for entry in not_preprints %}
  {% unless entry.first_author or entry.preprint %}
    <li>
      {% include bib.html %}
    </li>
  {% endunless %}
{% endfor %}
{% endif %}

{% assign preprints = site.data.research.list | where: "preprint", true %}
{% if preprints.size > 0 %}
<h3>Pre-prints</h3>
{% for entry in preprints %}
<li>
{% include bib.html %}
</li>
{% endfor %}
{% endif %}
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