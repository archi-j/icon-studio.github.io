---
layout: post
title: "[Paper Reading] From obXML to the OP Ontology: Developing a Semantic Model for Occupancy Proﬁle"
date: 2022-10-27 09:00:00 +0300
description: "2020_From obXML to the OP Ontology: Developing a Semantic Model for Occupancy Proﬁle" # Add post description (optional)
img: 20221027_post_main.JPG # Add image post (optional) 280px, 350px, 470px, 700px, 940px
fig-caption: # Add figcaption (optional)
category: [PR]
tags: [Occupancy Profile, Ontology, Semantic Web]
---

**Publication year:** 2020 <br>
**Authors:** Serge Chavez-Feria, Giorgos Giannakis, Raul Garcıa-Castro, and Marıa Poveda-Villalon<br>

## Introduction
- However, the accuracy of a 3D zonal-type simulation is highly affected by the level of detail of its input data.
- Static data include the building geometry, construction materials, glazing information, systems used in the building, etc., while dynamic data consist of all time-dependent data such as user-actions (e.g. opening and closing the windows), occupancy schedules in each of the building zones, use of equipment, weather predictions, etc., commonly being in-building sensed measurements.
- Despite its stochastic nature, in common practice OB is oversimplified and introduced to the 3D zonal-type simulation engines as either deterministic or predefined rule-based schedules, ignoring that way the OB diversity
- In the context of the H2020 European project BIMERR, the consortium leverages the outcomes of the Annex 66,4 adapting the obXML data model to an OWL ontology representation.

## BIMERR Project context
- The BIMERR project aims to design and implement a set of Building Information Modelling tools to facilitate the development of building renovations projects.
- Due to this high diversity of tools, the core of the system need an interoperability layer that support the flow of information between the applications.
- In this context, one of the key modules in the network is the OP ontology, which is utilized to define residents profiles and their interactions with building system.

## Methodological background
- This methodology focuses on: a) the reuse of already published vocabularies or ontologies and b) the online publication of the built ontology in several formats according to the Linked Data principles.
- The LOT methodology defines iterations over a basic workflow composed of the following activities: 1) ontological requirements specification; 2) ontology implementation; 3) ontology publication; and 4) ontology maintenance.
- The goal of the ontology requirements specification activity is to collect the requirements that the ontology should fulfill
- Taking as input the ORSD (Ontology Requirement Specification Document), the main goal of the ontology implementation activity is to build the ontology using a formal implementation language
- The ontology encoding activity refers to the translation of the conceptualization into one or more ontologies formalized in OWL.
- Ontology reuse refers to the process of using available ontologies for solving different problems
- Evaluation. This activity refers to checking the technical quality of an ontology against a frame of reference
- The goal of the ontology publication activity is to make the ontology available on-line both as human-readable documentation and in one or more machine-readable formats
- Finally, the goal of the ontology maintenance activity is to update the ontology after the last release.

## Occupancy profile ontology development
- Requirements Specification for the OP Ontology
  - The goal of the OP ontology is to provide an ontological representation of the occupant behaviour domain.
  - From the obXML and associated documentation, we created three tables with a set of initial functional requirements. The first table handles the main concepts of the domain, the second table the relationships identified between concepts, and the last table the attributes that describe certain aspect of the concepts by means of literals.
- Implementation of the OP Ontology
  - Even though obXML gives the main resources to model the domain, the constructs available in an XML schema are not directly mapped to OWL constructs, therefore some modelling decisions should be made by ontology engineers to transform obXML into an ontology compliant to the OWL semantics (while keeping a OWL-DL complexity).
  - The first decision about ontology engineering was related to the ontology reuse activity. In this case, as no ontology covering the OP domain was known nor found in ontology registries such as LOV,6 the decision made was to develop a first ontology conceptualization based on obXML and then to look for subsets of it that could be covered by or aligned to standard or well-known ontologies.
  - In the conceptualization we reuse the classes created for the Building ontology, which at the same time reuse and are aligned with some well know ontologies in the LBD community such as BOT, or SAREF4BLDG.
  - obXML describes an occupant as a particular person instead of a general profile. It means, an instance of op:Occupant has a particular name and age.
  - A behavior can lead to an action over a system or a passive acceptance of the uncomfortable conditions. This is modeled by the link op:leadsTo that connects to union of individuals of the classes op:Action and op:Inaction (OMD6).
  - A space may contain several systems that occupants can interact with to adjust their comfort requirements. The obXML schema provides an initial list of systems. Instead of creating a new class to allocate such list, we reuse concepts available in SAREF and SAREF4BLDG (OMD3)
  - One important aspect in occupant behavior is the stochasticity involved in human-system interaction. The way to model this interaction occurrence probability is through mathematical formulas, represented in the model by op:InteractionFormula.
  The model should allow to express if the occupant internal needs are influencing in a certain way its behavior. The property op:influencedByNeed connects a behavior to individuals of op:Need.
  - occupant movements (op:Movement) can have an impact over building energy performance. In obXML, the movement models are specified by space occupancy specifications and event specifications, gathered in the initial conceptualization under the class op:MovementSpecification (OMD9).
  - A behavior could also be triggered by external factors, like the day of the week, environmental properties or the room itself, which are modelled by the concept op:Driver.
- Publication and Maintenance of the OP Ontology
  - For the ontology publication, we followed W3C best practices, setting up content negotiation mechanisms for the OP ontology URI https: // bimerr. iot. linkeddata. es/ def/ occupancy-profile.

## Related work
- up to the authors’ knowledge, no OWL ontology that represents this model is available. For this reason, in this paper the obXML schema has been taken as the main non-ontological input to generate the OP ontology in a format compatible with linked data and semantic web technologies.

## Conclusions and future steps
- This paper has presented the process of developing a semantic model, implemented as an OWL ontology, based on the obXML standard. The ontology is available online together with human-readable documentation and an example of use.
- This work presents a catalogue of 10 well-argued decisions that could serve for other ontology developments.
- Future works
  - Authors will also explore the construction of mapping rules in order to transform obXML data into RDF statements automatically.
  - the connection of the OP ontology with other domains from the BIMERR network needs to be evaluated in order to address overlaps, and to determine how this complementary data (sensor data, building data, etc) can enrich the description and help in the understanding of occupancy profile information.
