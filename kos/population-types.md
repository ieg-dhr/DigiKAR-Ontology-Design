---
layout: page
title: Einwohner
permalink: /kos/population-types/
categories: KOS
tags: SKOS, Concept Scheme, 
---

## Kodierschema für Arten von Einwohnern

Die Begriffe im Kodierschema Einwohner (Präfix `dmlv-population:`) dienen zur Kodierung der Art von Einwohnern.

RDF-Turtle-Repräsentation des Kodierschemas (Auszug aus den Einwohnerarten im Datenbestand des Repertorium Saxonicum):

```turtle
@prefix dmlv-population: <http://digikar.eu/vocabulary/population/> .

@prefix skos: <http://www.w3.org/2004/02/skos/core#> .
@prefix rdfs: <http://www.w3.org/2000/01/rdf-schema#> .
@prefix dct: <http://purl.org/dc/terms/> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .


dmlv-population: a skos:ConceptScheme ;
  rdfs:label "Einwohner" ;
  skos:notation "population" ;
  skos:prefLabel "Arten von Einwohnern"@en ; 
  skos:prefLabel "Population Types"@en ;
  dct:description "Begriffe zur Kodierung der Art von Einwohnern."@de ; 
  skos:hasTopConcept dmlv-population:bm ;
  skos:hasTopConcept dmlv-population:gr ;
  skos:hasTopConcept dmlv-population:hr ;
  skos:hasTopConcept dmlv-population:hs ;
  skos:hasTopConcept dmlv-population:mr ;
  skos:hasTopConcept dmlv-population:pf ;
  dct:source "https://repsax.isgv.de/hilfe.php"^^xsd:anyURI 
.

dmlv-population:bm a skos:Concept ;
  rdfs:label "Besessene Mann" ;
  skos:notation "bm" ;
  skos:prefLabel "Besessene Mann"@de ;
  skos:definition "Einwohner, der Land besaß"@de ;
  skos:inScheme dmlv-population: 
.

dmlv-population:gr a skos:Concept ;
  rdfs:label "Gärtner" ;
  skos:notation "gr" ;
  skos:prefLabel "Gärtner"@de ;
  skos:altLabel "Erbgärtner"@de ;
  skos:definition "Grundbesitzer, der einen Garten besitzt und über einen erheblich geringeren Grundbesitz als Bauern verfügt; siehe auch Hintersasser"@de ; 
  skos:related dmlv-population:hs ;
  skos:inScheme dmlv-population: 
.

dmlv-population:hr a skos:Concept ;
  rdfs:label "Häusler" ;u
  skos:notation "hr" ;
  skos:prefLabel "Häusler"@de ;
  skos:definition "Einwohner eines Dorfes, der nur ein Haus besitzt, aber keinen Grundbesitz"@de ; 
  skos:inScheme dmlv-population: 
.

dmlv-population:hs a skos:Concept ;
  rdfs:label "Hintersasser" ;
  skos:notation "hs" ;
  skos:prefLabel "Hintersasser"@de ;
  skos:definition "Kleinbauer, der so wenig Acker besitzt, dass er kein Zugvieh halten kann; auch Bezeichnung für einen Mietbewohner"@de ; 
  skos:inScheme dmlv-population: 
.

dmlv-population:mr a skos:Concept ;
  rdfs:label "Müller" ;
  skos:notation "mr" ;
  skos:prefLabel "Müller"@de ;
  skos:inScheme dmlv-population: 
.

dmlv-population:pf a skos:Concept ;
  rdfs:label "Pferdner" ;
  skos:notation "pf" ;
  skos:prefLabel "Pferdner"@de ;
  skos:definition "Bezeichnung für Einwohner, die Frondienste mit Pferden leisten"@de ; 
  skos:inScheme dmlv-population: 
.

```

