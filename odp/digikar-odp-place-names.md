---
title: Ontologie-Entwurfsmuster zur Modellierung von Ortsnamen eines Ortes
layout: page
permalink: /odp/names/
categories: ODP
---

## Schema-Diagramm

Information über historische Ortsnamen bzw. Ortsnamensvarianten gehören zu den grundlegenden Angaben, die in einem Gazetteer hinterlegt sein sollten. Zur Modellierung historischer Orstnamen und deren zeitlicher Gültigkeit wird im Entwurfsmuster die CRM-Klasse `E41 Appellation` und die Klasse `F52 Name Use Activity` aus der CRM-Erweiterung FRBRoo verwendet. Die Klasse `F52 Name Use Activity` ist eine Unterklasse der CRM-Klasse `E13 Attribute Assignment` und ermöglicht somit die Modellierung Attributen, die einer Entität zugeschrieben werden -- so wie eben Ortsnamen für einen bestimmten Zeitraum zur Bezeichnung eines Ortes verwendet worden sind.


## Beispieldaten



## Competency Questions


## SPARQL-Beispielabfragen

Die folgende SPARQL-Abfrage liefert als Ergebnis eine Liste von Namensvarianten für den Ort (Siedlungstyp Stadt) Mainz, wie sie aus der Topographia (1646) entnommen wurden.

```sparql
PREFIX crm: <http://www.cidoc-crm.org/cidoc-crm/>
PREFIX frbroo: <http://iflastandards.info/ns/fr/frbr/frbroo/>
PREFIX dmlr: <http://digikar.eu/resource/>
PREFIX dmlr-place: <http://digikar.eu/resource/place/>
PREFIX dmlr-document: <http://digikar.eu/resource/document/>

SELECT ?name WHERE {
  dmlr-place:M1 
    crm:P1_is_identified_by ?place_name .
  ?place_name crm:P190_has_symbolic_content ?name ;
    crm:P70i_is_documented_in dmlr-document:topographia_1646 .
}
ORDER BY ?name
```


## OWL-Datei


## SHACL-Constraints


## Axiomatisierung



## Hinweise auf ähnliche Entwurfsmuster

- [Place Reference Data Model](https://docs.swissartresearch.net/et/place/#names-and-classifications) aus dem Musterkatalog von SARI (Swiss Art Research Infrastructure)
- FRBRoo-Klasse `F52_Name_Use_Activity` zur Modellierung eines zeitabhängigen Ortsnamens


## Relevante verfügbare Datensätze

