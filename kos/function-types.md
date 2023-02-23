---
layout: page
title: Funktion
permalink: /kos/function-types/
categories: KOS
tags: SKOS, Concept Scheme, 
---

## Klassifikationssystem für Funktionen

Die Begriffe im Klassifikationssystem Funktion (Präfix `dmlv-function:`) dienen zur Typisierung der Funktion von Personen.

Auszug aus der RDF-Turtle-Repräsentation des Klassifikationssystems:

```turtle
@prefix dmlv-function: <http://digikar.eu/vocabulary/function/> .

@prefix skos: <http://www.w3.org/2004/02/skos/core#> .
@prefix rdfs: <http://www.w3.org/2000/01/rdf-schema#> .


dmlv-function: a skos:ConceptScheme ;
  rdfs:label "Funktion";
  skos:notation "fu" ;
  skos:prefLabel "Funktion"@de ;
  skos:prefLabel "Function"@en ;
  dct:description "Kontrolliertes Vokabular zur Klassifikation der Funktionen von Personen."@de ;
  skos:hasTopConcept dmlv-function:amt ; 
  skos:hasTopConcept dmlv-function:pupil ; 
  skos:hasTopConcept dmlv-function:student ; 
  skos:hasTopConcept dmlv-function:kin ;
  skos:hasTopConcept dmlv-function:member 
.

dmlv-function:amt a skos:Concept ;
  rdfs:label "Amt" ;
  skos:notation "amt" ;
  skos:prefLabel "Amt"@de ;
  skos:prefLabel "Amt"@en ;
  skos:inScheme dmlv-function: ;
  skos:narrower dmlv-function:secular-function ;
  skos:narrower dmlv-function:ecclesiastical-function ;
  skos:editorialNote "Dieser Begriff dient testweise als Sammelbegriff für alle möglichen Ämter und deren Aufteilung in weltliche und kirchliche Ämter." 
.

dmlv-function:secular-function a skos:Concept ;
  rdfs:label "weltliches Amt" ;
  skos:notation "secular-function" ;
  skos:prefLabel "weltliches Amt"@de ;
  skos:prefLabel "Secular office"@en ;
  skos:inScheme dmlv-function: ;
  skos:broader dmlv-function:amt ;
  skos:narrower dmlv-function:amtmann ; 
  skos:narrower dmlv-function:teacher ;
  skos:narrower dmlv-function:elector ; 
.

dmlv-function:amtmann a skos:Concept ;
  rdfs:label "Amtmann" ;
  skos:notation "amtmann" ;
  skos:prefLabel "Amtmann"@de ;
  skos:prefLabel "Amtmann"@en ;
  skos:inScheme dmlv-function: ;
  skos:broader dmlv-function:secular-function ;
  skos:altLabel "Domprobsteiamtmann" ,
    "markgräflich baden-badischer Oberamtmann" , 
    "sächsischer Oberamtmann" , 
    "kurmainzischer Amtmann" , 
    "gräflich waldbott-bassenheimischer Oberamtmann" , 
    "fürstlich hohenlohe-waldenburg-schillingsfürstischer Amtmann" , 
    "fürstlich hohenlohe-waldenburg-schillingsfürstischer Oberamtmann" , 
    "Amtmann, stellvertretender" ; 
  skos:editorialNote "Der interessante Fall 'Amtmann, stellvertretender' in der Synonymliste müsste evtl. doch als eigener Unterbegriff eingeordnet werden, da dieser Spezialfall eines stellvertretenden Amtmanns ggf. bei der Verknüpfung mit Ortstdaten als explizite Angabe benötigt wird." ; 
  skos:editorialNote "In der Synonymliste kommen nicht durchgehend weltliche Ämter vor: siehe Eintrag 'Domprobsteiamtmann'!" 
.

dmlv-function:teacher a skos:Concept ;
  rdfs:label "Lehrer" ;
  skos:notation "teacher" ;
  skos:prefLabel "Lehrer"@de ;
  skos:prefLabel "Teacher"@en ;
  skos:inScheme dmlv-function: ;
  skos:broader dmlv-function:secular-function ;
  skos:altLabel "Lehrer der Mathematik" ;
  skos:editorialNote "Ist mit 'Lehrer' ggf. auch die Rolle einer Person in einer sozialen Beziehungen (Lehrer-Schüler-Verhältnis) gemeint?!"
.

dmlv-function:elector a skos:Concept ;
  rdfs:label "Kurfürst" ;
  skos:notation "elector" ;
  skos:prefLabel "Kurfürst"@de ;
  skos:prefLabel "Elector"@en ;
  skos:inScheme dmlv-function: ;
  skos:broader dmlv-function:secular-function 

.

dmlv-function:bishop a skos:Concept ;
  rdfs:label "Bischof" ;
  skos:notation "bishop" ;
  skos:prefLabel "Bischof"@de ;
  skos:prefLabel "Bishop"@en ;
  skos:inScheme dmlv-function: ;
  skos:broader dmlv-function:ecclesiastical-function ;
  skos:narrower dmlv-function:cardinal ;
  skos:altLabel "Weihbischof" , 
    "Erzbischof" , 
    "Chorbischof" 
.

dmlv-function:cardinal a skos:Concept ;
  rdfs:label "Kardinal" ;
  skos:notation "cardinal" ;
  skos:prefLabel "Kardinal"@de ;
  skos:prefLabel "Cardinal"@en ;
  skos:inScheme dmlv-function: ;
  skos:broader dmlv-function:bishop ;
  skos:narrower dmlv-function:pope  
.

dmlv-function:pope a skos:Concept ;
  rdfs:label "Papst" ;
  skos:notation "pope" ;
  skos:prefLabel "Papst"@de ;
  skos:prefLabel "Pope"@en ;
  skos:inScheme dmlv-function: ;
  skos:broader dmlv-function:cardinal 
.

dmlv-function:pupil a skos:Concept ;
  rdfs:label "Schüler" ;
  skos:notation "pupil" ;
  skos:prefLabel "Schüler"@de ;
  skos:prefLabel "Pupil"@en ;
  skos:inScheme dmlv-function: ;
  skos:altLabel "Schülerin"
.

dmlv-function:student a skos:Concept ;
  rdfs:label "Student" ;
  skos:notation "student" ;
  skos:prefLabel "Student"@de ;
  skos:prefLabel "Student"@en ;
  skos:inScheme dmlv-function: ; 
  skos:altLabel "stud." , 
    "stud. iur." , 
    "stud. phil." , 
    "stud. iur" , 
    "stud. theol." , 
    "stud. iur. " , 
    "Student [?]" , 
    "stud. [theol.]" , 
    "stud. phill." , 
    "logicae studiosus" , 
    "stud. phil" , 
    "stud. phil. / physicus" ; 
  skos:editorialNote "Gender-neutral oder nicht?" 
.

dmlv-function:kin a skos:Concept ;
  rdfs:label "Verwandtschaft" ;
  skos:notation "kin" ;
  skos:prefLabel "Verwandtschaft"@de ; # Verwandtschaft 
  skos:prefLabel "Kin"@en ;
  skos:inScheme dmlv-function: ;
  skos:narrower dmlv-function:child ;
  skos:narrower dmlv-function:father ;
  skos:narrower dmlv-function:mother ;
  skos:narrower dmlv-function:grandfather ;
  skos:narrower dmlv-function:baptised 
.

```

