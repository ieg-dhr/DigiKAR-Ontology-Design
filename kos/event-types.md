---
layout: page
title: Ereignis
permalink: /kos/event-types/
categories: KOS
tags: SKOS, Concept Scheme, 
---

## Klassifikationssystem für Lebensereignisse

Die Begriffe im Klassifikationssystem Ereignis (Präfix `dmlv-event:`) dienen zur Typisierung der Lebensereignisse von Personen.

Auszug aus der RDF-Turtle-Repräsentation des Klassifikationssystems:

```turtle
@prefix dmlv-event: <http://digikar.eu/vocabulary/event/> .

@prefix skos: <http://www.w3.org/2004/02/skos/core#> .
@prefix rdfs: <http://www.w3.org/2000/01/rdf-schema#> .


dmlv-event: a skos:ConceptScheme ;
  rdfs:label "Ereignis"@de , "Event"@en ;
  skos:notation "ev" ;
  skos:prefLabel "Ereignis"@de ;
  skos:prefLabel "Event"@en ;
  dct:description "Kontrolliertes Vokabular zur Klassifikation der Lebensereignisse von Personen."@de ;
  skos:hasTopConcept dmlv-event:birth ;
  skos:hasTopConcept dmlv-event:death ;
  skos:hasTopConcept dmlv-event:residency ;
  skos:hasTopConcept dmlv-event:occupation 
.

dmlv-event:birth a skos:Concept ;
  rdfs:label "Geburt" ;
  skos:notation "birth" ;
  skos:prefLabel "Geburt"@de ;
  skos:prefLabel "Birth"@en ;
  skos:inScheme dmlv-event: 
.

dmlv-event:death a skos:Concept ;
  rdfs:label "Tod" ;
  skos:notation "death" ;
  skos:prefLabel "Tod"@de ;
  skos:prefLabel "Death"@en ;
  skos:inScheme dmlv-event: 
.

dmlv-event:residency a skos:Concept ;
  rdfs:label "Wirkungsort" ;
  skos:notation "residency" ;
  skos:prefLabel "Wirkungsort"@de ;
  skos:prefLabel "Residency"@en ;
  skos:inScheme dmlv-event: 
.

dmlv-event:occupation a skos:Concept ;
  rdfs:label "Funktionsausübung" ;
  skos:notation "occupation" ;
  skos:prefLabel "Funktionsausübung"@de ;
  skos:prefLabel "Occupation"@en ;
  skos:altLabel "Berufsausübung"@de ;
  skos:inScheme dmlv-event: 
.

```

