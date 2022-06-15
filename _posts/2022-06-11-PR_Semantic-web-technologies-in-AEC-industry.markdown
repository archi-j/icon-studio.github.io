---
layout: post
title: "[Paper Reading] Semantic web technologies in AEC industry: A literature overview"
date: 2022-06-11 09:00:00 +0300
description: 2017_Semantic web technologies in AEC industry: A literature overview # Add post description (optional)
img: 20220611_post_main.jpg # Add image post (optional) 280px, 350px, 470px, 700px, 940px
fig-caption: # Add figcaption (optional)
category: [PR]
tags: [BIM, IFC, Smantic Web]
---

**Publication year:** 2017 <br>
**Authors:** Pieter Pauwels, Sijie Zhang, Yong-Cheol Lee<br>
**DOI:** [https://doi.org/10.1016/j.autcon.2016.10.003](https://doi.org/10.1016/j.autcon.2016.10.003)


## Introduction
- Building Information Modeling (BIM) and beyond
  - Rather than just adopting software applications, which simply display geometric perspectives and views of a building, or lengthy textual descriptions and spreadsheets of unstructured data, the industries have made significant progress towards the development of a robust semantic structure and a well-organized semantic connectivity map.
  - As BIM research in itself has a lot of focus on ‘information’ tends to stress on the ways in which information can be made available for addressing the core research challenges. In addition, this significant focus on information has led to increased attention on efficient usage and smooth exchange of data and information, across the various application areas in the building life-cycle.
  - IoT standards have been proposed to allow and improve communication between the multiple devices and systems available in the construction sites and offices, regardless of the system or application features.
- The advent of semantic web technologies in the AEC domain
  - Considering this high focus on combinations of information and data, it comes as no surprise that there has been an increasing interest in the use of semantic web technologies and linked data technologies. Semantic web technologies namely allow to represent information in structured graphs and efficiently integrate building information of an entirely different nature. As a result, the development of software applications that rely on multiple information sources is within reach.
    - Early articles focusing on the added value of semantic web technologies similarly see these technologies as one of the diverse sets of web technologies that can bring improvements to information exchange in the construction industry.
    - Secondly, semantic web technologies were found useful to increase the value of BIM by enabling data integration and complex search queries across several data sources.
    - With the increase of the application of sensing technology in the construction site, the third added value brought by semantic web technology is to incorporate sensing technology to manage construction document information in the field.
- Promises and expectancies
  - The primary question this article investigates is what has been and can be obtained by adopting semantic web or linked data technologies for the AEC industries.
    1. Interoperability: The usage of semantic web technologies has been considered as an opportunity to improve interoperability in the AEC industries [16–21], thus resulting in an integrated and successful data exchange environment.
    2. Linking across domains: Second, semantic web technologies provide the option to link information stemming from diverse domains (e.g. BIM, GIS, heritage, sensor data, simulation data, smart cities) into one web of linked building data.
    3. Logical inference and proofs: A third and last topic that is often used in arguing for the adoption of semantic web technologies in the architectural design and construction industry, is the underlying logical foundations of the language(s) used by semantic web technologies. An appropriate usage of the language thus allows the inference of extra information from the originally represented information.
  - It is not always clear what the difference is between “interoperability” and “linking across domains”. We consider interoperability to be the challenge to load the same content in multiple applications. Linking across domains is considered here as the challenge to combine different content that is available in multiple applications (e.g. cost data, energy simulation data, geometrical data, GIS data).
- Methodology
  - We investigated the most recent articles pertaining to semantic web technologies in the AEC industry in order to identify the development and application progress of semantic web technologies in this industry according to the three topical axes outlined above.
  - Instead of making a purely quantitative analysis of articles, as was for example done for BIM research in Yalcinkaya and Singh,we have made a qualitative assessment of the information in the surveyed papers and critically analyzed to what extent contributions are made to validating any of the three outlined topical axes.

## Semantic web technologies
- The RDF core
  - At the core of the semantic web stands a flexible and generic language that allows to easily represent and combine information from diverse knowledge domains, namely RDF. The semantic web thus becomes a semantic network in which information is represented as directed labeled graphs (RDF graphs). Each node in such a graph represents a concept or object in the world, identified with a Unique Resource Identifier (URI). By describing all information as such in interlinked directed labeled graphs, a uniform representation of information is achieved, making information reusable by both humans and computer applications.
  - The most basic elements describing such ontologies are contained in the RDF Schema (RDFS) vocabulary, which consists of the specifications of classes, subclasses, comments, and data types. An RDFS interpreter is able to infer extra RDF statements that are implicitly available via the RDFS constructs. More expressive elements to describe ontologies are available within OWL. In short, OWL further enhances the RDFS concepts to allow making more complex RDF statements, such as cardinality restrictions, type restrictions, and complex class expressions. The RDF graphs constructed with OWL concepts are called OWL ontologies.
  - RDF(S) and OWL provide the basis to allow working with rules and proofs. By relying on rules and proofs, it is possible to build applications that reach particular levels of trust, precisely because of the way in which they deploy their rules and build their proofs.
- OWL semantics and OWL profiles
  - As in the case of OWL, also OWL2 has a number of so-called profiles, namely OWL2 EL, OWL2 QL and OWL2 RL
- Closed World Assumption (CWA) vs. Open World Assumption (OWA)
  - According to CWA, any statement that is not known to be true,must be considered as false.When applied to a BIM model, one can conclude that whenever something is not specified in the model, it is most definitely not there.On the other hand, according to OWA, a statement that is not known to be true, is not necessarily false,nor true, but unknown.
  - Many traditional software applications adopt a CWA, including BIM tools and common database systems. Semantic web technologies, however, generally rely on an OWA because the technologies are supposed to be used on the Web, which is a system with incomplete information.
  - The difference between CWA and OWA plays a key role when an ontology is used to represent a BIM model, because if something is not specified, then one cannot conclude much, except that it might still be true or false. A whole different kind of information usage and inference becomes available
  - the OWA of semantic web technologies is still something different from the traditional CWA features in current software applications.
- Linked data vs. semantic web
  - Other terms that can regularly be found in relation to semantic web technologies are linked data, web of data, and semantic web

## Aim 1: interoperability
- Interoperability standards
  - The desire for interoperability in the AEC domain was the key driver behind the International Alliance for Interoperability (IAI), now commonly known as BuildingSMART International. The efforts by this community have evolved into the Industry Foundation Classes (IFC) data model, along with a number of other standards (mvdXML, IFD, IDM).
  - Building model data in a BIM authoring tool can be exported and imported to another tool using the IFC STEP Physical File Format (SPFF) following ISO 10303-21
  - IFC is defined in the EXPRESS schema. The IFC release also contains the IFC schema defined in the XSD schema (ISO 10303-28), which allows building models to be shared as ifcXML files. The purpose of providing this alternative format is to leverage accessibility and applicability of the IFC schema through the XML format, which has been broadly used in other industry domains. Similarly, the ifcOWL ontology is proposed and maintained as a second alternative schema
  - There are a number of challenges in using the IFC schema in EXPRESS as a means for achieving interoperability.
    1. Binding
      - Compatibility with the IFC schema, however, highly depends on implementation and usage practice because heterogeneous IFC translation and binding processes of each BIM authoring tool could result in unintended geometric transformations and semantic errors
    2. Adaptability
      - various industry domains and software vendors require a tremendous amount of work to agree upon and generate the compliant IFC schema and associated specifications. It thus requires a significant amount of time to reach consensus on its content, representation and definition scope, so that the schema typically does not encompass state-of-the-art technology and newly-launched construction methods.
    3. Extensibility
      - If one wants to express information that is not available as such in the IFC schema (and he does not know how to do this in EXPRESS), IfcProxy concepts and custom IFC property sets can be used. However, these are semantically very loose additions, in the sense that anybody who wishes to use this information will need to manually interpret strings in their application logics.
- A semantic alternative
  - In response to the earlier outlined challenges, it was therefore investigated whether semantic web technologies might provide an alternative technical means to address the interoperability issue
  - The BuildingSMART LDWG has therefore produced an ifcOWL ontology that can serve as a domain ontology for the construction industry. The LDWG working group has heavily relied on earlier proposals to convert the IFC schema into an OWL ontology and to convert IFC STEP Physical Files (SPF) into RDF graphs that follow the ifcOWL ontology
  - Further modifications and extensions to the ifcOWL ontology are now proposed, based on critical ontological analysis and tested alternative suggestions.
- Binding parallel representations
  - Of course, adopting semantic web technologies (ifcOWL) cannot address bad implementation and usage practices. However,
    1. as they provide a single data model (RDF) for representing any kind of information;
    2. as they allow adding a logical DL basis to this representation using OWL;
    3. as they focus intensively on linking diverse graphs of information together in a web-like fashion,
    - semantic web technologies might be the ideal technical means to provide interoperability while also allowing to flexibly handle new semantic structures
  - An IFC, X3D and STL representation of a box can all be interlinked in diverse ways, but if one of these representations changes, the same changes should also be made for the other two representations in an interoperable system.
  - Link sets
    - One interesting solution proposed in El-Gohary and El-Diraby is an ontology integrator (Onto-Integrator) for facilitating ontology interoperability within the AEC domains. The Onto-Integrator offers a heuristic for ontology merging, including the merging of concept taxonomies, relations, and axioms.
    - Furthermore, Törmä argues for the need for instance-level interoperability in addition to ontologylevel or schema-level interoperability. This is particularly important when actual exchange of partial models (requirement model, architectural model, MEP model) takes place, in which the key challenge is to find out which elements in the diverse partial elements are actually identical
    - There is no mechanism or suggestion made in the semantic web domain to properly deal with this situation. This leaves a high risk of redundancy and inconsistency of information. For example, Scherer et al. [19] and Törmä[69] propose to implement this transition mechanism with linked data technologies, which results in ‘linksets’: sets of links that represent the relationships between partial models (i.e. the blue circular arrows in Fig. 5). These linksets still need to be managed through human intervention though.
  - Mapping schemas in formal rules
    - Assuming that all RDF graphs in the central web of data follow a specific OWL ontology, and thus have a solid formal structure, it should be possible to devise a mapping schema between specific pairs of schemas. By representing that mapping schema in formal rules, one can use an inference engine to automatically infer data in alternative ontologies, starting from data in a master ontology or central ontology
    - In theory, this approach of mapping schemas in formal rules can also be used in the context of Model View Definitions (MVDs). An MVD is a subset of the building product model schema (the IFC schema) that provides a complete representation of BIM exchange data needed for a particular domain of the AEC industries. MVDs are currently captured in mvdXML files. The information that is currently captured in an mvdXML file can also be captured using semantic web rules (SWRL, N3Logic, and other) or SPARQL CONSTRUCT queries
    - In principle, this would allow to ‘query’ the complete IFC/RDF file and automatically output the required subset on demand. One advantage of this approach is that the process can be implemented using regular semantic web technologies, including out-of-the-box inference engines, triple stores and query interpreters. The greatest advantage of this approach, however, is likely that it allows a far more flexible mechanism to generate subsets. Both semantic web rules and SPARQL construct queries namely allow to output information that does not have to follow the IFC schema (as opposed to a regular MVD subset). As such, output might be generated that automatically matches the semantic information structure of a target program, hence supporting interoperability in an alternative fashion (mapping schemas in formal rules).
    - The two main components in this architecture, the Federal Controllor (FC) and the Federal Descriptor (FD) are placed in-between a knowledge base and a user interface (Fig. 6). These two components take into account the ontologies used in the query coming from the user interface and translate the query via ontology alignments and inference mechanisms to the ontology structures used in the knowledge base.

## Aim 2: linking across domains
- Some of these approaches are more closely affiliated to linked data rather than semantic web technologies, although ontologies equally often play a crucial role as well. When specifically relying on ontologies, the key research question is often related to the creation of domain ontologies, which aim at providing a shared representation for the concepts within a domain of knowledge, and how they should be linked together and still remain useful
- Collaborative information management
- Product manufacturer data
- Building performance analysis
- Regulation compliance checking
- Geographical and infrastructure data

## Aim 3: logical inference and proofs
- Regulation compliance checking
- Interoperability and model handling
- Inference processes within regular use cases

## Conclusion
- Application areas for semantic web technologies
- Key research challenges
