---
layout: page
title: Ontologie-Entwurfsmuster zur Modellierung der räumlichen Ausdehnung eines Ortes
permalink: /odp/presence/
categories: ODP
---

Mit dem Entwurfsmuster kann die räumliche Ausdehnung eines Ortes modelliert werden. Typischerweise geschieht dies durch Polygone. Es ist aber durch den Einsatz des WKT-Formats möglich, auch nur Punktkoordinaten anzugeben. Das Entwurfsmuster ist um die CRM-Klasse `E93 Presence` aufgebaut, womit mit den zugehörigen [CRMgeo](https://www.cidoc-crm.org/crmgeo/)-Elementen modelliert werden kann, welchen geographischen Raum ein Ort während einer bestimmten Zeit eingenommen hat. Dabei kann es sich etwa um die Fläche eines Anwesens oder die Grenzen einer Stadt oder auch eines geistlichen oder weltlichen Verwaltungsgebiets handeln. In der Definition und Beschreibung der Klasse `E93 Presence` ist in der CRM-Dokumentation als passendes Beispiel die Ausdehung des Römischen Reichs im Jahr 33 v.Chr. aufgeführt.


## Schema-Diagramm

![Schema-Diagramm](/DigiKAR-Ontology-Design/img/dmlo-place-presence.svg)

## Beispieldaten

Der Germania Sacra-Datensatz zu den Bistümern des Alten Reiches enthält auch Polygon-Daten zur rnäumliche Ausdehnung der Bistümer. Diese Daten können durch entsprechende Transformation in die Struktur des DigiKAR-Datenmodells gebracht werden (WKT-Polygondaten gekürzt):

```turtle
@prefix crm: <http://www.cidoc-crm.org/cidoc-crm/> .
@prefix dct: <http://purl.org/dc/terms/> .
@prefix dmlo: <http://digikar.eu/ontology/> .
@prefix dmlr-document: <http://digikar.eu/resource/document/> .
@prefix dmlr-place: <http://digikar.eu/resource/place/> .
@prefix frbroo: <http://iflastandards.info/ns/fr/frbr/frbroo/> .
@prefix geo: <http://www.opengis.net/ont/geosparql#> .
@prefix owl: <http://www.w3.org/2002/07/owl#> .
@prefix prism: <http://prismstandard.org/namespaces/basic/2.0/> .
@prefix rdfs: <http://www.w3.org/2000/01/rdf-schema#> .
@prefix sf: <http://www.opengis.net/ont/sf#> .

dml-place:gs_17 a dmlo:Place ;
  rdfs:label "Bistum Meissen" ;
  dct:identifier 17 ;
  crm:P166i_had_presence [ a crm:E93_Presence ;
    crm:P164_is_temporally_specified_by [ a crm:E52_Time-Span ;
      crm:P81a_end_of_the_begin "1500-01-01"^^xsd:date ;
      crm:P81b_begin_of_the_end "1806-08-06"^^xsd:date ] ;
    crm:P167_was_within [ a crmgeo:SP6_Declarative_Place ;
      crm:P70i_is_documented_in dmlr-document:gs ;
      crmgeo:P168_place_is_defined_by [ a geo:SP15_Geometry ;
        geo:asWKT "POLYGON ((13.750167 52.406361, ..., 13.750167 52.406361))" ] ] ] ;
  crm:P41i_was_classified_by [ a crm:E17_Type_Assignment ;
    crm:P42_assigned dmlv-place:bi ;
    crm:P70i_is_documented_in dmlr-document:gs ] .
    
    
dmlr-document:gs a efrbroo:F2_Expression ;
  rdfs:label "Bistumsgrenzen Altes Reich (nur Germania Sacra)  1500" ;
  prism:doi "10.26015/adwdocs-34" ;
  dcat:landingPage <https://doi.org/10.26015/adwdocs-34> .

```


## Competency Questions

1. Zu welchen Orten liegen Geodaten (Polygone etc.) vor?
2. Welche Geodaten gibt es zu einem Territorium?
3. Gibt es Geodaten zu Territorium X im WKT-Format?
4. Aus welcher Quellen stammen die Geodaten?
5. Zu welchen Territorien gibt es mehrere Geodaten aus verschiedenen Quellen?


## SPARQL-Beispielabfragen

```
PREFIX dmlo: <http://digikar.eu/ontology/>
PREFIX dmlr: <http://digikar.eu/resource/>
PREFIX dmlr-place: <http://digikar.eu/resource/place/>
PREFIX dmlr-document: <http://digikar.eu/resource/document/>
PREFIX crm: <http://www.cidoc-crm.org/cidoc-crm/>
PREFIX crmgeo: <http://www.ics.forth.gr/isl/CRMgeo/>
PREFIX geo: <http://www.opengis.net/ont/geosparql#>
PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>

SELECT ?place ?label ?geo WHERE {
  ?place a dmlo:Place ;
    crm:P166i_had_presence/crm:P167_was_within/crmgeo:P168_place_is_defined_by/geo:asWKT 
      ?geo ;
    rdfs:label ?label .
}
ORDER BY ?label
```


## OWL-Datei


## SHACL-Constraints


## Axiomatisierung


## Hinweise auf ähnliche//verwandte Entwurfsmuster

- Mit dem [Linked Places Format](https://github.com/LinkedPasts/linked-places-format) bzw. der [Linked Pasts Ontology](https://github.com/LinkedPasts/linked-pasts-ontology) kann eine oder mehrere (zu verschiedenen Zeiten) GeoJSON-Geometrien modelliert werden.  
- Die CRM-Erweiterung CRMgeo wird auch in den im Folgenden verlinkten Datenmodellen zur Modellierung voneinander abweichender Angaben zur territorialen Ausdehnung oder zu Grenzverläufen in verschiedenen historischen Quellen verwendet: 
  - Francesco Beretta (für [GEO-LARHRA](http://geo-larhra.org/))
  - Vincent Ducatteeuw (siehe [digitalhistory: Vincent Ducatteeuw: Developing an urban gazetteer: modelling historical platial information, in: Digital History Berlin (Blog), erschienen am: 10. Januar 2022](https://dhistory.hypotheses.org/1055))



## Relevante verfügbare Datensätze

- [Die Grenzen der Bistümer des Alten Reiches um 1500. Rekonstruktion der Germania Sacra anhand publizierter Karten und Quellenmaterialien (Datensammlungen der Germania Sacra. Materialien zur Kirche des Alten Reiches 4), Version 2, Göttingen 2022.](https://doi.org/10.26015/adwdocs-34)
- [Viabundus-Datensatz Town outlines](http://www.landesgeschichte.uni-goettingen.de/handelsstrassen/index.php#download)



