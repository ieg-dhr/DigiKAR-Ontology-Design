---
layout: page
name: Punktkoordinaten eines Ortes
title: Ontologie-Entwurfsmuster zur Modellierung von Punktkoordinaten eines Ortes
permalink: /odp/centroid/
categories: ODP
---

Das Entwurfsmuster dient in erster Linie dazu, um Punktkoordinaten eines Ortes für die Darstellung von weiterer ortsbasierter Information über den Ort auf einer Karte. Die Ermittlung der Punktkoordinaten zur geographischen Verortung sollte nach einer Konvention erfolgen, wie dass z.B. die Position der Kirche als Zentrum eines Dorfs zur Bestimmung der Punktkoordinaten verwendet wird. Die Erfassung des Ortsmittelpunkts erfolgt praktischerweise anhand der Eigenschaft [`has centroid`](https://opengeospatial.github.io/ogc-geosparql/geosparql11/#hascentroid) aus der [GeoSPARQL-Ontologie](http://www.opengis.net/ont/geosparql). Die Angaben zur Quelle der Koordinaten (z.B. eine historische Karte) werden mit dem Entwurfsmuster für Quellenangaben erfasst. Sollte von der Konvention zur Ermittlung der Zentrumskoordinaten abgewichen werden müssen, sollte das entsprechend begründet in den Angaben vermerkt werden.

## Schema-Diagramm

![Schema-Diagramm](/DigiKAR-Ontology-Design/img/dmlo-place-centroid.svg)


## Beispieldaten

Die Ortsdaten in der Datenbank des [HOV (Historische Ortsverzeichnis von Sachsen)](https://hov.isgv.de/) umfassen auch Punktkoordinaten und können bei der Aufbereitung und Konvertierung der Daten in das DigiKAR-Datenmodell mit dem Enturfsmuster für Punktkoordinaten eines Ortes modelliert werden:

```turtle
@prefix crm: <http://www.cidoc-crm.org/cidoc-crm/> .
@prefix dct: <http://purl.org/dc/terms/> .
@prefix dmlr-document: <http://digikar.eu/resource/document/> .
@prefix dmlr-place: <http://digikar.eu/resource/place/> .
@prefix frbroo: <http://iflastandards.info/ns/fr/frbr/frbroo/> .
@prefix geo: <http://www.opengis.net/ont/geosparql#> .
@prefix owl: <http://www.w3.org/2002/07/owl#> .
@prefix rdfs: <http://www.w3.org/2000/01/rdf-schema#> .
@prefix sf: <http://www.opengis.net/ont/sf#> .

dmlr-place:hov_10001 a crm:E92_Spacetime_Volume ;
  rdfs:label "Abend" ;
  dct:identifier "10001" ;
  geo:hasCentroid [ a sf:Point ;
    crm:P70i_is_documented_in dmlr-document:hov ;
    geo:asWKT "POINT(12.408333 51.131944)" ] .
    
  dmlr-document:hov a frbroo:F2_Expression ;
    rdfs:label "Digitales Historisches Ortsverzeichnis von Sachsen" .
    
```


## Competency Questions

1. Zu welchen Orten liegen Punktkoordinaten vor?


## SPARQL-Beispielabfragen

```
PREFIX dmlr: <http://digikar.eu/resource/>
PREFIX dmlr-place: <http://digikar.eu/resource/place/>
PREFIX dmlr-document: <http://digikar.eu/resource/document/>
PREFIX crm: <http://www.cidoc-crm.org/cidoc-crm/>
PREFIX geo: <http://www.opengis.net/ont/geosparql#>
PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>

SELECT ?place ?label ?point WHERE {
  ?place a dmlo:Place ;
    geo:hasCentroid/geo:asWKT ?point ;
    rdfs:label ?label .
}
ORDER BY ?label
```


## OWL-Datei


## SHACL-Constraints


## Axiomatisierung


## Hinweise auf ähnliche Entwurfsmuster

- Die Klasse `E47 Spatial Coordinates` aus der CRM-Ontologie könnte als -- vergleichsweise ähnlich einfache -- Alternative in einem Entwurfsmuster verwendet werden.
- Das [Ontologie-Entwurfsmuster zur Modellierung der räumlichen Ausdehnung eines Ortes](/DigiKAR-Ontology-Design/odp/presence/) kann verwendet werden, um ggf. Punktkoordinaten zu verschiedenen Zeiten sowie aus verschiedenen Quellen zu modellieren.


## Relevante verfügbare Datensätze

- HOV-Datenbankdump

