---
layout: default
title: Resource Tag Index
---

# {{ page.title }} #

{% assign resourcetags =  site.qgis_resources | map: 'tags' | join: ','  | split: ',' %}
{% assign minutetags = site.minutes | map: 'tags' | join: ',' | split: ',' %}
{% assign alltags = resourcetags | concat: minutetags %}
{% assign tags = alltags | sort | uniq %}

<ul class="tags">
  {% for tag in tags %}
    <li><a href="#{{ tag }}" class="tag">{{ tag }}</a></li>
 {% endfor %}
</ul>


{% for tag in tags %}
  <h3 id="{{ tag }}">{{ tag }}</h3>
  <ul>
  {% for res in site.qgis_resources %}
    {% if res.tags contains tag %}
    <li><a href="/resources.html#{{ res.title }}">{{ res.title }}</a></li>
    {% endif %}
  {% endfor %}
  {% for min in site.minutes %}
    {% if min.tags contains tag %}
    <li><a href="{{ min.url }}">{{ min.title }}</a></li>
    {% endif %}
  {% endfor %}
  </ul>
{% endfor %}
