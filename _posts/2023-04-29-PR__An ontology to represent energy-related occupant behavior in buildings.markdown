---
layout: post
title: "[Paper Reading] An ontology to represent energy-related occupant behavior in buildings. Part II: Implementation of the DNAS framework using an XML schema"
date: 2023-04-29 09:00:00 +0300
description: "2015_An ontology to represent energy-related occupant behavior in buildings. Part II: Implementation of the DNAS framework using an XML schema" # Add post description (optional)
img: 20230429_post_main.jpg # Add image post (optional) 280px, 350px, 470px, 700px, 940px
fig-caption: # Add figcaption (optional)
category: [PR]
tags: [Occupant Behavior, Building Energy, Ontology]
---

**Publication year:** 2015 <br>
**Authors:** Tianzhen Hong, Simona D'Oca, Sarah C. Taylor-Lange, William J.N. Turner, Yixing Chen, Stefano P. Corgnati<br>

## Introduction
- Based on a comprehensive review of 130 published academic papers, Part I of this paper introduced the DNAS (Drivers, Needs, Actions, Systems) framework intended to formalize the modeling of energy-related occupant behavior (OB) in buildings
- Building occupants are not passive receptors to their indoor environment. Instead, occupants interact with building systems to bring about desired thermal, visual, and acoustic comfort and good indoor air quality (IAQ).
- As stated by Parson, occupants acclimatize to their environment through three main adaptive responses: physiological, psychological and behavioral.
  - A physiological response is any type of unconscious reaction which allows the human body to adapt thermally to the indoor environment.
  - A psychological response involves the cognitive and cultural variables of each individual with respect to their perception of the indoor environment
  - A behavioral response is any type of action performed to maintain or restore a state of comfort when the indoor environmental conditions cause discomfort.
- In everyday practice, and often without fully considering the consequences, occupants interact with the building systems in their homes and workplaces in order to achieve desired environmental conditions. In this context, this paper focuses on behavioral comfort-driven responses of occupants within the built environment.
- Commonly, OB models used in building simulation are formed under the assumption that occupants behave in a set way according to standard deterministic design conditions such as occupancy levels, ventilation rates, thermostat set points and other threshold values.The inclusion of the adaptive comfort model into European (EN 15251) and U.S. standards (ASHRAE 55) has promoted interest in:
  1. The prediction of OB actions performed by individuals to restore their personal comfort
  2. The quantification of the energy impact of OB to understand the factors driving the difference between predicted and actual building energy use.
- Over the past 30 years, building-occupant interaction models have been developed to describe human behavior in a need-action-event cognitive process and have been the focus of investigation for a substantial body of scientific research. Recent efforts have been made within the framework of the International Energy Agency (IEA) Energy in Buildings and Communities Programme (EBC) Annex 53 to categorize the most relevant types of energy-related OB for residential buildings. A dedicated section of Annex 53 focuses on OB modeling, exploring existing theories on OB and behavioral models, and providing a comprehensive literature review of the influencing parameters (referred to as ‘driving forces’) for the various types of energy-related OB.
- From these examples, the selection of different drivers for similar occupant behavior models makes it difficult to compare the models and incorporate them into building energy modeling (BEM) programs. In order to bridge this classification gap, an ontology was developed to describe the main behavioral adaptation mechanisms.
- The obXML schema allows relationships to be formed/defined between different drivers and the eventual action, in a standardized way. obXML is designed to provide enough flexibility for both existing and future occupant behavior, building energy and system models to be captured in a consistent way.

### XML - eXtensible Markup Language
- JSON documents are widely used for targeting web browser display applications using Java and JavaScript code.
- An XML document is a machine- and human-readable document used to provide a convenient and simple way of storing and transferring data between applications and software tools. An XML schema provides a platform to facilitate and standardize the sharing, storage and management of data, especially when data is collected from heterogeneous sources.
  - The Green Building XML schema (or gbXML), was developed to facilitate the transfer of building information stored in CAD building information models, enabling integrated interoperability between building design models and a wide variety of engineering analysis tools and models.
  - The ifcXML schema, developed by buildingSMART, is derived from the Industry Foundation Classes (IFC) EXPRESS model. ifcXML is a neutral, open, and object-based data format intended to facilitate interoperability in the architecture, engineering and construction industries.

### Occupant behavior modeling
- The XML language was chosen because of its ability to provide an automated mechanism which can capture the data syntax and structure needed to represent the DNAS framework in the form of an interoperable language for energy-related OB in buildings.
- The obXML schema is intended to be integrated into current building energy modeling (BEM) programs or Functional Mock-up Units (FMUs), to support both model exchange and co-simulation of OB models.
- When used in wholebuilding energy simulation obXML will help to eliminate model and data ambiguity and narrow the gap between the simulated and actual energy consumption of buildings. The implementation of the obXML schema into an FMU (which enable co-simulation environments) via a Functional Mockup Interface (FMI) such as Modelica, will allow simultaneous simulations with current BEM programs to be performed.
- FMI is a tool-independent interface standard intended to support both model exchange and cosimulation of two or more dynamic models.
- A simulation model or program which implements the FMI standard is called an FMU. An FMU comes along with a small set of easy-to-use C-functions (FMIfunctions) whose input and return arguments are defined by the FMI standard.
- The integration of human behavior simulation with BIM is one way to bridge the gap between predicted and actual building energy consumption. However, there has been little effort exerted to establish such integration. BIM could provide a core for building OB models, supporting a new generation of Occupant Information Modeling (OIM) that will enable the simulation of tailored scenarios of occupant operation and management for specific building cases.

## Implementing the DNAS framework into a schema

### Categorizing occupant behaviors using the DNAS framework
- The topology of the schema follows the DNAS framework, with each adaptation mechanism described using the four key components:
  - Drivers represent the environmental factors that stimulate occupants to fulfill a physical, physiological or psychological need.
  - Needs represent the physical and non-physical requirements of the occupant that must be met in order to ensure satisfaction with their environment.
  - Actions are the interactions with systems or activities that occupants can perform to achieve environmental comfort.
  - Systems refer to the equipment or mechanisms within the building with which occupants may interact to restore or maintain environmental comfort.

## Discussion
- Current simulation-based evaluations of building energy performance oversimplify assumptions on occupant behavior creating inconsistencies between simulated and actual building energy performance.
- The main aim of the obXML schema is to facilitate the development of new methodologies to enable robust and standardized occupant behavior descriptions which can better capture real-life complexity and uncertainty during simulation.
- The obXML schema allows the creation of obXML instance files which contain a representation of occupant behaviors in buildings following the DNAS framework ontology. The obXML schema facilitates the development of a quantitative description of human interactions with building systems.
- One challenge with the development of the schema is establishing the order of events, considering multiple occupants and multiple actions. To account for this, each behavior within a group of behaviors is defined by a unique ID and priority indicator.
- The question becomes which action is performed first and how is this sequence of events captured by obXML? In the current version of the schema (version 1.0) a priority ranking may be applied manually to each behavior.
- Future work will address the algorithms needed for this priority ranking system with improvements to include constraints associated with (1) group versus individual behavior, (2) the occurrence of simultaneous multiple-actions, (3) the sequence of occupant actions and, (4) better accountability for culturally-motivated actions.
- The behavior software module can be used in three different ways:
  1. to pre-calculate schedules or settings which are used as inputs for occupancy or actions without feedback
  2. to direct code integration via function calls to dynamic link libraries (DLLs)
  3. to facilitate co-simulation with current BEM programs via FMIs.
- The advantages of this approach against the direct implementation or coupling of advanced OB models in/with building simulation programs are that it (1) utilizes the capabilities of domain-specific simulation and provides the flexibility to be integrated with an array of building modeling programs, extending beyond EnergyPlus, (2) allows users the option to select preferred simulation programs and directly enhances the occupant modeling component of the select simulation program and, (3) enables standardize representation of occupant behavior models for flexibility, future expansion and interoperability.

## Conclusion
- The DNAS framework described in Part I was implemented into the form of an XML schema called obXML. The notable contributions of the development of the obXML version 1.0 include the following:
  1. The obXML schema provides a standardized structure to describe occupant behavior which can be used by researchers and industry stakeholders to standardize the language of occupant behavior studies.
  2. The obXML schema provides a platform to describe occupant behavior in buildings and assess the impact of occupant behavior on building energy modeling in more detail than present methods allow.
  3. The design of the obXML schema allows for flexibility and extensibility with easy adaptability, so that it can be modified to include additional elements or attributes if so desired.
  4. The obXML schema is intended to be integrated into current BEM programs or Functional Mock-up Units to support both model exchange and co-simulation of dynamic models.
