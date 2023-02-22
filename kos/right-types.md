---
layout: page
title: Herrschaftsarten
permalink: /kos/right-types/
categories: KOS
tags: SKOS, Concept Scheme, 
---

## Klassifikationssystem für Herrschaftsrechte

Die Begriffe im Klassifikationssystem Herrschaftsarten (Präfix `dmlv-right:`) dienen zur Spezifizierung der Herrschaftsrechte (z.B. anhand der Begriffe für Grundherrschaft oder Gerichtsbarkeit bzw. deren Unterbegriffe für Hochgerichtsbarkeit und Niedergerichtsbarkeit).

Auszug aus der RDF-Turtle-Repräsentation des Klassifikationssystems:

```turtle
@prefix dmlv-right: <http://digikar.eu/vocabulary/right/> .

@prefix skos: <http://www.w3.org/2004/02/skos/core#> .
@prefix rdfs: <http://www.w3.org/2000/01/rdf-schema#> .


dmlv-right: a skos:ConceptScheme ;
  rdfs:label "Herrschaftsarten" ;
  skos:notation "right" ;
  skos:prefLabel "Arten der Herrschaftsrechte"@en ;
  skos:prefLabel "Right Types"@en ;
  dct:description "Begriffe zur Typisierung der Herrschaftsträgerschaft (z.B. grundherrschaftlicher Besitz)."@de ;
  skos:hasTopConcept dmlv-right:administrative ;
  skos:hasTopConcept dmlv-right:manorial ;
  skos:hasTopConcept dmlv-right:ecclesiastical ;
  skos:hasTopConcept dmlv-right:legal
.

dmlv-right:manorial a skos:Concept ;
  rdfs:label "manorial" ;
  skos:notation "manorial" ;
  skos:prefLabel "grundherrschaftlich"@de ;
  skos:prefLabel "manorial"@en ;
  dct:description "Begriff zur Typisierung einer Zugehörigkeit bzw. Herrschaftsbeziehung als grundherrschaftlicher Beziehung."@de ;
  skos:inScheme dmlv-right: 
.

dmlv-right:legal a skos:Concept ;
  rdfs:label "juristisch" ;
  skos:notation "legal" ; # jurisdiction 
  skos:prefLabel "juristisch"@de ;
  skos:prefLabel "legal"@en ;
  skos:altLabel "juridical"@en ;
  dct:description "Begriff zur Typisierung einer Zugehörigkeit bzw. Herrschaftsbeziehung als juristischer Beziehung."@de ;
  skos:inScheme dmlv-right: 
.

# Obergericht --> Inhaber 
dmlv-right:high-justice a skos:Concept ;
  rdfs:label "Hochgerichtsbarkeit" ; 
  skos:notation "high-justice" ;
  skos:prefLabel "Hochgerichtsbarkeit"@de ;
  skos:prefLabel "high-justice"@en ;
  skos:altLabel "Blutgerichtsbarkeit"@de ;
  skos:altLabel "blood justice"@en ;
  skos:broader dmlv-right:legal ;
  skos:inScheme dmlv-right: 
.

# Erbgericht --> Inhaber 
dmlv-right:low-justice a skos:Concept ;
  rdfs:label "Niedergerichtsbarkeit" ; # probate court  Patrimonialgericht 
  skos:notation "low-justice" ;
  skos:prefLabel "Niedergerichtsbarkeit"@de ;
  skos:prefLabel "low-justice"@en ;
  skos:altLabel "Niedere Gerichtsbarkeit"@de ;
  skos:altLabel "patrimoniale Gerichtsbarkeit"@de ;
  skos:broader dmlv-right:legal ;
  skos:inScheme dmlv-right: 
.

```

