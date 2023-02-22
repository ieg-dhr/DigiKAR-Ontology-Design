---
layout: page
title: Wissensorganisationssysteme
permalink: /kos/
---

## Übersicht der bisher in den Ontologie-Entwurfsmustern verwendeten Wissensorganisationssysteme

<ul>
{% for p in site.pages %}
   {% if p.categories contains 'KOS' %}
      <li><a href="/DigiKAR-Ontology-Design{{ p.url }}">{{ p.title }}</a></li>
   {% endif %}
{% endfor %}
</ul>

## Modellierung der Wissensorganisationssysteme mit SKOS

Wir verwenden SKOS (Simple Knowledge Organisation System) zur Modellierung der im Projekt eingesetzten Begriffsystemen wie Typologien, Klassifikationssystemen oder auch einfachen Kodierlisten (wie etwa zur Angabe von Sprachcodes).
