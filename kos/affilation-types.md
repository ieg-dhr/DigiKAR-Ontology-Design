---
layout: page
title: Zugehörigkeitsarten
permalink: /kos/affiliation-types/
categories: KOS
tags: SKOS, Concept Scheme, 
---

## Klassifikationssystem für Arten der Zugehörigkeit

Die Begriffe im Klassifikationssystem Zugehörigkeitsarten (Präfix `dmlv-affiliation:`) dienen zur Spezifizierung der Art der Herrschaftsbeziehung zwischen Ort und Herrschaftsträger(n) (z.B. zur Angabe von geteilter oder umstrittener Herrschaft).

RDF-Turtle-Repräsentation des Klassifikationssystems:

```turtle
@prefix dmlv-affiliation: <http://digikar.eu/vocabulary/affiliation/> .

@prefix skos: <http://www.w3.org/2004/02/skos/core#> .
@prefix rdfs: <http://www.w3.org/2000/01/rdf-schema#> .


dmlv-affiliation: a skos:ConceptScheme ;
  rdfs:label "Zugehörigkeitsarten" ;
  skos:notation "affiliation" ;
  skos:prefLabel "Arten der Zugehörigkeit"@en ;
  skos:prefLabel "Affiliation Types"@en ;
  dct:description "Begriffe zur Typisierung der Herrschaftsbeziehung zwischen einem Ort und Herrschaftsträger(n)."@de ;
  skos:hasTopConcept dmlv-affiliation:shared ;
  skos:hasTopConcept dmlv-affiliation:disputed 
.

dmlv-affiliation:shared a skos:Concept ;
  rdfs:label "geteilt" ;
  skos:notation "shared" ;
  skos:prefLabel "geteilt"@de ;
  skos:prefLabel "shared"@en ;
  skos:altLabel "anteilig"@de ;
  skos:altLabel "proportionate"@en ;
  skos:scopeNote "Begriff zur Typisierung einer Herrschaftsbeziehung mit mindestens zwei Herrschaftsträgern, die sich die Herrschaft teilen."@de ;
  skos:inScheme dmlv-affiliation: 
.

dmlv-affiliation:disputed a skos:Concept ;
  rdfs:label "umstritten" ;
  skos:notation "disputed" ;
  skos:prefLabel "umstritten"@de ;
  skos:prefLabel "disputed"@en ;
  skos:scopeNote "Begriff zur Typisierung einer Herrschaftsbeziehung mit mindestens zwei Herrschaftsträgern, zwischen denen die Herrschaft umstritten ist."@de ;
  skos:inScheme dmlv-affiliation: 
.

```

