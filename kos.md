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

Wir verwenden {SKOS (Simple Knowledge Organisation System)](https://www.w3.org/2004/02/skos/) zur Modellierung der im Projekt eingesetzten Begriffsystemen wie Typologien, Klassifikationssystemen oder auch einfachen Kodierlisten (wie etwa zur Angabe von Sprachcodes). Mit SKOS setzen wir auf den de-facto-Standard für die Modellierung von Wissensorganisationssystemen im Semantic und Linked Data Web.

Zentral beim Einsatz von SKOS zur Modellierung von Wissensorganisationssystemen ist der begriffsbasierte Ansatz. Der folgende Auszug aus der [SKOS-Dokumentation](https://www.w3.org/TR/skos-primer/##secconcept) macht dieses Modellierungsprinzip klar:

> The fundamental element of the SKOS vocabulary is the *concept*. Concepts are the *units of thought* [...]---ideas, meanings, or (categories of) objects and events---which underlie many knowledge organization systems [...]. As such, concepts exist in the mind as abstract entities which are independent of the terms used to label them.
