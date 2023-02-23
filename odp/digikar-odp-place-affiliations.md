---
layout: page
title: Ontologie-Entwurfsmuster zur Modellierung von multiplen Zugehörigkeiten eines Ortes
permalink: /odp/affiliations/
categories: ODP
---

Als eines der zentralen Entwurfsmuster von DigiKAR dient das Datenmodell zur Modellierung von Herrschaftsrechten. Dazu eignet sich die Klasse `C14 Holding of a Right or Obligation` aus der CRM-Erweiterung [SDHSS (Semantic Data for Humanities and Social Sciences)](https://ontome.net/namespace/11) als Ausgangsbasis für die Zusammenstellung des Anwendungsprofils aus existierenden CRM- und SDHSS-Klassen und -Eigenschaften.
 

## Schema-Diagramm

![Schema-Diagramm](/DigiKAR-Ontology-Design/img/dmlo-place-affilation.svg)


## Beispieldaten

Angaben zur Grundherrschaft aus der Datenbank des [HOV (Historische Ortsverzeichnis von Sachsen)](https://hov.isgv.de/) gemäß dem DigiKAR-Entwurfsmuster modelliert:

```turtle
@prefix crm: <http://www.cidoc-crm.org/cidoc-crm/> .
@prefix dmlr-document: <http://digikar.eu/resource/document/> .
@prefix dmlr-place: <http://digikar.eu/resource/place/> .
@prefix dmlv-affiliation: <http://digikar.eu/vocabulary/affiliation/> .
@prefix dmlv-right: <http://digikar.eu/vocabulary/right/> .
@prefix frbroo: <http://iflastandards.info/ns/fr/frbr/frbroo/> .
@prefix rdfs: <http://www.w3.org/2000/01/rdf-schema#> .
@prefix sdh-so: <https://ontome.net/namespace/112/> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .

dmlr-place:hov_10001 sdh-so:P8i_is_subject_to [ 
  a sdh-so:C14_Holding_of_a_Right_or_Obligation ;
  crm:P4_has_time-span [ a crm:E52_Time-Span ;
    crm:P3_has_note "1764" ;
    crm:P82a_begin_of_the_begin "1764-01-01"^^xsd:date ;
    crm:P82b_end_of_the_end "1764-12-31"^^xsd:date ] ;
  crm:P70i_is_documented_in dmlr-document:hov ;
  sdh-so:P29_has_holding_of_a_right_type dmlv-right:manorial ;
  sdh-so:P9_is_right_of "Amtsdorf" ], [ 
  a sdh-so:C14_Holding_of_a_Right_or_Obligation ;
  crm:P4_has_time-span [ a crm:E52_Time-Span ;
    crm:P3_has_note "1547" ;
    crm:P82a_begin_of_the_begin "1547-01-01"^^xsd:date ;
    crm:P82b_end_of_the_end "1547-12-31"^^xsd:date ] ;
  crm:P70i_is_documented_in dmlr-document:hov ;
  sdh-so:P29_has_holding_of_a_right_type dmlv-right:manorial ;
  sdh-so:P9_is_right_of "Domkapitel Meißen" ] .

dmlr-document:hov a frbroo:F2_Expression ;
    rdfs:label "Digitales Historisches Ortsverzeichnis von Sachsen" .    
```


## Competency Questions

1. Zu welchen weltlichen oder geistlichen Verwaltungseinheiten gehören die Orte?
2. Welche grundherrschaftlichen Zugehörigkeiten gibt es zu einem Ort?


## SPARQL-Beispielabfragen

SPARQL-Abfrage der Orte mit Zugehörigkeiten zu weltlichen Verwaltungseinheiten:

```sparql
PREFIX crm: <http://www.cidoc-crm.org/cidoc-crm/>
PREFIX dct: <http://purl.org/dc/terms/>
PREFIX geo: <http://www.opengis.net/ont/geosparql#>
PREFIX sdh-so: <https://ontome.net/namespace/112/>

PREFIX dmlo: <http://digikar.eu/ontology/>

PREFIX dmlv-place: <http://digikar.eu/vocabulary/place/>
PREFIX dmlv-right: <http://digikar.eu/vocabulary/right/>

SELECT ?place ?administrative_entity ?begin ?end ?source WHERE { 
  ?place a dmlo:Place ;
    rdfs:label ?label .

  ?place sdh-so:P8i_is_subject_to ?affiliation .
  ?affiliation sdh-so:P29_has_holding_of_a_right_type dmlv-right:administrative ;
    sdh-so:P9_is_right_of ?administrative_entity ;
    crm:P4_has_time-span/crm:P82a_begin_of_the_begin ?begin ;
    crm:P4_has_time-span/crm:P82b_end_of_the_end ?end ;
    crm:P70i_is_documented_in ?source .
} ORDER BY DESC(?label)
```

SPARQL-Abfrage der Orte mit grundherrschaftlicher Zugehörigkeit zu Grundherren -- in der Suche wird unterschieden zwischen normalisierten Einträgen zu den Grundherren (Variable `?right_owner_entity`) und ggf. noch nicht normalisierten Einträgen (Variable `?right_owner_literal`):

```sparql
PREFIX crm: <http://www.cidoc-crm.org/cidoc-crm/>
PREFIX dct: <http://purl.org/dc/terms/>
PREFIX geo: <http://www.opengis.net/ont/geosparql#>
PREFIX sdh-so: <https://ontome.net/namespace/112/>

PREFIX dmlo: <http://digikar.eu/ontology/>

PREFIX dmlv-place: <http://digikar.eu/vocabulary/place/>
PREFIX dmlv-right: <http://digikar.eu/vocabulary/right/>

SELECT ?place ?right_owner_entity ?right_owner_literal ?right_owner_index ?affiliation_type ?begin ?end ?source WHERE { 
  ?place a dmlo:Place ;
    rdfs:label ?label .

  ?place sdh-so:P8i_is_subject_to ?affiliation .
  ?affiliation sdh-so:P29_has_holding_of_a_right_type dmlv-right:manorial ;
    #sdh-so:P9_is_right_of ?right_owner ;
    crm:P4_has_time-span/crm:P82a_begin_of_the_begin ?begin ;
    crm:P4_has_time-span/crm:P82b_end_of_the_end ?end ;
    crm:P70i_is_documented_in ?source .

  OPTIONAL {
    ?affiliation sdh-so:P9_is_right_of ?right_owner_entity 
    FILTER(isURI(?right_owner_entity)) 
  }

  OPTIONAL {
    ?affiliation sdh-so:P9_is_right_of ?right_owner_literal 
    FILTER(isLiteral(?right_owner_literal)) 
  }

  OPTIONAL {
    ?affiliation crm:P2_has_type ?affiliation_type 
  }

  OPTIONAL {
    ?affiliation dmlo:hasIndex ?right_owner_index  
  } 

} ORDER BY DESC(?label)

```

## OWL-Datei


## SHACL-Constraints


## Axiomatisierung


## Hinweise auf ähnliche Entwurfsmuster

- [Linked Places Format](https://github.com/LinkedPasts/linked-places-format) bzw. [Linked Pasts Ontology](https://github.com/LinkedPasts/linked-pasts-ontology) mit `relations`- und `relationType`-Einträgen
- Datenmodell des Historischen Atlas von Bayern (HAB)


## Relevante verfügbare Datensätze

- HOV-Datenbankdump
- RepSax-Datenbankdump

