---
layout: page
title: Ontologie-Entwurfsmuster zur Modellierung von Aktivitäten von Personen für Institutionen oder Personen
permalink: /odp/activity/
categories: ODP
---

## Schema-Diagramm

![Schema-Diagramm](../img/dmlo-actor-activity.svg)


## Beispieldaten


## Competency Questions

1. Welche Rolle spielte eine Person in einer sozialen Beziehung?
2. Welche Rolle spielte eine Person in einer beruflichen Tätigkeit?


## SPARQL-Beispielabfragen

Abfrage zur Ermittlung aller Aktivitäten in denen eine Person eine Rolle (Funktion) spielt:

```sparql
PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>
PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>
PREFIX crm: <http://www.cidoc-crm.org/cidoc-crm/>

SELECT * WHERE {
  ?activity a crm:E7_Activity .
  ?person_role crm:P01_has_domain ?activity ;
    crm:P02_has_range ?person ;
    crm:P14.1_in_the_role_of ?function .
  ?person a crm:E21_Person .
} 
```


## OWL-Datei


## SHACL-Constraints


## Axiomatisierung



## Hinweise auf ähnliche Entwurfsmuster


https://docs.swissartresearch.net/pattern/temporal/#agent-role-in-the-activity


https://docs.swissartresearch.net/et/persons/#social-relations



Modellierung der Rollen von Personen in Ereignissen in
CRM (RDF) als n-äre Relation: https://docs.swissartresearch.net/pattern/general/##roles



## Relevante verfügbare Datensätze


Germania Sacra – biographische Daten aus Gatz, Bischöfe 1648 bis 1803 (Quelle):
https://doi.org/10.26015/adwdocs-33

https://wiag-vocab.adw-goe.de/bischof

https://wiag-vocab.adw-goe.de/domherr

- [Die Bischöfe des Alten Reiches nach Erwin Gatz. Basisdaten und Normdaten (Datensammlungen der Germania Sacra. Materialien zur Kirche des Alten Reiches 3), Göttingen 2021.](https://doi.org/10.26015/adwdocs-33)


https://adw-goe.de/artikel/das-geistiliche-personal-des-domstifts-mainz/

Das geistliche Personal des Domstifts Mainz, bearbeitet von der Redaktion der Germania Sacra (Germania Sacra. Prosopographische Studien 4), https://doi.org/10.26015/adwdocs-2481, Göttingen 2022.


Time indexed participation 
http://ontologydesignpatterns.org/wiki/Submissions:Time_indexed_participation

Time indexed person role
http://ontologydesignpatterns.org/wiki/Submissions:Time_indexed_person_role

