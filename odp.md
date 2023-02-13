---
layout: page
title: Ontologie-Entwurfsmuster
permalink: /odp/
---

## Katalog der bisher im Projekt entstandenen Ontologie-Entwurfsmuster

<ul>
{% for p in site.pages %}
   {% if p.categories contains 'ODP' %}
      <li><a href="{{ p.url }}">{{ p.title }}</a></li>
   {% endif %}
{% endfor %}
</ul>

## Vorgehensweise zur Entwicklung der Ontologie-Entwurfsmuster

Die interative Vorgehensweise bei der Entwicklung der Ontologie-Entwurfsmuster (Ontology Design Patterns) für DigiKAR besteht aus den folgenden Schritten:

1. Sammeln von sogenannten **User Stories**, welche die Anforderungen in kurzer, struktu-
ierter Form beschreiben.
2. Ableiten von sogenannten **Competency Questions** aus den jeweiligen User Stories.
3. Auswählen oder Erweitern existierender oder ggf. Entwickeln neuer **Ontology Design Patterns** auf Basis der Anforderungsanalyse mit User Stories und Competency Questions.

Sie insbesondere zu Schritt 1 und 2 die Dokumentation unserer Sammlung von Competency Questions auf der gesonderten GiutHub Pages-Website: [DigiKAR Competency Questions](https://ieg-dhr.github.io/DigiKAR-Competency-Questions/)

## Beschreibung von Ontologie-Entwurfsmustern mit SHACL

Im Prinzip ist das Datenmodell für DigiKAR ein CRM- & CRMgeo-Anwendungsprofil, das sich modular aus Ontologie-Entwurfsmustern zusammensetzt. Wir verwenden zur Beschreibung dieser Entwurfsmuster SHACL (SHApes Constraint Language). Aus der sehr umfangreichen und komplexen CRM-Ontologie und relevanter CRM-Erweiterungen wie CRMgeo oder auch FRBRoo können somit die für die speziellen Anforderungen benötigten Klassen und Eigenschaften ausgewählt und deren bei der Datenmodellierung möglichen bzw. erlaubten Zusammenhänge mit SHACL festgelegt werden.

Der Einfachheit halber befinden sich derzeit alle in SHACL repräsentierten Module in einer SHACL-Datei (siehe folgendes Schema-Diagramm). Die Ontologie-Entwurfsmuster können daher während der Projektlaufzeit bei Bedarf an einer zentralen Stelle erweitert oder angepasst werden, um ggf. bisher noch nicht unterstützte Anforderungen an die Datenmodellierung oder Datenbankabfragemöglichkeiten zu erfüllen.

Erweiterbar sind auch die [Wissensorganisationssysteme](/kos/), die von den Entwurfsmustern z.B. zur Typisierung vonb Orten oder zur Klassifikation der Funktionen von Amtsträgern im Alten Reich vorgesehen sind.

![Schema-Diagramm](/img/dmlo.svg)
*Schema-Diagramm der mit SHACL definierten Ontologie-Entwurfsmuster für Orstdaten und biographische Daten*

Im Schema-Diagramm sind sowohl die Ontologie-Entwurfsmuster zur Modellierung der ortsbasierten Information (zentral für Arbeitspaket 2), als auch die zur Modellierung biographischer Daten, d.h. der Aktivitäten von historischen Personen benötigten Entwurfsmuster. Zur besseren Sichtbarkeit sind die Module auf den oben unter der Überschrift _Katalog der bisher im Projekt entstandenen Ontologie-Entwurfsmuster_ verlinkten strukturierten Dokumentationen der Ontologie-Entwurfsmuster im jeweiligen Schema-Diagramm auf die Datrstellung der für das Muster wesentlichen Klassen und Eigenschaften beschränkt. In der Mitte des Diagramms erkennt man übrigens die Grundstruktur des [Linked Places Format](https://github.com/LinkedPasts/linked-places-format) bzw. der [Linked Pasts Ontology](https://github.com/LinkedPasts/linked-pasts-ontology) (zur Modellierung von (historischen) Ortsnamen, Ortstypen, Geometrien/Koordinaten und Relationen zwischen Orten), an denen wir uns bereits am Anfang des Projekts orientiert haben.
