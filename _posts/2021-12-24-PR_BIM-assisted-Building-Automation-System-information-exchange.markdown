---
layout: post
title: "[Paper Reading] BIM assisted Building Automation System information exchange using BACnet and IFC"
date: 2021-12-28 09:00:00 +0300
description: 2021_BIM assisted Building Automation System information exchange using BACnet and IFC # Add post description (optional)
img: 20211228_post_main.jpg # Add image post (optional) 280px, 350px, 470px, 700px, 940px
fig-caption: # Add figcaption (optional)
category: [PR]
tags: [BIM, IFC, Reading]
---

**Publication year:** 2021 <br>
**Authors:** Shu Tang, Dennis R. Shelden, Charles M. Eastman, Pardis Pishdad-Bozorgi, Xinghua Gao <br>
**DOI:** [https://doi.org/10.1016/j.autcon.2019.103049](https://doi.org/10.1016/j.autcon.2019.103049)

## Introduction
- Smart buildings are the trend of the next generation's commercial buildings, which link different building systems together with Building Automation System (BAS). It allows the smart buildings to collect, analyze data, and control facility functions and services.
- Common functionalities of BAS are temperature and air quality monitoring, lighting system control, fire control and sending signals when faults occur. It relies on sensors to collect the condition or status of control parameters and actuators to conduct physical actions.
- Data communication protocols play key roles in information exchange in the BAS domain; however, it is rarely seen to design BAS or exchange BAS information
- Unlike other building systems, BAS seldom participates in the design-build BIM cycle but blends into facility management (FM) in the later stage.
- Normally, BAS is the last system to be built in the construction phase, it may suffer from error and corrections made during the setup of other systems. The information sharing between BAS designers, all sub-contractors, and building's general contractors without BIM may be inefficient
- BAS is designed based on communication protocol like BACnet, while BIM information can be represented using open standards like IFC. With the object-oriented modeling characteristic of the BAS protocols and open BIM standards, it is possible to design and modify BAS usign BIM tools without specifying device vendors during the design phases.
- This research aims to set a fundamental step to facilitate information exchange for BIM assisted BAS design and operation using one of the BAS open communication protocol named BACnet and BIM open standard, known as IFC.
- This research leveraged the Information Delivery Manual (IDM) and the Model View Definition (MVD) methodologies to define an IFC subset schema (a BACnet MVD) so that BAS information conforming to the BACnet protocol can be represented in IFC data model for information exchange throughout various project stages

<img src="https://ars.els-cdn.com/content/image/1-s2.0-S0926580519301645-gr1_lrg.jpg" class="post_img" style="width:60%;" alt="BACnet device, object, and properties">

## Background
- BACnet overview
  - ASHRAE has developed BAC net protocol to address the communication needs of BAS for different applications like heating, lighting control, and fire detection systems.
  - BACnet aims to solve interoperability issues among different devices vendors by modeling exchanged information with object-oriented representations
  - Currently, 60 Object Types defined in ANSI/ASHRAE Standard 135-2016 are modeled as a collection of BACnet Objects.
  - BACnet Objects hold information, which relates to a device as sets of properties which has an identifier, a data type and a conformance code indicating whether this property is required or optional
  - One potential application benefitting O&M is accessing BAS information through the extended BACnet Web Service (BACnet/WS) and integrating it with BIM online. The BACnet/WS is capable of using technologies like REST, JSON and OAuth2 within BACnet and integrating with the BIM models
  - Another potential application benefiting O&M would be to exchange information which resides in the BAS model with FM tools like Metasys and Niagara which directly connect to sensors and controllers as the control system using the MVD created in this paper.
- IFC/MVD/IDM overview
  - The most commonly used data exchange format for open BIM is IFC that has been accepted as ISO 16739 standard. The IFC enables data exchange between different software applications across the entire building lifecycle.
  - BIM models can be enormous if the information is fully integrated. A fully populated model is unnecessary for all stakeholders or a certain software at a project stage. To solve this issue, buildingSMART International created IDM and MVD approaches to define subsets of IFC   schema for certain Exchange Requirements (ER)
  - An IDM firstly captures business processes and ERs at the user level. Then, the MVD defines a subset of IFC schema based on ERs identified by the IDM. In this way, models can be filtered and size-reduced according to an MVD to satisfy specific business processes.
  - BuildingSMART has released official MVDs among which COBie (Construction Operation Building Information Exchange) is used to exchange specifications for life-cycle capture and delivery of information needed by facility managers
  - COBie does not emphasize on exchange BAS information that follows the BACnet protocol. Some practitioners suggested that COBie contains universal facility management parameters and fails to selectively filter most relevant data for bespoke operation and maintenance requirements.

## Research Method & Result
  - This paper leveraged IDM/MVD methodologies to define an IFC subset schema (a BACnet MVD), so that BAS information complying with the BACnet protocol can be represented in the IFC data model for information exchange between BIM tools and FM tools throughout various project stages.

<img src="https://ars.els-cdn.com/content/image/1-s2.0-S0926580519301645-gr2_lrg.jpg" class="post_img" style="width:70%;" alt="Overall process of methodology">

  - Firstly, the IDM method defined the information sharing process and a set of information to be exchanged at the user level for BAS design and operation.
    - The IDM contained process model, ER and Functional Parts (FPs).
    - The process model identified the purpose and a set of data for exchange.
    - As the BACnet protocol was defined by BAS domain experts, information which needs to be exchanged (ERs) was directly extracted from the BACnet protocol. These ERs defined a group of information units to exchange based on the process model and ANSI/ASHRAE Standard 135–2016.
    - The information units were further breakdown into FPs which described the information in terms of the required capabilities of IFC standard.
  - The second part involved developing an MVD using the IfcDoc tool.
    - The MVD enabled IDM outputs to translate into IFC entities, attributes, and properties to facilitate interoperability at the software level. The functions of IDM outputs including
process model, ERs, FPs were represented by MVD concepts.
    - A mapping spreadsheet was created to clarify the relationships between each information unit, FP and MVD concept.
  - The last part demonstrated a prototype test of the BACnet MVD using Autodesk Revit and Web browser as importing and exporting tools for BAS information exchange.
    - BACnet Object Types and property identifiers expressed in IfcXML were imported into a Web browser to demonstrate the possibility to exchange BAS information using IFC data model.
- IDM
  - The aim of IDM is to collect domain knowledge and information needed regarding workflows from experts. It specifies process model, ERs and FPs at user level
  - With modern documentation tools like IfcDoc, creating an MVD does not necessarily require an IDM. However, the conventional templates are userful to streamline the IDM/MVD process and demonstrate various terminologies
  - Process model
    - It is the initial step to identify the purpose and a specified set of data for exchanged
    - The formalization of the process model describes the activities, related information, logical sequence of activities and roles involved for a particular goal.
    - The process model was created to illustrate the process of BAS design and operation information exchange across project stages.
    - The codes and the phases of this process are based on Omni Class Construction Classification System
  - Information exchange requirements
    - Information or data flow between two or more parties is documented by ERs. An ERs connects business process with relevant information defined within a particular information model.
    - The identification of ERs started with an in-depth analysis ANSI/ASHRAE Standard 135-2016 by understanding the BACnet protocol architecture, modeling control device as a collection of objects, object types, modeling control device as a collection of objects, obejct types, property identifiers, and property datatypes
    - The relationships and similarities between BACnet object types/property identifiers/property datatypes and IFC entities/attributes/datatypes were discovered during this analyzing process.
    - The implementation starts with an official ER template that consists of a header & overview section and information requirements section.
    - The key to identify ERs is the list of information units in the information requirement section. The information requirement section describes a set of information units to satisfy user requirements.
    - One of the potential usages of the BACnet MVD is to assist design BAS systems using BIM authorizing tools, the BACnet objects can be modeled as virtual instances in BIM tools. The geometric representation, location, space relationships and connectivity between these virtual instances are also important information for BAS design.
  - Functional parts
    - Information units can be broken down into FPs. Each FP describes the information in terms of the required capabilities of the IFC standard to provide technical support for information units.
    - An FP is a reusable information model in its own right as well as being a subset of information model on which it is based on IFC
    - Each information unit is mapped to an FP, which can be expressed as: i) IFC entity; ii) attribute of IFC entity with specified data type; iii) property in a property set with specified data type; iv) referring to another FP.

<img src="https://ars.els-cdn.com/content/image/1-s2.0-S0926580519301645-gr3_lrg.jpg" class="post_img" style="width:70%;" alt="Process map for BIM-based BAS design and operation information exchange">
<img src="https://ars.els-cdn.com/content/image/1-s2.0-S0926580519301645-gr4_lrg.jpg" class="post_img" style="width:80%;" alt="Example of information unit, functional part and concept mapping">

- MVD
  - MVDs have been defined as subsets of IFC model specification to support IFC implementation. The IFC implementation should satisfy requirements coming from end-users as defined in IDM
  - MVDs enable IDM outputs, including process map, ERs, and FPs to translate into IFC schema and to facilitate interoperability at the software level. An MVD consists of Model Views, Exchange Definition, Concept Root, Concepts, Concept templates, and Property Sets.
  - BuildingSMART developed an official tool IfcDoc to assist in generating MVDs. IfcDoc improves consistency and computer-interpretability of the MVDs' definition. IfcDoc assists in generating diagrams, defining schemas, and specifying the scope and contents of custom-made specifications
  - Model view and exchange Definition
    - Model View defines the scope of MVD by specifying Exchange Definition, entity usage, concepts usage and importing/exporting requirements.
    - Model View groups a set of IFC entities (entity usage) and Concepts (concept usage) to satisfy exchange scenarios.
    - There are several existing official MVDs defined by buildingSMART, for example, IFC4 Reference View, IFC4 Design Transfer View and IFC2x3 Coordination View
  - Concept root, concept, concept usage, concept template
    - Concepts are the technical solutions to exchange a commonly useful package of information identified in ERs. Concepts can be applied to IFC entities as Concept usage including attribute usage, property usage, quantity usage, and mapping usage.
    - Concept Roots collect available Concepts in a hierarchical tree structure. Concept Roots divide Concepts by their context and objectives such as project content, object definition, and object attributes.
  - Documentation
    - An automatic documentation process enables additional descriptions and constraints to be encoded into MVD using HyperText Markup Language (HTML). IfcDoc generated an HTML documentation containing entity usage, concepts usage, and properties for BAS design and operation information exchange (Fig. 8). This documentation acts as an indication of information that is necessary to import/export between different BIM tools and FM tools.

<img src="https://ars.els-cdn.com/content/image/1-s2.0-S0926580519301645-gr5_lrg.jpg" class="post_img" style="width:70%;" alt="BACnet view exchange requirement view">
<img src="https://ars.els-cdn.com/content/image/1-s2.0-S0926580519301645-gr6_lrg.jpg" class="post_img" style="width:60%;" alt="Concept template and instance diagram">
<img src="https://ars.els-cdn.com/content/image/1-s2.0-S0926580519301645-gr8_lrg.jpg" class="post_img" style="width:80%;" alt="The BACnet MVD documentation in HTML">

- Implementation of the prototype Test
  - A prototype test following the BACnet MVD was carried out with both the exporting tool and importing tool.
<img src="https://ars.els-cdn.com/content/image/1-s2.0-S0926580519301645-gr10_lrg.jpg" class="post_img" style="width:80%;" alt="Sample testing scenario">
<img src="https://ars.els-cdn.com/content/image/1-s2.0-S0926580519301645-gr11_lrg.jpg" class="post_img" style="width:90%;" alt="Sample exported IFC instance file">
<img src="https://ars.els-cdn.com/content/image/1-s2.0-S0926580519301645-gr9_lrg.jpg" class="post_img" style="width:90%;" alt=" The BACnet MVD implementation steps">

## Results and Discussion
- The result of this study showed that IFC is suitable for representing BAS metadata, whether representing BAS control, communication, constraints, and other data sources like real-time data using the IFC data model is appropriate or not remains to be a concern.
- IDM
  - A process model (Fig. 3) was created to capture the BAS information exchange from the design phase to operation phase. This process model together with the BACnet protocol was explored to identify ERs.
  - Altogether, the authors identified 395 information units including 25 BACnet Object Types and 370 property identifiers
- MVD
  - A BACnet View was created using IfcDoc to document all collected information in the IDM process.
  - Twenty-five BACnet Object Types indicated 12 entity usages in the BACnet View.
- Implementation of prototype Test
  - BACnet object types were modeled as Revit families. Several Revit families include BACnet Device, Analog Input Object, and Analog Output Object were constructed with user-defined attributes and share parameters indicating exporting settings as a test scenario.
  - The prototype test has successfully exported IFC entities, predefined types and other attributes following the BACnet MVD.
- Limitations
  - Data mapping
    - Although this study has mapped 25 BACnet Object Types and 370 property identifiers to IFC entities, attributes, and properties, only part of the BACnet Object Types and required property identifiers were involved to demonstrate the possibility of representing BACnet data in IFC data model.
  - Implementation of prototype Test
    - i) the prototype test was based on limited test scenarios and BACnet Object Types.
    - ii) export settings in Revit contains official buildingSMART MVD like IFC4 Design Transfer View, IFC 2 × 3 Coordination View, and IFC4. Since the BACnet view was newly proposed, the exporting
process required manual set up for each object.
    - iii) to check whether the exported IFC instance file contains necessary BACnet data, the data validation process was done manually.
    - vi) most of the current BIM tools including Revit have the limitation in creating object connectivity so that BACnet objects/devices decomposition and composition cannot be explicitly indicated
  - Tool Limitation
    - Design BAS using Revit required custom-made families and the manual connection between objects. This process is time-consuming and may not satisfy industry needs.
  - Other data source
    - BAS information exchange is more complex than just metadata. Time-series data, which record continuous readings from BAS sensors and meters, is another important source of data.
    - As this study shows, the IFC data model is suitable to represent BAS metadata. However, representing real-time data in IFC data model may not be an appropriate approach.

## Conclusion
  - Summary
    - This research demonstrates the possibility to exchange BAS information conforming to the BACnet protocol with the IFC data model for BAS design and operation.
    - This study has successfully leveraged IDM/MVD methodologies to define a subset of IFC schema, which represents BACnet Object Types and property identifiers. The IDM method was utilized to identify the BAS information sharing process and ERs at the user level.
    - A prototype test was carried out with a BIM tool and web browser to demonstrate the implementation of BACnet MVD for BAS information exchange between BIM tools and FM tools.
  - Contribution
    - The significance of designing BAS using BIM tools is addressed, brining insights for the potential of using BIM tools for BAS information exchange
    - This study made detail IFC representation of BACnet protocol including BACnet objectsand associated property identifiers using IFC entities, properties, and relationships.
    - The BACnet MVD created allows BAS information to be represented in IFC data models which enable information sharing among various BIM tools and project stages.
    - The prototype test demonstrates the possibility to design BAS using BIM tools by selecting BACnet objects with BACnet property identifiers, and exchange BAS information using the IFC data model.
    - The prototype test sets a foundation for software vendors to develop automatic data importing and exporting in BIM tools for BAS information exchange. It also can be the starting point of the software certification process and the data validation process.
    - Limitation for data mapping, tool implementation, and process of prototype test was identified to shed light on future work to bring the BAS design and operation into the BIM cycle.
  - Future works
    - extending IFC data model and integration with other data models to represent BACnet services and constraints.
    - In terms of prototype test implementation, complex real projects or more test scenarios should be tested.
    - An automatic data validation process for exporting BIM-based BAS data based on BACnet protocol should be explored.
    - to create BIM-based BAS design tools or a plug-in for both importing and exporting requirements following the BACnet MVD.
    - An API or plugin in BIM tools that allows automatic data mapping when exporting and importing BAS information following the BACnet MVD is necessary to guarantee a reliable data validation process
    - Further collaboration with current BIM-based design and FM tools vendors may be the next step to enable the seamless exchange of BAS information using IFC data model between BIM tools and FM tools.
    - different data sources such as real-time data, data generated during various project stages and data produced from interaction with other disciplines need the most suitable data models for representation.
    - Integration between building contextual data, BAS information and the Internet of Things using extended BACnet/WS and other open-source data models like Project Haystack deserve future investigation
    
