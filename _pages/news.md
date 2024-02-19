---
layout: default
title: News
titlealt: Recent and past news
permalink: /news/
order: 3
---

This page chronologically outlines some milestones in my life, categorized by their academic period.

While it mainly focuses on my professional accomplishments —such as awards, conferences, publications, and press appearances— it also contains other activities that have contributed to my personal growth, like my volunteer work at math olympiads and my music projects. 

You can also find my CV [here](/assets/RubioMadrigalCelia_cv.pdf).

{% for milestone in site.data.news %}
<h2>{{ milestone.date }}</h2>
<p>{{ milestone.event | markdownify }}</p>
<div style="display: flex; flex-wrap: wrap;">
{% for tag in milestone.tags %}
  <span style="border: 1px solid grey; padding: 4px; border-radius: 5px; font-size: 0.6em;
    vertical-align: middle; text-transform: uppercase; margin-right: 10px;">
    <span class="fa-solid fa-tag"></span>
    {{ tag }}{% if forloop.last == false %} {% endif %}
    </span>
{% endfor %}</div>

  <ul>{% for item in milestone.details %}
    <li>{% for type in item.type %}
    {% if type == "work" %}{% assign fa = "fa-regular fa-bookmark" %}
    {% elsif type == "event" %}{% assign fa = "fa-regular fa-calendar" %}
    {% elsif type == "award" %}{% assign fa = "fa-regular fa-star" %}
    {% elsif type == "press" %}{% assign fa = "fa-regular fa-newspaper" %}
    {% elsif type == "publication" %}{% assign fa = "fa-solid fa-pen-nib"%}
    {% elsif type == "code" %}{% assign fa = "fa-solid fa-terminal" %}
    {% elsif type == "math" %}{% assign fa = "fa-solid fa-square-root-variable" %}
    {% elsif type == "music" %}{% assign fa = "fa-solid fa-music" %}
    {% else %}{% assign fa = "fa-solid fa-ellipsis-h" %}{% endif %}
    <span style="border: 1px solid grey; padding: 4px; border-radius: 5px; font-size: 0.6em; 
    vertical-align: middle; min-width: 13px; text-align: center;" class="{{ fa }}"></span>
    {% endfor %} 
    {{ item.event | markdownify | remove: '<p>' | remove: '</p>' }}</li>
{% endfor %}</ul>
{% endfor %}
