---
layout: default
title: Talks
titlealt: Talks and posters
permalink: /talks/
order: 2
---

Click on some of the icons to see pictures from the events.

<p id="filter">Filter by category:
<select id="choosetalkcategory">
  <option value="">All events</option>{% for category in site.data.talks.legend %}<option value="{{ category.name }}">{{ category.name | capitalize }}s</option>{% endfor %}
</select></p>

<!-- <div style="height: 0.5em;"></div> -->


{% for item in site.data.talks.list %}
<ul id="bib-{{forloop.index}}" 
style="list-style-type: none; padding-inline-start: 0em;" 
categories="{% for event in item.events %}{{ event.type }}{% unless forloop.last %},{% endunless %}{% endfor %}">
<li>{{ item.title | markdownify | remove: '<p>' | remove: '</p>' }}</li>
</ul>

<ul id="bib-{{forloop.index}}-2" 
style="list-style-type: none; padding-inline-start: 0em;" 
categories="{% for event in item.events %}{{ event.type }}{% unless forloop.last %},{% endunless %}{% endfor %}">

{% for event in item.events %}

<li id="bib-{{forloop.parentloop.index}}-{{forloop.index}}"
 style="margin-block-start: 1em; margin-block-end: 1em; padding-inline-start: 1em;" categories="{{ event.type }}">
{% for legenditem in site.data.talks.legend %}
{% if event.type == legenditem.name %}<span onclick="image2(this)"  style="{% if event.event_name %} cursor: pointer; {% endif %} border: 1px solid var(--color-text); padding: 4px; border-radius: 5px; font-size: 0.6em; vertical-align: bottom; min-width: 13px; text-align: center;" class="{{ legenditem.icon }}">{% if event.event_name %}<img src="{{ site.url }}{{ site.baseurl }}/assets/img/events/{{ event.event_name }}.jpeg" alt="{{ event.event_name }}" style="display: none; ">{% endif %}</span>
    
<span>{{ event.date }}</span>: {{ event.place | markdownify | remove: '<p>' | remove: '</p>' }}
    {% if event.url %}
        [<a href="{{ event.url | prepend: legenditem.folder }}">{{ event.type | capitalize }}</a>]
    {% endif %}
    
{% endif %}{% endfor %}
</li>

{% endfor %}
</ul>
{% endfor %}



<script>
document.addEventListener('DOMContentLoaded', function() {
    var selector = document.getElementById('choosetalkcategory');
    if (selector) {
        selector.addEventListener('change', function() {
            var selected = this.value;
            var entries = document.querySelectorAll('ul[id^="bib-"]');
            console.log(entries);
            entries.forEach(function(entry) {
                var categories = entry.getAttribute('categories');
                if (selected === "" || categories.includes(selected)) {
                    entry.style.display = 'block';
                } else {
                    entry.style.display = 'none';
                }
            });
            var entries2 = document.querySelectorAll('li[id^="bib-"]');
            entries2.forEach(function(entry) {
                var categories = entry.getAttribute('categories');
                if (selected === "" || categories.includes(selected)) {
                    entry.style.display = 'block';
                } else {
                    entry.style.display = 'none';
                }
            });
    });
    }
});
</script>