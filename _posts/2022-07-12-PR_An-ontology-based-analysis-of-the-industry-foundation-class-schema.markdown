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
  - Description logics (DL) and frame-based systems are tools that enable the researchers to represent knowledge in a structured way that support automated reasoning. A DL model consists of a domain and an interpretation function. The domain is the set of objects and the interpretation function is a mapping from individual, class, and property names to elements of the domain, subsets of the domain and binary relations on the domain
  - The key feature of DL’s is that they are formal languages with well-defined semantics. Importance is given to formally defined relationships (i.e., subsumption, equivalence) between the objects. DL help information to be shared without any misinterpretation of the terminology and their meaning.
  - An important advantage of formalizing the terminology is that automated reasoning of business rules to check consistency of classes and model view definitions becomes possible. However, there are trade-offs between providing expressivity and formal tractability. It is a computational balance, which is important in the case of rich schemas like IFC. It is important that the constructors and axioms developed can support practical decision procedures.
- Engineering ontology
  - Ontology is a formal representation of an abstracted view of a domain that describes the objects, concepts and relationships between them that holds in that domain for a stated purpose. There are different classifications of ontologies, based on parameters such as level of granularity, their use and types of relationships
  - The Knowledge Interchange Format (KIF) is an formal approach used for knowledge exchange among computer programs that are different in nature [34]. The semantics of KIF are based on the correlation between the terms and sentences of the language and the conceptualization of the world in terms of objects, functions and relations. KIF uses declarative semantics for representing the meaning of expressions using first order predicate calculus and reasoning rules.
  - F-Logic is another approach, where well-defined semantics of logics are integrated with frame-based languages to provide formal semantics and resolution-based proof procedures. This was developed particularly as a database logic language comprising the object-oriented features such as object identity, complex objects, inheritance, methods, and rules
  - Structure–function–behavior (SFB or SBF or FBS) is another knowledge representation paradigm for engineered products where information is grouped according to the material and geometry of the product’s structure, the model’s function, and behavior in order to construct a clear, consistent, computable, and widely useful model
- Semantic web technologies
  - Semantic web is an example of inter-linked data available in a standard format, reachable and manageable by automated tools. Similar sets of issues are faced by the semantic web development effort as are found in IFC interoperability.
  - Extensible markup language (XML) was developed to separate the markup of web content from presentation, thereby streamlining task specific and domain specific data. XML is widely used on the web and has been successfully implemented as an exchange format for EXPRESS data. Representing model views in XML, called mvdXML, provides a computer readable format, however it lacks formulating axioms and cannot be considered an ontology.
  - BuildingSMART has recognized mvdXML as the standard for representing model views [47]. Providing a formal ontological structure from which mvdXMLs can be generated would be beneficial to the industry. RDF strives to add a formal definition to the web by providing a data model and syntax conventions based on the obj ect–attribute–value
  - The main advantage of RDF over basic XML is that RDF can define a basic set of terms with specifiable meanings in the form of a schema or layer on top, called RDFS. Using a schema with entities such as rdfs:class, rdfs:subclass, rdfs:property, rdfs:domain, and rdfs:range we can model a hierarchy of classes and properties with domains and restrictions. In RDF, the schema is separate from the data and any model can reference and share the schema (like IFC). XML Schema definition language, on the other hand, is a direct machine-readable mapping from IFC to XML schema, facilitating automated mapping
  - Web ontology language (OWL) is the formal ontology language developed for the semantic web. There are two alternative ways to provide semantics in OWL, direct semantics or RDF-based semantics. OWL data types are based on the XML schema definition language (XSD). OWL data types are based on the XML schema definition language (XSD). OWL/XML, which is an XML serialization, provides users with a variety of options to process information using XML tools.

## Framework for interoperability in AEC/FM
- Research questions
  - Can a well-defined method for semantic classification and representation of IFC entities be developed? The practical objective of this goal is to determine a data model that can represent the range of semantic structures needed to address building model semantics.
  - The longer term objective is to adapt IFC schema to support easy definition of model views that are consistent, testable, extensible and re-usable across various domains in the AEC/FM industry.
- Research methodology
  - The first step in the framework is an in-depth analysis of the IFC product modeling schema to identify the explicit semantic classes needed to distinguish the different meanings and related issues in model exchanges.
  - The second phase involves the development of an ontology-based definition for IFC based on the classifications defined in the first phase. This phase includes the preparation of a knowledge base, setting up the modeling criteria, and assumptions.
  - Semantic Exchange Modules (SEM) provide the additional implementation layer in the form of object-oriented libraries developed on top of the ontology. The ontology layer provides the abstract structure of the schema, whereas, the object-oriented layer provides the actual implementation structure in the form of data and code.
  - Validation and verification, which form the final phase, are concerned with ensuring semantic correctness of the defined product. For the purpose of the research in this paper, these questions can be translated to verification focuses on the correctness of the mvdXML structure developed in relation to the ontology and validation equates to checking whether the mvdXML development-based ontologies actually cover the semantic needs identified.

## Ontology building
- The objective of the ontology development is to remove ambiguities associated with differing viewpoints and formalize IFC definitions for a robust model exchange solution
- In order for the importing application to infer semantic knowledge from the exchange, the exporting application should structure the data based on an agreed upon standard. The ontology definitions provide a means to remove ambiguity regarding those different meanings in such scenarios, by using constraints that define the relationships and also provide equivalences between individuals.
- Once the ontology is developed and validated, it can then be applied to other domains as well such as cast-in place concrete and steel industry. Protégé and web ontology language (OWL) are the tools that are used to represent knowledge in a structured and reasonable way and the final model view is in the form of mvdXML.

## Ontology definitions
- Part-whole relationships
- Spatial rules
- Overlapping volumes
- Feature based modeling
- Connections and systems

## Applications of ontology definitions
- Some comparison of component ontology and the IFC schema
- Defining a new classification structure based on ontology definitions
  - The focus of this comparative study begins at the IfcElement level and classifies the hierarchy based on definitions from the ontology.
  - A breadth first approach has been followed to divide the elements into two broad groups namely, (a) primary building elements and (b) element components.
  - PrimayBuildingElements = [IfcBeam, IfcChimney, IfcColumn, IfcCurtainWall, IfcDoor, IfcFooting, IfcMember, IfcPile, IfcRamp, IfcRoof, IfcSlab, IfcStair, IfcWall, IfcWindow, IfcProxyBuildingElement]
  - ElementParts = [IfcCovering, IfcRampFlight, IfcStairFlight, IfcBuildingElementPart, IfcDoor, IfcWindow]
  - The ontology structure allows defining a more logical and consistent semantic structure to the building elements, defined as concepts. An important benefit of this classification is that, ideally based on their function, different users, as well as the software implementers can unambiguously define classes.

## Conclusion and outlook
- This research outlines a possible foundation for the development and implementation of a new integrated framework that is expected to define a clearer and less ad hoc structure for IFC. The new structure, like the current IFC is extensible. In addition, the method and classifications of extensions are well defined. This research has shown the usefulness of ontologies for specifying consistent implementation structures using IFC.
- Product model schemas such as IFC are rich, but redundant. Based on the insights gathered from developing the Precast National BIM Standard and further analysis as part of this research, a new methodology based on ontological definition of the IFC schema is introduced. The definition of a Precast System Ontology is explained.
- Based on the analysis, it is shown that MVD development process needs to be transitioned from the current ad hoc manner to a more rigorous framework and/or methodology similar to the one explained in this research.
- Future work might include an ontology-based object-oriented library for model view development, testing, and certification. An ontology specifies how the application functionality is to be implemented and it serves roles similar to entity-relationship (ER) diagrams, object models, and object patterns. In the case of model exchanges, the ontology is intended to provide the structure of the model view.
- For this purpose, the ontology layer developed in this research is converted to an object-oriented class library. This additional layer of mapping is used for implementation. IFC entities, relations, attributes, etc. are mapped onto the application ontology developed in the previous phase.
- This significantly lowers the barriers for practitioners (software developers).This library is developed to be extensible and it is envisioned that future model views will be developed based on this library.
