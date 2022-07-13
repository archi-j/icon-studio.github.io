---
layout: post
title: "[Paper Reading] An ontology-based analysis of the industry foundation class schema for building information model exchanges"
date: 2022-07-12 09:00:00 +0300
description: "2015_An ontology-based analysis of the industry foundation class schema for building information model exchanges" # Add post description (optional)
img: 20220712_post_main.jpg # Add image post (optional) 280px, 350px, 470px, 700px, 940px
fig-caption: # Add figcaption (optional)
category: [PR]
tags: [BIM, IFC, Semantic Web]
---

**Publication year:** 2015 <br>
**Authors:** Manu Venugopal, Charles M.Eastman, Jochen Teizer<br>
**DOI:** [https://doi.org/10.1016/j.aei.2015.09.006](https://doi.org/10.1016/j.aei.2015.09.006)


## Introduction
- Industry Foundation Classes (IFC) provide a rich, redundant but ambiguous schema for interoperability. An important issue is that IFC lacks semantic clarity in mapping entities and relationships, resulting in the potential for multiple data structures to represent the same information. This is necessary because building models require different semantics for different workflows over a project’s lifecycle.
- The objective of the research reported here is to define an ontological framework which makes the IFC definitions more formal and consistent such that data provide an improved basis of information exchanges than what exists today. A formal specification of IFC entities to create a taxonomy of the classes is outlined. Various issues such as the need for a logical framework, the current semantic approaches in the AEC/FM industry, and advantages of building an ontology structure are addressed.
- Model exchanges based on IFC are still file-based and errorprone [7]. Errors still occur when both translators involved in exchange are IFC compliant; exported data needed for a targeted exchange but semantically not understood by the importing application. Hence, object schemas such as IFC are necessary but not sufficient for achieving robust data exchanges.
- Lacking is a formal framework for deriving semantically driven views from models generated from different applications. Moreover, the granularity and atomicity with which such model views are defined is not consistent across the industry [8]. This adds to the overhead for software developers and hinders IFC based implementations. In order for that to happen, additional levels of specificity are required to define model exchange requirements and model views in a formal, consistent, modular, and reusable manner.

## Background
- BIM interoperability in the cloud realm
  - The National BIM StandardTM initiative (NBIMS) [11] proposes facilitating information exchanges through model view definitions (MVD) [12–14]. A model view is defined as a subset of the building product model schema that provides a complete representation of the information concepts needed for a particular use-case in an AEC workflow
  - The model view approach defines the appropriate information entities from a schema for particular exchange requirements (ER) and the rules regarding their instance population. This step is performed by documenting them in an information delivery manual (IDM), and mapping these to the IFC schema definitions defined in a MVD
  - Two sets of semantics are at the core of any model view specification [8], namely: (i) the user/application functional semantics defining the information that must be exchanged and (ii) the representational semantics available in IFC or other data-modeling schema for representing the user intentions.
  - IFC is highly object-oriented supporting inheritance, polymorphism, and extensibility. Objects are represented as functional classes connected through objectified relationships and attributes. IFC supports multiple kinds of representations and open-ended value properties. As the coverage of the schema has grown, it has become difficult to keep the extensions and modifications semantically consistent.
  - Exchange models are found to be repetitive and these repetitive specifications, which form the building blocks of a MVD, were termed IFC Concepts. The idea of IFC Concepts was introduced as a means of modularizing MVD development and also for improving re-usability. However, the two public support facilities available for model views assume varying levels of granularity and atomicity of the building blocks for an MVD
  - GTDS aims to automate the testing of IFC files based on validation rules that formalize the constraints imposed by the model view definition. Export test instructions, import calibration test files, validation rules, and more are under development to automate the certification workflow based on IFC Concepts.
  - However, this approach has several limitations as well, such that testing cannot be complete as there is no means to verify the semantic correctness of relationships and patterns of entities. On the other hand, the IFC solutions factory approaches concepts from a microscopic level, whereby each and every IFC entity is defined as a concept
- IFC semantics
  - There are other ambiguous relationship entities. Assemblies are defined with IfcRelAggregate relation. An aggregation is a general collection of entities of varied type. Currently, no distinction is made between objects assembled so they cannot overlap (steel assemblies) and those that can overlap (cast-in-place concrete elements). This makes the general computation of properties of an assembly often impossible or erroneous.
- Summary
  - The current status of model exchanges using IFC is summarized as follow:
    1. IFC is rich and redundant offering multiple ways to define objects and relationships (to reflect user intention).
    2. The development of an information delivery manual (IDM) is based on industry knowledge and human expertise.
    3. The translation from IDM to MVD is largely manual and requires significant trial-and-error.
    4. The base concepts for exchange (IFC Concepts) are not strictly defined and as a result have multiple versions.
    5. The IDM/MVD is not based on logic foundations, and hence, the application of machine-based reasoning mechanisms is not possible.
    6. The require level of detail for most model exchanges is not specified.


## Knowledge representation mechanisms
- Formal methods
- Engineering ontology
- Semantic web technologies

## Framework for interoperability in AEC/FM
- Research questions
- Research methodology

## Ontology building

## Ontology definitions
- Part-whole relationships
- Spatial rules
- Overlapping volumes
- Feature based modeling
- Connections and systems

## Applications of ontology definitions
- Some comparison of component ontology and the IFC schema
- Defining a new classification structure based on ontology definitions

## Conclusion and outlook
- This research outlines a possible foundation for the development and implementation of a new integrated framework that is expected to define a clearer and less ad hoc structure for IFC. The new structure, like the current IFC is extensible. In addition, the method and classifications of extensions are well defined. This research has shown the usefulness of ontologies for specifying consistent implementation structures using IFC.
- Product model schemas such as IFC are rich, but redundant. Based on the insights gathered from developing the Precast National BIM Standard and further analysis as part of this research, a new methodology based on ontological definition of the IFC schema is introduced. The definition of a Precast System Ontology is explained.
- Based on the analysis, it is shown that MVD development process needs to be transitioned from the current ad hoc manner to a more rigorous framework and/or methodology similar to the one explained in this research.
- Future work might include an ontology-based object-oriented library for model view development, testing, and certification. An ontology specifies how the application functionality is to be implemented and it serves roles similar to entity-relationship (ER) diagrams, object models, and object patterns. In the case of model exchanges, the ontology is intended to provide the structure of the model view.
- For this purpose, the ontology layer developed in this research is converted to an object-oriented class library. This additional layer of mapping is used for implementation. IFC entities, relations, attributes, etc. are mapped onto the application ontology developed in the previous phase.
- This significantly lowers the barriers for practitioners (software developers).This library is developed to be extensible and it is envisioned that future model views will be developed based on this library.
