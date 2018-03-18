---
layout: default
title: Resource Tag Index
---

# {{ page.title }} #

{% assign unsorttags =  site.qgis_resources | map: 'tags' | join: ','  | split: ',' | uniq %}
{% assign tags = unsorttags | sort %}

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
    <li><a href="resources.html#{{ res.title }}">{{ res.title }}</a></li>
    {% endif %}
  {% endfor %}
  </ul>
{% endfor %}
