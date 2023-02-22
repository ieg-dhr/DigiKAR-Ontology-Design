---
layout: page
title: Ortstypologie
permalink: /kos/place-types/
categories: KOS
tags: SKOS, Concept Scheme, 
---

## Ortstypologie

Die Begriffe im Klassifikationssystem Ortstypologie (Präfix `dmlv-place:`) dienen zur Spezifizierung der Ortstypen (z.B. anhand der Begriffe für die Siedlungstypen Dorf oder Stadt).

Auszug aus der RDF-Turtle-Repräsentation der Ortstypologie (inkl. Konkordanz zur Ortstypologie des GOV anhand der `skos:exactMatch`-Eigenschaft):

```turtle
@prefix dmlv-place: <http://digikar.eu/vocabulary/place/> .

@prefix gov-types: <http://gov.genealogy.net/types.owl#> .

@prefix skos: <http://www.w3.org/2004/02/skos/core#> .
@prefix rdfs: <http://www.w3.org/2000/01/rdf-schema#> .


dmlv-place: a skos:ConceptScheme ;
  rdfs:label "Ortstypologie" ;
  skos:notation "pt" ;
  skos:prefLabel "Ortstypologie"@de ;
  skos:prefLabel "Place Typology"@en ;
  skos:description "Ortstypologie für DigiKAR."@de ;
  skos:hasTopConcept dmlv-place:st ;
  skos:hasTopConcept dmlv-place:at 
.

dmlv-place:st a skos:Concept ;
  rdfs:label "Siedlung" ;
  skos:notation "st" ;
  skos:prefLabel "Siedlung"@de ;
  skos:prefLabel "Settlement"@en ;
  skos:altLabel "Ortschaft"@de ;
  skos:altLabel "Locality"@en ;
  skos:inScheme dmlv-place: ;
  skos:exactMatch gov-types:120
.

dmlv-place:vi a skos:Concept ;
  rdfs:label "Dorf" ;
  skos:notation "vi" ;
  skos:prefLabel "Dorf"@de ;
  skos:prefLabel "Village"@en ;
  skos:broader dmlv-place:st ;
  skos:inScheme dmlv-place: ;
  skos:exactMatch gov-types:55
.

dmlv-place:to a skos:Concept ;
  rdfs:label "Stadt" ;
  skos:notation "to" ;
  skos:prefLabel "Stadt"@de ;
  skos:prefLabel "Town"@en ;
  skos:broader dmlv-place:st ;
  skos:inScheme dmlv-place: ;
  skos:exactMatch gov-types:51
.

```
