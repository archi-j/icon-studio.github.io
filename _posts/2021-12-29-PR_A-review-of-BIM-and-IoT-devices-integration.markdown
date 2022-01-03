---
layout: post
title: "[Paper Reading] A review of building information modeling (BIM) and the internet of things (IoT) devices integration"
date: 2021-12-28 09:00:00 +0300
description: 2021_BIM A review of building information modeling (BIM) and the internet of things (IoT) devices integration # Add post description (optional)
img: 20211229_post_main.jpg # Add image post (optional) 280px, 350px, 470px, 700px, 940px
fig-caption: # Add figcaption (optional)
category: [PR]
tags: [BIM, IoT, Reading]
---

**Publication year:** 2019 <br>
**Authors:** Shu Tang, Dennis R. Shelden, Charles M. Eastman, Pardis Pishdad-Bozorgi, Xinghua Gao <br>
**DOI:** [https://doi.org/10.1016/j.autcon.2019.01.020](https://doi.org/10.1016/j.autcon.2019.01.020)

## Introduction
- BIM models offer high fidelity representations of the project at the component level. By incorporating geometry, spatial location and a scalable set of metadata properties, BIM models provide a
high-fidelity operable dataset capturing the as-designed building objects, properties and spatial organization as a set of virtual assets.
- IoT can be defined as “interconnection of sensing and actuating devices providing the ability to share information across platforms through a unified framework, developing a common operating picture for enabling innovative applications”.
- IoT data enhances this information set by providing real-time and recordable status from the actual operations in construction and operations. The potential information sampled from sensors is highly variable but includes both positioning information, physical measurements, weather, etc.
- Both BIM and IoT data may be accessed through several mechanisms, including manual interfaces of proprietary systems, programming APIs associated with these applications, potential database connections to the systems, and export via open standards. A number of open standards are emerging in both BIM and IoT fields.
- Most of the current studies can only be considered as the integration of BIM and IoT devices that lack information sharing across the Internet through a unified framework. The applications of BIM and IoT device integration are scattered, it is sufficiently matured that patterns, issues, and opportunities can be identified.

## methodology
- To acquire up-to-date and high-quality papers, the following steps were taken:
  - (i) Journal search from Web of Science
  - (ii) Set journal selection criteria and select high impact journals
  - (iii) Paper search in individual databases and libraries
  - (iv) elimination of duplication and irrelevance
  - (v) Categorization based on the results of content analysis and discussion on reviewed articles
  - (vi) Explore potential research directions for the future.

## BIM and IoT integration for different domains
- Construction operation and monitoring
  - On-site environment monitoring
  - Resource monitoring
  - Communication and collaboration
  - Construction performance and progress monitoring
- Health and safety Management
  - H&S training
  - On-site monitoring for H&S
- Construction logistic and Management
  - Automation in prefabrication
  - Lean Construction
- Facility Management
  - Building operation and Maintenance
    - i) Identify physical building components and link with BIM models through RFID tags [42,43] for asset tracking
    - ii) link physical objects with digital objects by linking BMS and BIM using BIM tool APIs for O&M
    - iii) Extract real-time data, visualize problems either from Augmented Reality (AR) devices or BIM tools on mobile device on facility managers' perspective to conduct maintenance or control of assets
  - Building performance management
    - i) Linking BIM with BMS data for visualization and management of real-time building performance data
    - ii) monitoring Indoor Environment Quality (IEQ) by reading temperature and humidity information from BIM tools in a timely manner and improving user comfort
    - iii) using semantic web technologies for real-time building performance monitoring and assessment
  - Energy Management
    - i) web-based energy management solution which allowed facility manager to view BIM models, query sensor data and get actuation suggestions at a “near real-time” basis
    - ii) Geographic Information System (GIS) integrated energy management solutions that are capable of visualizing 3D models and monitoring geospatially referenced energy usage
    - iii) software/system architecture as energy management solution to monitor real-time energy consumption and building condition with BIM
    - iv) energy performance analysis based on real-time energy consumption using cosimulation tools like Building Controls Virtual Test Bed (BCVTB) and Cyber-Physical Building Energy Management System (CBEMS) which extracted building data from BIM models
    - v) integration of WSN and BIM for energy monitoring, real-time feedback & control and energy benchmarking
  - Disaster and emergency response
    - i) detecting indoor location of trapped victims and display location in BIM models
    - ii) calculating shortest evacuation path with building information from BIM models in real-time and location data from sensors or victims' mobile devices
    - iii) creation of mobile guidance for evacuation with BIM tool API and mobile devices
    - iv) large scaled emergency response using BIM, IoT devices and GIS

## BIM and IoT devices integration method
- When discussing BIM and IoT device integration, there are three components:
  - BIM serves as a data repository for contextual information including building geometry, IoT devices' description, static information and other soft building information collected from occupancy patterns and schedule data like social media, building feedback, occupant interactions, room allocation, weather forecast and financial pricing
  - the time-series data which records continuous sensor readings [68]. Traditional time-series data is stored in a well-structured relational database and can be effectively queried using Structured Query Language (SQL).
  - the integration method between contextual information and time-series data. This section explains different integration methods of contextual information (BIM data) and timeseries (sensor collected) data.
- BIM tools' APIs + relational databases
  - Description of this approach
    - i) Sensor collected time-series data is stored and updated in relational database (e.g. SQL server database, Microsoft Access)
    - ii) BIM models which are constructed in BIM tools (e.g. Revit), can be exported into relational database formats using APIs (e.g. Revit DB Link, Dynamo, Grasshopper)
    - iii) Define a database schema which clarifies the relationship between virtual objects and physical sensors.
    - iv) A two-way importing and exporting of a relational database and BIM model can be achieved using APIs
    - v) Processing queries of sensor data through custom-built API (e.g. graphic user interface (GUI) based on Revit), third party processing engine (e.g. Unity engine) and direct query over SQL database (as the object properties).
  - Discussion of this approach
    - Pros
      - The integration process can be done using the existing APIs. Model data can be exported to open database connectivity (ODBC) format which is compatible with external database software (e.g. MS Access, MySQL).
      - the ease in linking model data and sensor data because of they both store in the relational database.
      - time-series data can be automatically updated in BIM tools with these APIs.
    - Cons
      - Since only shared parameters between projects and families can be exported, there will be limitations on what to update.
      - although sensor data can be automatically updated in the relational database, manual export of model files incurs repetitively if model change happens
- Transform BIM data into relational database using new data schema
  - Description of this approach
    - One effective way to integrate sensor data with BIM is to transform BIM data into a queryable database which allow information extraction from different users' perspective
    - Transforming BIM data into relational database structured data is the foundation step for binding time-series data with BIM. Once BIM data is SQL queryable, sensor data can be linked to BIM
  - Discussion of this approach
    - Pros
      - As a new schema or data structure is defined based on the user's perspective, this approach shows its flexibility in expanding users' perspectives while effectively extracting external system data. Time-series data retains in its original database.
      - This approach has the capability to use existing SQL in normal database management system platforms, avoiding rewriting query interface from scratch.
    - Cons
      - creating a new data schema requires significant efforts in mapping data which is time-consuming.
      - manipulation on SQL is necessary if special queries or operations are needed.
- Create a new query Language
  - Description of this approach
    - to create a new query language to query sensor data over BIM models or IFC models instead of using SQL. the newly developed query language is used to developing queries that process time-series data.
  - Discussion of this approach
    - Pros
      - expressiveness and ease of use is obvious when compared to general purpose language
    - Cons
      - the newly developed query languages either lack real-time sensor data query capability or used external ELP.
      - to implement a newly developed query language about real-time sensor data and BIM, a corresponding platform need to be developed at the same time
      - new query languages that are not standardized may not be widely adopted.
- Semantic web approach
  - Description of this approach
    - The integration of BIM and Semantic Web Technologies has the potential to meet the requirements for storing, sharing and using heterogeneous data sets.
    - The key concept is to have those data sets to be represented as or tagged using Resource Description Format (RDF). Linking BIM ontologies e.g. IfcOWL and ontologies in other domain e.g. Smart Appliances Reference ontology (SAREF), Semantic Sensor Network (SSN) for sensor devices domain is an effective approach for BIM and IoT device integration.
  - Discussion of this approach
    - Pros
      - linking cross-domain data in a homogeneous format and the ease of interlinking silos.
    - Cons
      - i) most of time-series sensor data was stored in well-structured and relatively mature relational database, the way the relational database store sensor data is more effective for query than store sensor data in RDF format
      - ii) Duplication of data may incur when converting time-series data into RDF
      - iii) The performance of RDF representing fixed-structured data is inefficient and storage consuming
- Hybrid approach: semantic web + relational database
  - Description of this approach
    - both the Semantic Web and relational databases are used to store cross-domain data.
    - Key steps:
      - i) represent contextual information including building context data, sensor information, and other soft building information into RDF format using semantic web approach
      - ii) Retain sensor collected time-series data in the relational database
      - iii) Map contextual information with time-series data, in particular, time-series data can be referenced using sensor ID described in RDF.
  - Discussion of this approach
    - i) Time-saving: as time-series data still stored in the relational database, duplicating time-series data into RDF format is not necessary
    - ii) Storage saving: the way that RDF data is stored (triple stores) requires more storage than relational database
    - iii) Better performance: relational database performs better in data lookup than triple stores
    - iv) Effective query language: the integrated query method use existing SPARQL and SQL to query RDF data and sensor data respectively.

## Future research direction
- Service-Oriented-Architecture (SOA) and web services for BIM and IoT Integration
  - SOA acts as the premier integration and architecture framework for the complex and heterogeneous computing environment. It uses the concept of software design where various services can be combined to provide functionalities of a large application through a communication protocol over network
  - Real-time model update based on IoT device readings
    - A new design of SOA patterns using RESTful Web Services named RESTful endpoint would be a potential solution to enable BIM entities' status update based on IoT devices' readings.
    - A RESTful endpoint, on one hand, receives readings from IoT nodes, on the other hand, conducts create/read/update/delete (CRUD) operations in the BIM data layer
  - Information acquisition and controls - a two-way-interaction
    - current research only realized one-way interaction (e.g. energy monitoring, IEQ monitoring, building performance monitoring). Only a few studies have explored human-building interaction for cognitive buildings
    - No two-way interaction that involves control of actuators through BIMs has been discovered in the reviewed articles
  - Ubiquitous monitoring and crowd sourcing monitoring
    - Potential solutions utilizing a RESTful service named Callback Responder can blend with traditional SOA patterns to realize ubiquitous monitoring and crowd-sourcing monitoring
    - Ubiquitous monitoring continuously providing information about building elements and IoT devices regardless of the situation in a 24/7 manner.
  - Integration with other cutting-edge technologies
    - Adding VR/AR/MR web-based application framework like the mobile agent to the SOA design patterns, digital models can be superimposed into the real world for web-based AR applications
- Standards for information integration and management in the AEC industry
  - The continuous developing frameworks aim to develop a shared understanding of CPS and smart cities including their foundational concepts and unique dimensions such as common language, taxonomy, architectural principles.
  - hardly any approach is available for this industry that:
    - i) provides a comprehensive overview of data sets that need to be handled in AEC industry
    - ii) evaluates the effectiveness of different methods that query and represent cross-domain data sets.
    - iii) globally manages collected data, processes information, and accumulates knowledge
    - iv) assures seamless information flow across different domains throughout lifecycle
  - Without standards for information integration and management, it is costly and time consuming to sort large and heterogeneous data sets into usable order
- Interoperability: IoT devices-BIM-smart cities
  - Although there is plenty of on-going research on solving interoperability issues among IoT devices and BIM, the interoperability issues among IoT paradigm and AEC industry still remain.
  - a potential research question can be how different data model, schema, standards and protocols like IoT device protocols, open BIM standards, and city-scale data model can be integrated to solve interoperability issues for smart devices, smart buildings, and smart cities.
  - Potential research directions can focus on current limitations, including:
    - i) differences in vocabulary, context, and semantic meaning in various domains
    - ii) differences in the data structure like data attributes and data formats among these schemas, IoT devices' communication protocols, and web-services' protocols.
- Cloud computing
  - Cloud computing involves hosting computing services over the Internet and enables connecting different IoT devices to existing Internet infrastructure
  - Enable real-time big data analytics
    - Based on BIM and IoT devices collected data, big data techniques can be applied to automated decision making that enables intelligent monitoring and actuation.
    - To enable real-time big data analytics, information acquired needs to be stored in an online storage which can be accessed from multiple IoT devices.
    - In the IoT cloud paradigm, there is no perfect big data management solution for the cloud
  - Create standards for the BIM-IoT Cloud
    - Although some research tried to standardize IoT and Cloud paradigms, there is no clear standard protocols, architecture, and APIs that interconnect various IoT devices and services in the Cloud
  - BIM and IoT data storage
    - The massive data amount coming from IoT deceives and BIMs will arouse problems in cloud-based data storage.
  - Using cloud-based IoT integration portal for BIM
    - These integration portals enable the machine-to-machine integration, visualization of sensor data, user interaction with actuators, service development and web resource update based on sensor data.
    - These cloud-based integration portals together with cloud storage will facilitate BIM applications integration in more convenient ways.
  - Create general integration methodology
    - even though several applications were built around IoT, BIM, and Cloud, little effort has been made to produce a universal methodology which integrates IoT, BIM and Cloud systems
  - Other issues
    - i) security and privacy
    - ii) pricing and billing
    - iii) network and communication
    - iv) scalability and flexibility
    - v) IoT devices performance management

## Conclusion
- This paper contributes to the body of knowledge by presenting an in-depth review of BIM and IoT devices integration in the AEC industry from domain application perspective and integration methodologies, and by shedding lights on current limitations and prominent areas for future research and development.
