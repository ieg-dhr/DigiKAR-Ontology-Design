---
layout: page
title: Klassifikationssysteme
permalink: /kos/
---

<ul>
{% for p in site.pages %}
   {% if p.categories contains 'KOS' %}
      <li><a href="{{ p.url }}">{{ p.title }}</a></li>
   {% endif %}
{% endfor %}
</ul>
