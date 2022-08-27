---
layout: post
title: "[Paper Reading] Metadata Schemas and Ontologies for Building Energy Applications: A Critical Review and Use Case Analysis"
date: 2022-08-17 09:00:00 +0300
description: "2021_Metadata Schemas and Ontologies for Building Energy Applications: A Critical Review and Use Case Analysis" # Add post description (optional)
img: 20220817_post_main.jpg # Add image post (optional) 280px, 350px, 470px, 700px, 940px
fig-caption: # Add figcaption (optional)
category: [PR]
tags: [Metadata, Ontology, Semantic Web]
---

**Publication year:** 2021 <br>
**Authors:** Marco Pritoni, Drew Paine, Gabriel Fierro, Cory Mosiman, Michael Poplawski, Avijit Saha, Joel Bender and Jessica Granderson<br>
**DOI:** [https://doi.org/10.3390/en14072024](https://doi.org/10.3390/en14072024)


## Introduction
- In the U.S., they are responsible for 39% of primary energy, 74% of electricity, and 38% of national carbon emissions, with similar impacts in other industrialized economies. A typical commercial building has also been shown to waste 30% of its energy consumption, attributable to suboptimal design, construction, and operational processes.
- Digitalization of Building Data
  - In the past decade, the integration of intelligence (e.g., microcontrollers and microcomputers), sensors, and networking (i.e., Internet of Things (IoT) connectivity) has become more common in all types of buildings. These systems can generate significant amounts of data if they record operational parameters with time intervals on the order of seconds or minutes
  - The scalability of building applications, such as energy audits, fault detection, and diagnostic and optimal controls (see Section 4), is currently hindered by the lack of standardization in metadata schemas that represent the meaning of the data. This issue is generally referred to as a lack of semantic interoperability.
- Interoperability Frameworks and the Role of Semantic Interoperability
  - The technical layer focuses on the digital exchange of data between two systems, including the physical, network, and syntactic aspects of the messages. The information layer deals with the semantics of the data, as well as its integration with business processes and procedures. The organization layer relates to business objectives and policy context.
  - Technical interoperability between devices can be achieved through use of the same communication protocol or by using communication gateways that allow messages to be translated between protocols. However, a lack of interoperability in the semantic layer is currently a significant problem that hinders the streamlined integration of interdependent software applications and the development of applications that can be reused across buildings
- Ontologies and the Semantic Web
  - Semantic models, also called semantic or metadata schemas, contain information that describes the meaning of the underlying data. They vary in complexity, from simple lists of terms (e.g., types of sensors), called glossaries or dictionaries, to taxonomies that encode a specific hierarchical relationship
  - Ontologies establish the domain’s concepts and relationships, classes, and attributes.
- Contribution of This Review
  - In the building domain, several parallel initiatives are using Semantic Web technologies to develop metadata schemas. While these are promising endeavors, there is growing confusion over their scope and overlap, and a review of such efforts would be beneficial to the building community.
  - This paper builds on previous research and provides a unique contribution by:
    - combining a systematic approach to reviewing the academic and gray literature with a deeper analysis of a select number of ontologies and use cases that have high value for building control and analytics applications affecting energy concerns
    - surveying schemas that cover multiple stages of the building life cycle
    - providing the reader with a comprehensive list of metadata schemas that are documented and publicly available
  - this work aims at answering the following research questions:
    - RQ1: What is the landscape of building-related metadata schemas/ontologies in the academic/gray literature?
    - RQ2: Given a selection of relevant ontologies, what are the overlaps and gaps among these metadata schemas that support building operational applications?
    - RQ3: How does this subset of schemas support a building

## Method
- To ensure a systematic approach, we used the previously developed preferred reporting items for systematic reviews and meta-analyses (PRISMA) approach.
- This method defines a set of steps to identify, screen, and select papers for formal review. Since new semantic models are introduced and documented in both academic as well as technical literature (e.g., standards, technical reports), we coupled a search of papers using the Scopus search engine with a survey of schemas based on informal ontology databases and expert searches. The identification of the articles used the following criteria, applied to the title, abstract, and keywords using the Scopus article search tool
- For papers, the screening was conducted by manually analyzing the title and abstract and looking for papers presenting original ontologies. While this process was designed to be linear, a small number of schemas were identified from references in the eligibility phase, in an iterative process conventionally called snowball sampling

## Results of the Review: Metadata Schemas for Buildings
- Definitions
  - Information Stack (Knowledge Hierarchy)
    - Information science scholars have proposed to use a hierarchy of concepts, known as the DIKW pyramid, to distinguish between data and more abstract concepts, such as information, knowledge, and wisdom
  - Metadata
    - Metadata is the information used to describe, present, or link other information. An example of metadata is the labels that describe the sensors in a BAS
  - Schema, Taxonomy, Ontology, and Linked Data
    - A schema refers to a data model that represents the relationships between a set of concepts. Some types of schemas include relational database schemas, taxonomies, and ontologies.
    - A taxonomy is a formal representation of relationships between items in a hierarchical structure.
    - An ontology (sometimes called a vocabulary) is a formal model that allows knowledge to be represented for a specific domain. An ontology describes the types of things that exist (classes), the relationships between them (properties), and the logical ways those classes and properties can be used together (axioms)
  - Tag, Tagging, and Folksonomy
    - A tag is an arbitrary text label associated with a resource or piece of data. Tagging is the process of annotating resources with tags by users (folks).
  - Model and Instance
    - In the literature, the term model is sometimes used as a synonym of schema (e.g., an ontology is a model) and sometimes used to describe an instance of a schema (e.g., a Brick model of a specific building). In this review, we will use the former definition.
  - Knowledge Base
    - A knowledge base is a type of database that contains information instead of raw facts
- Metadata Schemas
  - Schemas for Building Design and Energy Modeling
    - The IFC standard is widely used in industry, and its latest version was published in 2018. Green Building XML (gbXML) is another popular schema aimed at enabling exchange of information between a BIM and architectural/engineering analysis software, including Building Energy Modeling (BEM)
  - Schemas for Building Operations: Sensor Networks, IoT, and Smart Homes
  - Schemas for Building Operations: Commercial Building Automation and Monitoring
  - Schemas for Building Operations: Grid-Interactive Efficient Building (GEB) Applications
  - Schemas for Building Operations: Occupants and Behavior
  - Schemas for Building Operations: Asset Management and Audits

## Use Cases
- Use Case 1: Energy Audits
- Use Case 2: Automated Fault Detection and Diagnostics
- Use Case 3: Optimal Control of HVAC
- Core Concepts

## Results of the Review: Assessing Core Concepts in Five Ontologies
- Building Topology Ontology (BOT)
- Semantic Sensor Network/Sensor, Observation, Sample, and Actuator (SSN/SOSA)
- Smart Applications REFerence Ontology (SAREF) and Extensions
- RealEstateCore (REC)
- Brick Schema

## Discussion and Conclusions
- This paper presented a systematic survey of metadata schemas for building energy applications across the building life cycle to address three research questions.
  1. The Landscape of Metadata Schemas for Building Energy Applications
    - BIM commercial software packages implement some features of these standards differently, and some only support a specific subset of features (e.g., 3D architectural elements)
    - extension of BIMs to building operations still remains far from being realized in practice. However, some of the operation-focused schemas reviewed try to borrow concepts derived from the design phase
    - IoT schemas surveyed are just a small fraction of the total ontologies cited in other reviews.
    - Fourteen different schemas have been identified that describe metadata about controls and metering in commercial buildings, but from this high-level review, the overlaps between them and their gaps are unclear.
    - Collecting and identifying these schemas proved to be a challenging task. The search using Scopus was ineffective, since the title and abstract were often insufficient to determine whether the paper was presenting a new ontology that met the criteria specified
    - The search of ontologies using databases was also problematic. While centralized repositories of ontologies exist in other disciplines, this is not the case for building-related ontologies. This is probably a reflection of the heterogeneity of the academic communities working on buildings
    - Another challenge in collecting information about metadata schemas is that they may change in time. Similar to software packages, these schemas may go through different versions and the papers that described their original implementation may not be up to date
  2. Comparing Use Cases across the Ontologies
    - We examined five ontologies and their ability to represent the core concepts necessary for enabling energy audits, automated fault detection and diagnostics, and optimal control of HVAC systems.
    - Testing Ontologies vs. Core Concepts
      - Upper ontologies do not contain concepts specific to a domain, and they should be evaluated in terms of how well their structure describes the concepts and properties required by the domain and how easily a user can possibly extend the ontology for specific use cases.
      - Application ontologies should be evaluated like upper ontologies as well as in terms of how many of the domain-specific concepts and properties they capture. Where application ontologies are incomplete, an evaluation should again consider how easily the required concepts or properties can be expressed in terms of the provided ontological structure
    - Challenges and Gaps Applying the Ontologies to Our Use Cases
      - Even among just these five ontologies, the perspective and starting point for modeling and presenting building information can vary, from orientations around the topologies of buildings and their sub-components (BOT) such as sensors (SSN/SOSA) or devices (SAREF) and assets (Brick Schema).
      - We find that building modelers would generally be unable to represent key aspects of Zones and Spaces, in particular the geometry of these spaces. This is an area where an individual could develop their own extension, or pull in an external schema, but doing so would not necessarily lead to interoperability when using varied tools with different systems across use cases.
      - Building Envelopes are also consistently not fully represented across these schemas, with many key properties left out of the scope of the ontology designs.
      - A major limitation around Control Devices is the inability to represent aspects of control strategies, such as building schedules.
      - Upper ontologies (BOT, SSN/SOSA, the core of SAREF and SAREF4SYST) are generalpurpose ontologies that result in gaps that a modeler would need to fill in with extensions or external schemas.
        - BOT does not include representations of properties or units of measurement that affect multiple concepts related to systems, equipment, and devices, like sensors or actuators, making it difficult to capture the characteristics of a building’s envelope necessary for energy auditing
        - In contrast to BOT, SSN/SOSA ontologies are designed to model sensor networks and systems. Gaps emerge here where a modeler cannot natively represent locations and concepts like Zones and Spaces or many aspects of a building’s Envelope, such as properties of these components. Modeling Control Device schedules is also not within the scope of the ontology.
      - The application ontologies (Brick, RealEstateCore, SAREF4BLDG), in contrast, have gaps but provide many relevant domain-specific features that would benefit modelers with less experience or interest in taming complexity themselves.
        - SAREF and its many extensions cover a wide swath of our core concepts and yet still do not include ways to represent geometry and functions of spaces, aspects of building envelopes key to useful energy applications, or schedules and control strategies for control devices.
        - RealEstateCore similarly does not natively support modeling concepts and properties around zones, even though the ontology’s Virtual Building Component can represent such entities generally.
        - Brick at this point also does not include a mechanism to represent quantifiable static properties like room area or the rated power draw of motors.
  3. Answers to the Research Questions
    - Combining schemas in a rigorous way is generally challenging, with minimal guidance provided by developers, such as formal alignment between ontologies. Maintaining a model of a building that uses multiple schemas is likely to be challenging, given that each evolves at different rates.
    - Customizations required to add these concepts are possible, but they are labor intensive, tend to cause interoperability issues between applications, and reduce scalability.
    - We also found several overlapping concepts between ontologies that will need to be harmonized in the future to promote semantic interoperability in building applications
  4. Limitations of the Review
    - this review only considers schemas with published documentation, ignoring many models developed internally from companies and not shared publicly. Further, considering the fast pace at which new schemas and ontologies are introduced, especially in the IoT domain, this review has to be considered as just a snapshot in time
    - While the three use cases selected are often cited in the literature and are central to recent standardization efforts, they only represent a fraction of the possible applications and they only describe building operations.
    - It also became evident that a quantitative comparison between upper and domain ontologies was difficult to make as well as unfair, due to the different purposes underlying their design.
    - upper ontologies provide a different level of abstraction and do not directly contain domain concepts such as an AHU or a thermostat, but they may provide the constructs and relationships to describe them indirectly.
  5. Future Work
    - Create and maintain a public repository of schemas and ontologies for building energy applications. A centralized database and search engine will reduce the effort required to search and identify existing schemas, and hopefully promote the reuse of concepts, as demonstrated in other disciplines
    - Develop and share additional use cases. We faced the challenge of identifying useful but tractable use cases to use in our review. Future endeavors should work to produce public use cases and reference models (both conceptual and instantiated using particular ontologies) that clearly examine and weigh trade-offs modelers face building these key resources.
    - Work with multiple stakeholders to harmonize and standardize schemas. Academia, industry, and other interested stakeholders (e.g., policymakers) should collaborate within a standard organization (e.g., ASHRAE) to create a standard schema addressing semantic interoperability for building applications.
