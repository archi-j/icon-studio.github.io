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

## Aim 1: interoperability
- Interoperability standards
- A semantic alternative
- Binding parallel representations
  - Link sets
  - Mapping schemas in formal rules

## Aim 2: linking across domains
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
