---
layout: page
title: Wissensorganisationssysteme
permalink: /kos/
---

## Übersicht der bisher in den Ontologie-Entwurfsmusters verwendeten Wissensorganisationssysteme

<ul>
{% for p in site.pages %}
   {% if p.categories contains 'KOS' %}
      <li><a href="/DigiKAR-Ontology-Design{{ p.url }}">{{ p.title }}</a></li>
   {% endif %}
{% endfor %}
</ul>
