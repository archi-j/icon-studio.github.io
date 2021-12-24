---
layout: post
title: "[Paper Reading] Cloud BIM Technology as a Means of Collaboration and Project Integration
in Smart Cities"
date: 2021-09-05 09:00:00 +0300
description: 2021_Cloud BIM Technology as a Means of Collaboration and Project Integration in Smart Cities # Add post description (optional)
img: 20210905_post_main.jpeg # Add image post (optional) 280px, 350px, 470px, 700px, 940px
fig-caption: # Add figcaption (optional)
category: [PR]
tags: [BIM, Cloud, Reading]
---

**Publication year:** 2021 <br>
**Authors:** Ihuoma Onungwa , Nnezi Olugu-Uduma, and Dennis R. Shelden <br>
**DOI:** [https://doi.org/10.1177/21582440211033250](https://doi.org/10.1177/21582440211033250)

## Introduction
- Background
  - Cloud BIM is one of the technologies that can be used for smart city development and its implementation methods should be defined.
  - BIM 360 enables seamless exchange of drawings between consultants, facility managers, civil engineers, and other stakeholders in the project. It also facilitates visualization of the city and data exchange for IoT.
- Problem
    - Current technologies have governance problems, problems preserving worksets, loss of information in drawings, and difficulty in specifying coordinates on-site.
    - A limited number of studies have been carried out on cloud BIM and smart city development, but instruments, procedures, and methods for digital modeling of smart cities have not been clearly defined.
- Research Goal
    - This article aims to review the application of recent technologies in BIM collaboration and to review cloud BIM as a means of collaboration and project integration in smart city development using the Master Plan of Georgia Institute of Technology.
    - This paper investigates the use of cloud BIM, Revit, Autodesk Infraworks, and other modern technologies for digital modeling of a smart city.
    - It also creates methodologies for developing smart cities using cloud BIM and recommends a digital modeling workflow for smart city development

## Literature Review
- Cloud-Based BIM Technology
  - Ease of access, storage manageability, and high-performance computing abilities are the benefits of using cloud BIM technology for managing and storing BIM database
  - Cloud BIM can provide multiple servers, conduct parallel analysis and computing, and display all online BIMs in a 3-dimensional (3D) visualized way on standard web browsing. Also, it is used for costing, real-time quality checks and for site diaries.
  - However, most of solutions concentrate on the design and development phases of a project while the use of cloud BIM for operation, facility management, energy analysis, and other post-construction activities has not been established
  - The major hurdles includes the lack of clarification on who is responsible for ownership of cloud BIM models. Interoperability is another challenging to operate on different cloud platforms to interoperate.
- Taxonomy of Cloud-Based BIM Technology
  - The essential idea of cloud computing is to manage and schedule uniformly network-connected computing resources. The network that provides resources is referred to as a "cloud" that can be accessed at any time, used as needed, and paid for. The resources include networks, servers, storage, and software applications, which can be easily provided and released with minimal delay or interaction between service providers.
- Cloud-Based BIM governance
  - This approach attempts to bring various stakeholders to a shared platform to reach a consensus. Collaborative BIM servers have various technical requirements, however; this framework should be created to support the processing of data created during construction, because cloud BIM provides various stakeholders with exposure to project data.
- Challenges to Cloud BIM Implementation
  - Mahamadu et al. (2013): access authorization to users, information sharing doundaries, and legal and contract limitations
  - Alreshidi et al. (2018) identified cost of initial set up, maintenance, training, dependency on internet connection (especially in developing countries)
- Industry Foundation Classes (IFC)
  - IFC contains object specifications that provide a useful framework for data sharing between applications. IFC files were the first files for collaboration in the AEC industry before BIM servers and cloud BIM were introduced
  - IFC offers the universal standard for data exchange and is ideal for resolving the problem of Interoperability between applications
- BIM Server
  - It can be defined as a collaboration platform that maintains a repository of the building data and allows native applications to import and export files from the database for viewing, checking, updating, and modifying the data. BIM servers provide a platform for exchanging 3D models with attributes and embedded intelligence. To accomplish the aim of shared product data models across a building's life cycle, technical, method, and standardization issues needed to be addressed
- BIM and Smart City development
  - It has been used for energy efficiency, sewage planning, water demand, assessment of carbon dioxide emissions, and other environmental factors. Also, it has been touted as the instrument for interconnectivity of buildings and external services in smart city planning. For this to happen, the building has to be in the correct geographical position.
- IoT and Smart City Development
  - Hardware layer is important for developing smart city framework. The hardware layer is located at the bottom of the structure and it contains tangible hardware elements such as sensors, actuators, chips, and radios. The elements in this layer often communicate directly with the environment, other hardware elements, and some times users or consumers.

## Research Method & Result
- The methodology consists of six steps:
  - develooping individual models in Revit
  - creating the existing master plan in AutoCAD
  - placing buildings in the correct geographical location
  - storing individual Revit models and master plan in BIM 360
  - linking individual models to a master plan in the correct geographical position
  - exporting individual buildings and master plan to Autodesk Infraworks

## Challenges Encountered
- The large size of the master site slowed down the pace of work. Individual Revit models had to be unlinked to facilitate the process.
- Coordinates could not be specified on the cloud (BIM360). Drawings had to be downloaded locally and uploaded back after coordinates were specified.

## Findings and Discussion
- Volume: 65 Revit files, the Revit master plan, and Autodesk Infraworks files were all uploaded to BIM BIM360.
- Speed: The size and number of drawing files reduced the speed of execution of the project
- Accuracy: Clash detection from drawings on the master plan could easily be detected with BIM360.
- Information Management: In BIM360, folders were created for each drawing and the master site plan. This can be used for large-scale drawing and smart city development
- Stakeholders' Participation: All stakeholders were able to monitor the real-time progress of the project using BIM360
- Visualization of Information: Visualization of the project output was clear and authentic with the use of BIM360
