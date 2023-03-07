---
title: Ontologie-Entwurfsmuster zur Modellierung von Ortsnamen eines Ortes
layout: page
permalink: /odp/names/
categories: ODP
---

Information über historische Ortsnamen bzw. Ortsnamensvarianten gehören zu den grundlegenden Angaben, die in einem Gazetteer hinterlegt sein sollten. Zur Modellierung historischer Orstnamen und deren zeitlicher Gültigkeit wird im Entwurfsmuster die CRM-Klasse `E41 Appellation` und die Klasse `F52 Name Use Activity` aus der CRM-Erweiterung FRBRoo verwendet. Die Klasse `F52 Name Use Activity` ist eine Unterklasse der CRM-Klasse `E13 Attribute Assignment` und ermöglicht somit die Modellierung Attributen, die einer Entität zugeschrieben werden -- so wie eben Ortsnamen für einen bestimmten Zeitraum zur Bezeichnung eines Ortes verwendet worden sind.

## Schema-Diagramm

![Schema-Diagramm](/DigiKAR-Ontology-Design/img/dmlo-place-name.svg)


## Beispieldaten

Ortsnamen für Mainz aus der [Topographia Germaniae (1646)](https://de.wikisource.org/wiki/Topographia_Colonia_et_al.) extrahiert:

```turtle
@prefix crm: <http://www.cidoc-crm.org/cidoc-crm/> .
@prefix dmlo: <http://digikar.eu/ontology/> .
@prefix dmlr-document: <http://digikar.eu/resource/document/> .
@prefix frbroo: <http://iflastandards.info/ns/fr/frbr/frbroo/> .
@prefix rdfs: <http://www.w3.org/2000/01/rdf-schema#> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .

dmlr-place:M1 a dmlo:Place ;
    rdfs:label "Mainz" ;
    frbroo:R63i_was_named_by [ a frbroo:F52_Name_Use_Activity ;
            frbroo:R64_used_name [ a crm:E41_Appellation ;
                    crm:P190_has_symbolic_content "Mainz" ] ;
            crm:P4_has_time-span [ a crm:E52_Time-Span ;
                    crm:P81a_end_of_the_begin "1646"^^xsd:gYear ] ;
            crm:P70i_is_documented_in dmlr-document:topographia_1646 ],
        [ a frbroo:F52_Name_Use_Activity ;
            frbroo:R64_used_name [ a crm:E41_Appellation ;
                    crm:P190_has_symbolic_content "Moguntiaco" ] ;
            crm:P4_has_time-span [ a crm:E52_Time-Span ;
                    crm:P81a_end_of_the_begin "1646"^^xsd:gYear ] ;
            crm:P70i_is_documented_in dmlr-document:topographia_1646 ],            
        [ a frbroo:F52_Name_Use_Activity ;
            frbroo:R64_used_name [ a crm:E41_Appellation ;
                    crm:P190_has_symbolic_content "Magonza" ] ;
            crm:P4_has_time-span [ a crm:E52_Time-Span ;
                    crm:P81a_end_of_the_begin "1646"^^xsd:gYear ] ;
            crm:P70i_is_documented_in dmlr-document:topographia_1646 ],
        [ a frbroo:F52_Name_Use_Activity ;
            frbroo:R64_used_name [ a crm:E41_Appellation ;
                    crm:P190_has_symbolic_content "Mogontiacum" ] ;
            crm:P4_has_time-span [ a crm:E52_Time-Span ;
                    crm:P81a_end_of_the_begin "1646"^^xsd:gYear ] ;
            crm:P70i_is_documented_in dmlr-document:topographia_1646 ],
        [ a frbroo:F52_Name_Use_Activity ;
            frbroo:R64_used_name [ a crm:E41_Appellation ;
                    crm:P190_has_symbolic_content "Magontiaco" ] ;
            crm:P4_has_time-span [ a crm:E52_Time-Span ;
                    crm:P81a_end_of_the_begin "1646"^^xsd:gYear ] ;
            crm:P70i_is_documented_in dmlr-document:topographia_1646 ],
        [ a frbroo:F52_Name_Use_Activity ;
            frbroo:R64_used_name [ a crm:E41_Appellation ;
                    crm:P190_has_symbolic_content "Moguntiacum" ] ;
            crm:P4_has_time-span [ a crm:E52_Time-Span ;
                    crm:P81a_end_of_the_begin "1646"^^xsd:gYear ] ;
            crm:P70i_is_documented_in dmlr-document:topographia_1646 ],
        [ a frbroo:F52_Name_Use_Activity ;
            frbroo:R64_used_name [ a crm:E41_Appellation ;
                    crm:P190_has_symbolic_content "Maguntiacum" ] ;
            crm:P4_has_time-span [ a crm:E52_Time-Span ;
                    crm:P81a_end_of_the_begin "1646"^^xsd:gYear ] ;
            crm:P70i_is_documented_in dmlr-document:topographia_1646 ],
        [ a frbroo:F52_Name_Use_Activity ;
            frbroo:R64_used_name [ a crm:E41_Appellation ;
                    crm:P190_has_symbolic_content "Maguntia" ] ;
            crm:P4_has_time-span [ a crm:E52_Time-Span ;
                    crm:P81a_end_of_the_begin "1646"^^xsd:gYear ] ;
            crm:P70i_is_documented_in dmlr-document:topographia_1646 ],
        [ a frbroo:F52_Name_Use_Activity ;
            frbroo:R64_used_name [ a crm:E41_Appellation ;
                    crm:P190_has_symbolic_content "Mentz" ] ;
            crm:P4_has_time-span [ a crm:E52_Time-Span ;
                    crm:P81a_end_of_the_begin "1646"^^xsd:gYear ] ;
            crm:P70i_is_documented_in dmlr-document:topographia_1646 ],
        [ a frbroo:F52_Name_Use_Activity ;
            frbroo:R64_used_name [ a crm:E41_Appellation ;
                    crm:P190_has_symbolic_content "Mogontia" ] ;
            crm:P4_has_time-span [ a crm:E52_Time-Span ;
                    crm:P81a_end_of_the_begin "1646"^^xsd:gYear ] ;
            crm:P70i_is_documented_in dmlr-document:topographia_1646 ],
        [ a frbroo:F52_Name_Use_Activity ;
            frbroo:R64_used_name [ a crm:E41_Appellation ;
                    crm:P190_has_symbolic_content "Mongontiacum" ] ;
            crm:P4_has_time-span [ a crm:E52_Time-Span ;
                    crm:P81a_end_of_the_begin "1646"^^xsd:gYear ] ;
            crm:P70i_is_documented_in dmlr-document:topographia_1646 ],
        [ a frbroo:F52_Name_Use_Activity ;
            frbroo:R64_used_name [ a crm:E41_Appellation ;
                    crm:P190_has_symbolic_content "Mayance" ] ;
            crm:P4_has_time-span [ a crm:E52_Time-Span ;
                    crm:P81a_end_of_the_begin "1646"^^xsd:gYear ] ;
            crm:P70i_is_documented_in dmlr-document:topographia_1646 ],
        [ a frbroo:F52_Name_Use_Activity ;
            frbroo:R64_used_name [ a crm:E41_Appellation ;
                    crm:P190_has_symbolic_content "Maguntiacus" ] ;
            crm:P4_has_time-span [ a crm:E52_Time-Span ;
                    crm:P81a_end_of_the_begin "1646"^^xsd:gYear ] ;
            crm:P70i_is_documented_in dmlr-document:topographia_1646 ],
        [ a frbroo:F52_Name_Use_Activity ;
            frbroo:R64_used_name [ a crm:E41_Appellation ;
                    crm:P190_has_symbolic_content "Maguntiaco" ] ;
            crm:P4_has_time-span [ a crm:E52_Time-Span ;
                    crm:P81a_end_of_the_begin "1646"^^xsd:gYear ] ;
            crm:P70i_is_documented_in dmlr-document:topographia_1646 ],
        [ a frbroo:F52_Name_Use_Activity ;
            frbroo:R64_used_name [ a crm:E41_Appellation ;
                    crm:P190_has_symbolic_content "Moguntia" ] ;
            crm:P4_has_time-span [ a crm:E52_Time-Span ;
                    crm:P81a_end_of_the_begin "1646"^^xsd:gYear ] ;
            crm:P70i_is_documented_in dmlr-document:topographia_1646 ],
        [ a frbroo:F52_Name_Use_Activity ;
            frbroo:R64_used_name [ a crm:E41_Appellation ;
                    crm:P190_has_symbolic_content "Magotia" ] ;
            crm:P4_has_time-span [ a crm:E52_Time-Span ;
                    crm:P81a_end_of_the_begin "1646"^^xsd:gYear ] ;
            crm:P70i_is_documented_in dmlr-document:topographia_1646 ] ;
            
dmlr-document:topographia_1646 a frbroo:F2_Expression ;
    rdfs:label "Topographia (1646)" .
```


## Competency Questions

1. Seit wann ist der Ortsname in Gebrauch?
2. Von wann bis wann war der Ortsname in Gebrauch?
3. Vom wem wurde der Ortsname eingeführt?
4. Wo oder vom wem war der Ortsname in Gebrauch?
5. Welche Ortsnamen sind zu den Orten erfasst?


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
    frbroo:R63i_was_named_by ?place_name_use .
  ?place_name_use frbroo:R64_used_name/crm:P190_has_symbolic_content ?name ;
    crm:P70i_is_documented_in dmlr-document:topographia_1646 .
}
ORDER BY ?name
```

## Hinweise auf ähnliche Entwurfsmuster

- [Place Reference Data Model](https://docs.swissartresearch.net/et/place/#names-and-classifications) aus dem Musterkatalog von SARI (Swiss Art Research Infrastructure)
- FRBRoo-Klasse `F52 Name Use Activity` zur Modellierung eines zeitabhängigen Ortsnamens


## Relevante verfügbare Datensätze

- DigiKAR-Datensatz mit Ortsnamen (historische Ortsnamen, Ortsnamensvarianten) aus der [Topographia Germaniae (1646)](https://de.wikisource.org/wiki/Topographia_Colonia_et_al.)

