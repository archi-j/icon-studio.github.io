---
layout: post
title: "[Paper Reading] Brick : Metadata schema for portable smart building applications"
date: 2023-04-11 09:00:00 +0300
description: "2018_Brick : Metadata schema for portable smart building applications" # Add post description (optional)
img: 20230411_post_main.jpg # Add image post (optional) 280px, 350px, 470px, 700px, 940px
fig-caption: # Add figcaption (optional)
category: [PR]
tags: [Metadata schema, Building Energy, Brick]
---

**Publication year:** 2018 <br>
**Authors:** Bharathan Balaji, Arka Bhattacharya, Gabriel Fierro, Jingkun Gao, Joshua Gluck, Dezhi Hong, Aslak Johansen, Jason Koh, Joern Ploennigs, Yuvraj Agarwal, Mario Bergés, David Culler, Rajesh K. Gupta, Mikkel Baun Kjærgaard, Mani Srivastava, Kamin Whitehouse<br>

## Introduction
- Buildings account for 32% of the energy and 51% of the electricity demand worldwide as of 2010. Improving the energy efficiency of buildings can reduce energy demand by up to 90%, will help reduce operational cost, curb carbon emissions, improve indoor air quality, and keep occupants healthy and productive.
- Technological innovations in what is now called the “Internet of Things” (IoT) have led to connected lights, power meters, occupancy sensors and electrical appliances that are capable of interfacing with the underlying SCADA (supervisory control and data acquisition) systems used in building automation.
- As of 2012, 14% of the commercial buildings in the U.S. had deployed Building Management Systems (BMS) to manage data collection and remote actuation of the connected building infrastructure. Newer buildings are equipped with BMS by design, and many older buildings are being retrofitted with networked systems for improved efficiency.
- Deploying energy applications in buildings requires significant manual effort and building specific domain expertise. Even the most modern BMS present a cacophony of data and information flows that vary across buildings, vendors and locations. Unlike the mobile phone landscape, there is no standardized operating system or hardware abstraction layer for building applications.
- NIST in 2004 estimated that the U.S. building industry lost $15.8 billion annually due to lack of interoperability standards. Attempts have been made to address this problem. Building Information Models (BIM) were introduced to address the interoperability concerns both for the design and operation of buildings. Schemata such as the Industry Foundation Classes (IFC), and more recently the Green Building XML (gbXML), are useful but they remain largely oriented towards design and construction efforts.
- Designing a comprehensive schema for the emerging IoT universe in order to run any conceivable application in any context is a difficult task but unnecessary for the current scope of creating a usable platform spanning commercial buildings.
- In designing Brick, we ask the following important questions and seek answers with demonstrated effectiveness:
  - Completeness: Can Brick represent all the metadata information (such as a sensor’s location, type, etc.) contained in a building’s BMS?
  - Expressiveness: Can Brick capture all important relationships between building entities that are (a) explicitly or implicitly mentioned in a building’s BMS, and (b) expressed in canonical energy applications in published academic literature?
  - Usability: Can Brick represent the information in a way that is easy to use for both the domain expert and the application developer unambiguously? Can the schema support automation with machine readable data formats and querying tools? Can it be extended for new concepts in a unified way?
- The information in a BMS is characterized by data points that correspond to values reported by sensors, configuration parameters such as a temperature setpoint and status of equipment. Brick design is based on more than 17,700 data points supplied by BMS from six different vendors, and have vastly varying subsystems and sensors.


## Background
### Building applications and energy efficiency
- By taking advantage of the proliferation of sensing and control devices in buildings, many approaches have been developed to reduce this waste, ranging from naïve occupancy-driven control and AFDD to model-predictive control. Because these approaches are, for the most part, algorithms and heuristics that can be implemented in software, we refer to them as building applications.
- The largest barrier for the adoption of energy efficient applications is cost. As of 2012, 86% of the buildings in U.S. have no BMS that controls buildings in a centralized way. Adoption of a naïve BMS costs between 2.50 USD to 7.00 USD per square foot as of 2016, which sums up to a minimum of 250,000 USD for a 100,000 square feet building
### Metadata in buildings
- BMSes capture the building infrastructure information in terms of different subsystems such as lighting, electric power, water, and heating, ventilation and air conditioning (HVAC). BMSes describe the equipment in each domain, how they connect with each other, monitor their operation through networked sensors and actuate them through remote commands.
- Since BMS metadata information is neither standardized nor designed to be machine readable, “label” naming is heterogeneous and inconsistent across commercial vendors, between the buildings set up by the same vendor, and even within a building.
- Brick directly addresses this problem of building-specific labeling by compiling a normalized list of domain terms that we refer to as our vocabulary and devising canonical relationships that capture dependencies and connections in and between building subsystems. Brick describes a building in a machine readable format to enable programmatic exploration of different facets of a building.
### Current state of the art
#### Project Haystack
- Tags provide a flexible and scalable framework for annotating metadata to building data points. Haystack defines a vocabulary of tags describing building equipment, weather, units and data types. However, the current set of tags lacks or does not fully describe key aspects of buildings such as spatial elements, lighting equipment and electrical subsystems
- While deficiency of tags can be addressed by future updates, a subsequent challenge is that use of tags can be ambiguous and inhibit application portability.
- Haystack relationships lack the expressive power required of an effective building metadata schema. Haystack represents relationships using a ref tag, which is enough to associate two pieces of equipment, but cannot express the nature of that association.
- Haystack does not model “reverse” tags, which makes it difficult to enumerate sequences of equipment.
- Haystack Tagging Ontology (HTO) maps the Haystack tags to an ontology, with each tag corresponding to an ontology class. Thus, HTO is able to combine the flexibility of tags and the formal modeling of ontologies to define essential BMS metadata and the relationships between entities
- HTO confines the ontology to the defined tags, and does not model the building entities which are a collection of tags. HTO also does not provide a way to compose complex subsystems in a building and relies on Haystack tagging for mapping raw metadata to the ontology.
#### Industrial foundation classes
- IFC is a standardized Building Information Model (BIM) that developed from the need to have a common exchange model for 3D architectural drawings needed for a building’s construction.
- IFC lacks much of the vocabulary for describing the necessary subcomponents needed for building operation.
- the IFC standard does not include explicit mechanisms for describing the functional role of sensors, such as whether a temperature sensor measures supply, return or exhaust air. There is also no common way of adding new vocabularies compliant to existing ones.
#### Semantic web and ontologies
- Semantic Web is a framework promoting common data formats, exchange protocols and vocabularies with which machines can process contents’ meanings without human interruptions on the Web. Its relevant standards include RDF, SPARQL, and Turtle.
- These common concepts, however, do not effectively cover the diversity of devices and equipment in buildings because their goal was to capture generic sensor and smart devices rather than building operations where domain-specific information is required.
- Daniele et al. combined these ontology modeling efforts in collaboration with industry to create a simple but unified model called Smart Appliances REFerence (SAREF). These common concepts, however, do not effectively cover the diversity of devices and equipment in buildings because their goal was to capture generic sensor and smart devices rather than building operations where domain-specific information is required
- The BOnSAI smart building ontology describes the functionality of sensors, actuators and appliances as well as how they interact and effect their physical environment. However, they fail to capture the interactions and relationships between the sensors and other building assets. Further, the vocabulary does not describe the mechanical or functional compositions of critical building subsystems like HVAC and lighting.
#### Ontologies and energy management
- Energy management systems commonly consist of heterogeneous systems where a standardized way of retrieving and processing complex information is much desired.
- Various subsystems from different participants need to cooperate in EIP, which in turn increases the complexity in organizing the required information. They extend a couple of existing ontologies for processes and industrial symbiosis with domain vocabularies and necessary relationships for their energy applications. However, none of the existing work in energy management has shown the complete evaluation on the real systems and the extensibility as we present in this paper
#### Analysis of existing schemata
- The paper compares the capabilities of Haystack, IFC and SAREF using three metrics to measure the effectiveness of a schema: (i) the ability to completely map BMS metadata from three existing buildings to the schema, (ii) ability of the schema to capture the relationships required by applications, and (iii) the flexibility of the schema to deal with uncertainty as well as their extensibility to new concepts.
- Haystack shows the best vocabulary coverage as it is a tag-based model where tags can be arbitrarily combined. IFC is the most complete in describing application relationships as its model captures the building subsystems and the dependencies between them. SAREF scored the lowest for both metrics because it models the common concepts across different models and systems instead of comprehensively modeling buildings. In comparison, Brick has complete coverage of both vocabularies and application requirements.
- Brick builds upon these works in several ways to achieve both extensibility and expressibility. We utilize the tagging concept of Haystack and extend it with mechanisms to model relationships and entities. We use the location concepts from IFC. We use a semantic representation to utilize its flexibility and extensibility properties. The semantics allows us to formalize, restrict, and verify the usage of tags, entities, and relationships.

## Schema design
### Design principles
- Brick’s design focuses on data points, their metadata found in real building deployments and requirements defined by end use applications for operations and managements. Brick is separated into a core ontology defining the fundamental concepts and their relationships as discussed below and a domain specific taxonomy expanding the building specific concepts.
- Brick is distinguished from the other building schemata as follows:
  - Completeness: The current version of Brick covers the 98% of the vocabularies found in six buildings in different countries.
  - Vocabulary Extensibility: The structure of Tags/TagSets allow easy extensions of TagSets for newly discovered domains and devices while allowing inferences of the unknown TagSets with Tags.
  - Usability: Brick represents an entity as a whole instead of annotating it. It promotes consistent usages by different actors. Furthermore, its hierarchical TagSets structure allows user queries more generally applicable across different systems.
  - Expressiveness: Brick standardizes canonical and usable relationships, which can be easily extended with further specifications. SPARQL facilitates all the possible combinations of the relationships required by queries of the eights application categories in the literature.
  - Schema Interoperability: Using RDF enables straightforward integration of Brick with other ontologies targeting different domains or aspects.
### Tags and tagets
- With an ontology, we can analyze the metadata using standard tools and place restrictions to prohibit arbitrary tag combinations or relationships.
- We introduce the concept of a tagset that groups together relevant tags to represent an entity. With tagsets based on tags, we have a cohesive concept of a Zone_Temperature_Sensor that can be consistently used to represent actual instances of zone temperature sensor. We can further provide its semantics as the temperature is maintained between the zone’s Cooling_Setpoint and Heating_Setpoint.
### Class hierarchies
- As the central emphasis of our design is on representing points in the BMS, we introduce Point as a class, with subclasses defining specific types of points: Sensor, Setpoint, Command, Status, Alarm.
- Each point can have several relationships that relate the data point to other classes such as its location or equipment it belongs to.
- We define three dimensions as high level classes to which a Point can be related to: Location, Equipment and Resource. We define each category as follows:
  - Point: Points are physical or virtual entities that generate timeseries data. Physical points include actual sensors and setpoints in a building, whereas virtual points encompass synthetic data streams that are the result of some process which may operate on other timeseries data, e.g. average floor temperature sensor.
  - Equipment: Physical devices designed for specific tasks controlled by points belonging to it. E.g., light, fan, AHU.
  - Location: Areas in buildings with various granularities. E.g. room, floor.
  - Resource: Physical resource or materials that are controlled by equipment and measured by points. An AHU controls resources such as water and air, to provide conditioned air to its terminal units.
  - Note that the class hierarchy does not strictly follow a tree structure, and we use multiple inheritance when appropriate.
### Fundamental relationships
- Relationships connect the different entities in the building and are essential to providing adequate context for many applications.
- The categories of quintessential relationships we extract from the applications are:
  - Taxonomy: what class or classes of things define an entity
  - Location: which building, floor and room an entity is in, but also where in the room it is
  - Equipment Connections: what equipment an entity is connected to, and how it is connected
  - Equipment Composition: what equipment an entity is a part of, or what equipment is a part of it
  - Point Connections: what points affect the behavior of other points
  - Monitoring: what measures the entity or what it measures
- Portability and orthogonality are two primary concerns in designing the set of relationships. The orthogonality informs a set of relationships that are specific and non-redundant, which can lead to overfitting the set of relationships for a particular building or subsystem. To support the goal of designing a unified metadata schema across many buildings, these relationships must also be sufficiently generic to be portable to many buildings.
- A control sequence is the logic determining an equipment’s behavior. Select variables of such logic are exposed as points in building systems. Some points’ values are measurements of physical properties, some are results of calculations and others are configuration parameters used to control physical devices.
### Control sequences
- Brick does not currently attempt to model the control logic in building systems; rather, it describes the dependencies between sensors, actuators, commands, setpoints and related equipment and spaces. We model the control dependencies using the controls relationship between points.

## RDF and SPARQL
### Representing knowledge in RDF
- Brick adheres to the RDF (Resource Description Framework) data model, which represents knowledge as a graph expressed as tuples of subject-predicate-object known as triples.
- RDF enables easily composing different kinds of information in buildings such as hierarchical location information (e.g., room-101 is a part of the first floor) and interconnected equipment (e.g., a VAV is fed by an AHU).
- Brick especially exploits well-defined standard vocabularies from RDF, RDFS and OWL to express common relationships.
### Querying knowledge with SPARQL
- SPARQL queries specify constraints and patterns of triples, and traverse an underlying RDF graph to return those that match. For Brick applications, this underlying graph consists of all the entities and relationships in buildings.
## Brick development process
- Brick development was a collaborative effort from sixteen researchers across seven institutions across the U.S. and Europe.
- We organized the terms into a class hierarchy and identified relationships that would be essential but sufficient to capture the dependencies that existed between building equipment, locations and data points. We decided to use tags to support keyword search and ease of compatibility with tagging models such as Haystack
- To evaluate the effect of such “over-fitting” of Brick’s tagsets to the set of known BMS points, we examined the percentage of BMS points
## Applications
- As the timeseries data are in different structures compared to the metadata, the interactions are often separated into the following two steps.
- An application finds the names or the identifiers of the data points of interest with their metadata. Then, it retrieves or changes the data points’ timeseries data in a BMS or a data historian.
### Application coverage
- Brick allows applications to write portable queries that identify relevant resources in a building-agnostic manner. An application can then adapt its behavior to the set of returned resources, likely using some API to interact with the required points.
- The primary challenge in developing portable queries was accounting for the variance in relationships across buildings.

## Building operating system integration
### Building Operating System (BOS)
- Traditional BMSes provide supervisory operation and maintenance of different building systems. However, to support third party applications, we need to have other functionalities such as management of metadata, data storage, search, authentication and access control. We use the term Building Operating System (BOS) to describe such a system.
- A BOS abstracts the different types of systems, equipment and sensors in a building with a hardware presentation layer that provides a common interface for interactions and abstracts away different communication protocols such as BACnet, LonTalk or ZigBee. The infrastructure components are represented in a canonical way using Brick and stored in a database.
### Role of brick in a BOS
- The building Brick model describes all the infrastructure components using the Brick schema. Hence, it acts as the common metadata layer that applications and users use to interact with the building infrastructure. This Brick building model is stored in a metadata database and a user can search the database for specific sensors, setpoints, equipment, etc using SPARQL

## Integration with other ontologies
- There are various aspects of buildings that applications need to exploit and a single model cannot describe everything.
- In the RDF framework, it is easy to extend Brick to accommodate other ontologies by connecting relevant concepts via either predefined or custom relationships. Each ontology community can maintain and develop their own model without deteriorating the other models.
### Unit of measurement (QUDT)
- QUDT is a representative ontology for quantities, units, and data types. We link the vocabularies under QuantityKind and Unit it the QUDT ontology using the relationships hasQuantityKind and hasUnit respectively
### Control Logic (CTRLont)
- Even though Brick’s controls relationships can represent control dependencies between Points, some applications may require full control logic such as PID controllers and state machines. CTRLont is an ontology modeling control logic that can fully describe control actors and logic, and modularize the logic to ensure reusability and easy extension.
### Electrical Power System (SEAS)
- Smart Energy Aware Systems (SEAS) Knowledge Model is an ontology aligning energy systems to existing ontologies such as SOSA (Sensor, Observation, Sample, and Actuator) ontology and SAREF (Smart Appliances REFerence) ontology and has several subdomains including electric power systems.

## Conclusion
- The heterogeneity of building representation presents a major bottleneck in fast and low cost deployment of energy efficiency measures.
- Brick builds upon prior work and introduces a number of novel concepts. Brick uses easy to understand Tags and TagSets to specify sensors and subsystems in a building.
- We define tags and tagsets in an ontology with class hierarchies. We define portable and orthogonal relationships between entities from an extensive list of smart-building applications. 
- Relationships among entities are represented as triples, which allows users to leverage existing tools to build and query the resulting building representations.
- We showcase Brick’s extensibility model as well as its interoperability with other existing schemata and ontologies.
- Finally, we have proposed practical methodologies to use Brick in the real world including how to convert existing unstructured and structured metadata into Brick and how to integrate Brick with actual building systems.
