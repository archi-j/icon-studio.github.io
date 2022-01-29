---
layout: post
title: "[Paper Reading] A framework for integrating BIM and IoT through open standards"
date: 2022-01-10 09:00:00 +0300
description: 2018_A framework for integrating BIM and IoT through open standards # Add post description (optional)
img: 20220110_post_main.jpg # Add image post (optional) 280px, 350px, 470px, 700px, 940px
fig-caption: # Add figcaption (optional)
category: [PR]
tags: [IoT, Interoperability, Reading]
---

**Publication year:** 2018 <br>
**Authors:** Bhargav Dave, Andrea Buda, Antti Nurminen, Kary Främling <br>
**DOI:** [https://doi.org/10.1016/j.autcon.2018.07.022](https://doi.org/10.1016/j.autcon.2018.07.022)

# Introduction
- Recent advances in technologies such as Internet of Things (IoT), wireless sensors, data processing and analysis, and Building Information Modelling (BIM) have the potential to transform how we interact with the built environment and improve the experience for end users and service providers
- With the emerging popularity of the BIM platforms, there is an opportunity to leverage this technology so that it can be used to build open platforms that synchronise with diverse information sources such as wireless sensors and building automation systems
- However, there is a gap in research in integrating built environment data with IoT standards that shows tangible open systems which are built upon open standards. The need for open standards
become acute due to plethora of protocols and information exchange standards being used in both the built environment and IoT domains
- One of the motivations behind this study is to support distributed, cross cutting and bottom-up innovation by supporting both consumption of data provided by the system and development of applications and further research by utilising the APIs (Application Programming Interfaces) provided by the platform.


## Background
- The field of built environment is plagued by information silos and lack of standardization that affects the information flow
- As a major platform emerging to host built environment data, BIM is an important technology to consider from IoT integration perspective
- BIM and IoT
  - BIM now extends itself to cover many technological advances the industry is witnessing and is the natural interface for IoT deployment
  - Open standards, BIM and automation
    - Within the subdomain of building management systems, which at the moment is the “low hanging fruit” from IoT deployment perspective since it already hosts majority of sensor deployments, there exist plethora of protocols and standards such as Zigbee, KNX, BACnet, LONWorks, DACI, Mobus, oBIX, OPC, etc)
  - Visualization of spatial information in real-time
    - As a mediator of various data sources, an integration phase is required, typically collating CAD, BIM and GIS data sources to a multipurpose platform. However, as the related data sets are typically very complex, real-time visualization thereof has become a severe challenge, easily exceeding the capacity of the computer. The hopes often lie in future hardware; unfortunately, even the latest hardware always seems to become overloaded
- IoT standards
  - This vision of interoperability requires the mastery of protocols and standards to leverage system interoperability due to the large number of products, platforms, and competing applications that coexist in the IoT.
  - In lack of standardized solutions, it is likely that a proliferation of architectures and identification schemes will develop side by side, each one dedicated to a particular or separate use, which will lead to the fragmentation of the IoT. At the time of writing, there are more than 250 reported IoT platforms available on the market
- IoT deployment
  - Most IoT deployments remain expert driven and cater to specialised use cases. Also, majority of sensors due to their inherent nature are hidden away from human interaction, which in turn make them an area reserved for top-down innovation. The IoT domain in general and its deployment areas such as Smart Cities have come under criticism for being top driven and self-congratulatory
  - Researchers have realised the potential of campuses as rich test bed for IoT deployment. However, such opportunities are also somewhat restricted due to point wise implementation of proprietary technologies that do not provide open interfaces. Also, researchers have criticised that previous smart campus deployments have mainly been conducted in a lab based environment that provide limited potential to engage with real life users


## Otaniemi3D –core framework
- At the outset, a three way challenge is addressed by this research
  - i) the integration of built environment data and IoT sensors
  - ii) ensuring that open standards are used in deployment and integration of both IoT and BIM standards
  - iii) developing application areas to demonstrate the potential of this integration through real-world applications.
- Design rationale
  - The main aim of this research is to connect spaces/buildings with the data they generate through IoT devices with people living/working in those spaces
  - This knowledge can be useful when analysing data: for example a temperature sensor positioned close to a window might be the reason why the recorded value is an outlier in the considered data set.
  - There is a set of more concrete objectives, which represent the foundation of this research,
    - i) develop an end-to-end open source, secure IoT stack, from devices' firmware to web services
    - ii) provide programmatic data access using the standardized Web-API
    - iii) connect IoT data with the context and spaces in which it has been generated
    - iv) develop interfaces including Virtual Reality to provide context
aware information to various stakeholders.
<img src="https://ars.els-cdn.com/content/image/1-s2.0-S0926580517305964-gr1_lrg.jpg" class="post_img" style="width:60%;" alt="BACnet device, object, and properties">

- System architecture
  - the conceptual system architecture of Otaniemi3D, an open, campus wide platform that integrates Building Information using IFC with wireless sensor nodes through Open APIs. In synthesis, the developed system can be broken down in 3 main components:
    - IoT Devices
      - Their primary function is to sense and act upon the environment in which they have been installed.
    - Backend Server
      - A collection of loosely coupled services communicating with each other following the SOA (Service Oriented Architecture) design style.
      - This layer deals with the interpretation of the built environment data through standard formats such as IFC (Industry Foundation Classes) either through directly stored local data or through data stored in servers and accessed through APIs.
    - Front end(s)
      - The primary function of the frontends is to manage the interaction with the target users of the system (students and researchers).
      - one of the main goals of the entire smart campus project is to spark the development of a multitude of apps, leveraging on the competencies and interests of various research groups.
<img src="https://ars.els-cdn.com/content/image/1-s2.0-S0926580517305964-gr2_lrg.jpg" class="post_img" style="width:70%;" alt="BACnet device, object, and properties">

- Standardized Web-API
  - One of the objectives of the Smart Campus backend is to harmonize publishing and consumption of data though a standardized Web-API.
  - The selected standards for achieving this goal are the Open Messaging Interface (O-MI) (Open Group IoT Standard) and the Open Data Format (O-DF) (Open Group IoT Standard) published by the Open Group (TOG)
  - The key characteristics of these standards are:
    1. Transport agnostic: O-MI runs on top of existing transport level protocol. In general HTTP and WebSockets are the preferred protocols.
    2. Publication and discovery of data sources and semantic metadata: The data and methods available provided by a given node can be discovered using the ReadAll operation. In addition O-DF tags can be semantically enriched using RDFa and LinkedData vocabularies.
    3. Payload agnostic: Even though the preferred payload is O-DF (XML formatted), within specific O-DF tags any payload could be transported (CSV, HTML, proprietary file formats), or even binary file formats converted using Base64 binary-to-text encoding.
    4. Support for Subscription: The possibility to create ad hoc, time limited information flows by specifying for how long (TTL) and at which sampling rate (INTERVAL) the data should be received, is the cornerstone of O-MI and what makes it particularly suited for IoT
<img src="https://ars.els-cdn.com/content/image/1-s2.0-S0926580517305964-gr3_lrg.jpg" class="post_img" style="width:70%;" alt="BACnet device, object, and properties">    

- IoT devices and service
  - The IoT Service has been implemented using the open source reference implementation of the O-MI and O-DF standards, developed at Aalto University (available online at https://github.com/AaltoAsia/O-MI).
  - The data collected from the devices can be stored in a variety of databases. Currently, the O-MI and O-DF reference implementation supports all the major RDBMS (Relational Database Management Systems, such as SQL Server, Oracle, MySQL, Postgresql, SQLite etc.) providing a JDBC (Java Database Connectivity) driver.
<img src="https://ars.els-cdn.com/content/image/1-s2.0-S0926580517305964-gr4_lrg.jpg" class="post_img" style="width:80%;" alt="BACnet device, object, and properties">

- BIM service and front end
  - This service is essentially used to manage the relationship between spaces/buildings (described using IFC) and IoT data, in particular the translation of static IFC files into interactive web documents.
  - The translation toolchain adopted, required some custom programming for retaining the association between the IfcSensorType and the final output web formats. The process described is very similar to the one adopted by BIMServer (http://bimserver.org/).
  - It is important to highlight that the outputs produced by IfcOpenShell and InstantReality/AOPT is acceptable if the main purpose is simply to visualize the model.
<img src="https://ars.els-cdn.com/content/image/1-s2.0-S0926580517305964-gr5_lrg.jpg" class="post_img" style="width:70%;" alt="BACnet device, object, and properties">


## Otaniemi3D proof of concept
- The proof of concept has been called Otaniemi3D, where Otaniemi is the name of the Aalto University Campus and 3D stands for the dimension in which the BIM and IoT data is presented.
- the core components are:
  - (1D) Data Analytics Page.
  - (2D) Floor Plan and heatmaps page.
  - (3D) 3D Model and precise sensor location.
<img src="https://ars.els-cdn.com/content/image/1-s2.0-S0926580517305964-gr6_lrg.jpg" class="post_img" style="width:80%;" alt="BACnet device, object, and properties">

- 1D view. Live and historical sensor data
  - This view simply presents the sensor data in a traditional graph form.
  - To plot sensor readings, it is possible to drag and drop the items in the tree (e.g. CO2, Humidity, Temperature, etc. sensors organized according to room in which they have been installed) into the dotted line box
<img src="https://ars.els-cdn.com/content/image/1-s2.0-S0926580517305964-gr7_lrg.jpg" class="post_img" style="width:70%;" alt="BACnet device, object, and properties">

- 2D view. Floorplan heatmaps
  - This view leverages the same functionalities implemented for the 1D-View, but instead of plotting single data points, it calculates an average for the selected time period generating a heatmap which is overlaid on the building floorplan.
<img src="https://ars.els-cdn.com/content/image/1-s2.0-S0926580517305964-gr8_lrg.jpg" class="post_img" style="width:70%;" alt="BACnet device, object, and properties">

- 3D view. Locating sensors 3D model and 360 panoramic images
  - The 3D View is still in an experimental phase. Besides the traditional 3D interaction pattern (Zoom, Pan, Tilt), it is also possible to enter a room number in the search bar activating a custom viewpoint/camera centered in the middle of the selected room
  - Once in the middle of the room, it is possible to click a “360° Box” which opens an interactive 360° picture of the room. In this picture, it is possible to spot and click on the installed sensor box to retrieve the current readings. The same interactivity is also possible from the 3D model
<img src="https://ars.els-cdn.com/content/image/1-s2.0-S0926580517305964-gr9_lrg.jpg" class="post_img" style="width:70%;" alt="BACnet device, object, and properties">


## Supported use cases
- With an open framework, the authors envisage that a variety of use cases can be developed to demonstrate the capability of the system. Being a campus based system, there is an ongoing effort to encourage other research teams and students to develop compatible applications by using the open APIs provided by the Otaniemi3D platform
- Aalto spaces mobile application
  - The integration between the Aalto Space app and HVAC controls through O-MI and O-DF standards was part of the RealGO research & development project at Aalto University.
  - Aalto Space is a mobile app for Android and iOS devices (available in respective App stores), which can be used to find and book study and group work facilities and meeting rooms within the campus.
  - While the Aalto Space app was developed separately to the Otaniemi3D project, the developers of the ReadyGO project saw an opportunity to integrate the app with air conditioning and ventilation control along with the Aalto's campus booking facility using the open standards developed through Otaniemi3D research.
  - Functional description
    - The newly developed features have the possibility to control air conditioning and ventilation from the room reservation in the Aalto Space app.
    - It controls the building automation system of Fidelix (a commercial building automation provider based in Finland) and radiator thermostats of Fourdeg.
  - Technical implementation
    - Aalto Space app was modified to include controls to boost ventilation and change set point temperature after a reservation is made.
    - The app middleware server was used instead of direct messaging to the O-MI Node as it provides a simple security model for the app communication and allows easier modifications to connections to external services.
    - The device agent is a wrapper which converts O-DF/O-MI messages to proprietary vendor specific interfaces. It also schedules the reset for default air conditioning settings and publishes the existence of the devices to the O-MI Node.
  - Benefits of Aalto Space integration
    - One of the main benefits of the Aalto Space app is to enhance facility management by integrating IoT sensors to provide real-time control and information availability for better decision making.
    - By integrating real-time controls with the Aalto Space app and integrating these with sensors, there is a potential to improve user comfort and space utilisation.
    - by integrating the Aalto Space app with the campus' facility booking system, the HVAC systems can respond directly to the user demand and switch off when not in use.
    - It should be noted that without the use of open standards such as OMI/ O-DF, it would be quite challenging to integrate all the information sources such as, Aalto's campus booking system, heating and ventilation controls and sensors by Fidelix and Fourdeg, and building data through Aalto Space and Otaniemi3D as highlighted in the case here.
- Future integration


## Conclusion
- Contribution
  - This research shows that it is possible to engage wide range of stakeholders with IoT devices by integrating them with building information data. The communication takes place through Open Messaging interfaces eliminating the need to depend on closed proprietary systems that hinder scalable deployment of such systems and through intuitive interfaces
- Limitation
  - Without standardized export guidelines for IFC files, and parsers to export this data for web, it is challenging to map sensor data to objects in IFC.
  - Data capture, storage and analysis is also a challenge in such a distributed and heterogeneous environment, which needs to be tackled at the technical architecture design level
  - ethical and user privacy issues in data capture pose a risk that needs to be managed actively in order to develop real-world applications.
