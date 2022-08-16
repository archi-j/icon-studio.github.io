---
layout: post
title: "[Paper Reading] Ontology-based representation of IFC EXPRESS rules: An enhancement of the ifcOWL ontology"
date: 2022-08-07 09:00:00 +0300
description: "2015_Ontology-based representation of IFC EXPRESS rules: An enhancement of the ifcOWL ontology" # Add post description (optional)
img: 20220807_post_main.jpg # Add image post (optional) 280px, 350px, 470px, 700px, 940px
fig-caption: # Add figcaption (optional)
category: [PR]
tags: [BIM, IFC, Semantic Web]
---

**Publication year:** 2015 <br>
**Authors:** Walter Terkaj, Aleksandra Šojić<br>
**DOI:** [https://doi.org/10.1016/j.autcon.2015.04.010](https://doi.org/10.1016/j.autcon.2015.04.010)


## Introduction
- The Semantic Web (SW) technologies provide a modeling environment that can deal with heterogeneous data, supporting interoperability across diverse knowledge domains, integration of distributed data and employment of reasoning engines to infer new knowledge automatically.
- In this paper, we take into consideration the existing efforts in the direction of the IFC to OWL conversion. While taking an OWL version of IFC (named ifcOWL [5]) as a reference, we propose an enhancement of the conversion pattern in order to optimize its applicability.
- The conversion of the rules into the OWL version of IFC may enable the direct instantiation of the ontology without going through the generation of STEP files and afterwords checking the consistency of IFC projects, whatever is their origin.
- the enrichment of the ifcOWL ontology allows both to safely use general purpose SW tools and to develop new ifcOWL-based software tools while minimizing inconsistencies and erroneous applications of the standard.
- an OWL version of IFC (named ifcOWL) can be better integrated with other ontologies to support interoperability, while making use of data distribution capabilities; moreover, general purpose reasoning engines can be directly employed to infer new knowledge.

## State of the art
- The IFC model is structured into four layers: Resource layer (i.e. general purpose or low level concepts/objects), Core Layer (where the most abstract concepts of the model are defined), Interoperability Layer defining concepts or objects common to two or more domains, and the Domains/Application Layer
- The emergence of SW technologies led to several initiatives aimed at converting the IFC schema into an ontology language that can provide a semantically rich and platform independent framework to support the integration and interoperability of software tools and exchange of data in a knowledge based system that are human readable and processable by machines.

## IFC to OWL conversion pattern
- This section instead focuses the attention on the most recent development in this research field that was proposed by Pauwels. The key features of the conversion pattern are outlined together with a few examples that are relevant for the analysis carried out in the following sections

## Conversion of IFC rules into OWL class expressions
- In this section we propose an enhancement of the ifcOWL ontology by partially revising the conversion criteria defined by Pauwels. The criteria A and B (i.e. keeping ifcOWL in OWL DL profile and enriching the ifcOWL with axioms to match the original EXPRESS schema as closely as possible) are preserved, but criterion C (i.e. primarily supporting the conversion of IFC STEP physical files into equivalent RDF files) is excluded and replaced by the following one.

## Implementation of the conversion patterns
- The conversion patterns presented in the previous section have been implemented into a C++ program that makes use of programming libraries built on the Redland RDF libraries
- This program implements a set of general purpose routines for the automatic generation of OWL class expressions that are similar in structure to statements (65), (67), (70)–(72) defined for IfcWindow, IfcWindowType and IfcWindowPanelProperties.

## Ontology-based software tool exploiting additional OWL class expressions
- This section presents OntoGUI, an ontology-based software tool that can be employed in the management and instantiation of Abox ontology modules. This tool mainly aims at supporting:
  - The fast evaluation of ontology Tbox by concurrently instantiating a corresponding Abox, following a Test-driven development approach.
  - The generation of RDF data sets to be used as input for other ontologybased applications, without needing to develop complex customized graphical user interfaces or data converters.

## Concluding remarks
- The analysis of a test case under CWA and OWA scenarios has demonstrated that the additional class expressions allow the detection of impermissible relationships between individuals, thus showing how different conversion strategies can lead to more accurate (and even more reliable) ontological representations of the IFC standard.
- The relevance of the new class expressions has been discussed also in the scope of software development by addressing the case of the ontology-based software tool OntoGUI.
- The class expressions allow this tool to correctly create relations between object types, object occurrences, and pre-defined property sets while avoiding hard-coded implementations and enhancing the consistency and integrity of data on the level of application.
- Further developments are foreseen to address the following open issues:
  - IFC property and quantity sets have not yet been considered in the literature about EXPRESS to OWL conversion because they are not included in the EXPRESS schema, but attached to the IFC specification as XML files. However, the XML definition can be converted to OWL by creating new pre-defined property sets.
  - WHERE rules that constrain the feasible values of EXPRESS defined data types (e.g. IfcPositiveInteger and IfcTextAlignment)canbe converted to class expressions consisting in restrictions on OWL datatype properties (owl:DatatypeProperty). This conversion pattern would be general purpose and not limited to the IFC schema.
  - Further WHERE rules declarations in the IFC schema may be successfully converted into customized class expressions.
  - Implicit rules in the IFC standard could be made explicit in its OWL version.
