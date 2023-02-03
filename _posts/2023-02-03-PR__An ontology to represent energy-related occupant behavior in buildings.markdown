---
layout: post
title: "[Paper Reading] An ontology to represent energy-related occupant behavior in buildings. Part I: Introduction to the DNAs framework"
date: 2023-02-03 09:00:00 +0300
description: "2015_An ontology to represent energy-related occupant behavior in buildings. Part I: Introduction to the DNAs framework" # Add post description (optional)
img: 20230203_post_main.jpg # Add image post (optional) 280px, 350px, 470px, 700px, 940px
fig-caption: # Add figcaption (optional)
category: [PR]
tags: [Occupant Behavior, Building Energy, Ontology]
---

**Publication year:** 2015 <br>
**Authors:** Tianzhen Hong, Simona D'Oca, William J.N. Turner, Sarah C. Taylor-Lange<br>

## Introduction
- Due to the stochastic nature of occupant behavior, the mutual influences between humans, buildings, and the environment cannot be described in a simplistic way
- However, technology alone does not guarantee low energy use in buildings.
- So-called energy-efficient green buildings exhibit large fluctuations in energy consumption due to how occupants interact with building systems.
- Energy efficiency in buildings is not just about new technologies, it's about optimal decisions and an overall improvement in human behavior. This paper refers alternately to “human” behavior with respect to the more general concept of the stochastic nature of a human being, and to “occupant” behavior when specifically indicating actions undertaken by building users.
- This study focuses on energy-related building occupant behavior, taking into account actions and activities people perform in buildings to provide themselves with good indoor environmental quality (IEQ) (thermal comfort, visual comfort, acoustic comfort, indoor air quality, etc.).
- The term ‘behavior’ refers to “observable actions or reactions of a person in response to external or internal stimuli, or respectively actions or reactions of a person to adapt to ambient environmental conditions such as temperature, indoor air quality or sunlight”.
- In all of these studies, macroeconomic, cultural and climatic factors accounted for some of the locational variation, but not the variation across users.
- No standardized way of reporting or comparing results from different studies has emerged. This lack of structure in the field means that behavior models are difficult to compare and can be difficult to incorporate into building simulation tools.
- Among researchers, energy modelers and software developers, no common consensus has been reached on the standardization of modeling approaches, simulation tool usability and documentation or interoperability issues.
- To address these issues, a DNAs ‘Drivers - Needs - Actions Systems’ framework providing an ontology to standardize the representation of energy-related occupant behavior in buildings, is described in this study.

## Review of human behavioral frameworks
- The nine cognitive-behavioral frameworks are described as follows:
  - Perceptual Control Theory (PCT)
  - Human Operator Simulator (HOS)
  - Cognitive Complex Theory (CCT)
  - The Executive Process Interactive Control (EPIC)
  - The State, Operator and Result (SOAR)
  - The Adaptive Control of Thought (ACT)
  - The Cognition as a Network of Tasks (COGNET)
  - The Architecture for Procedure Execution (APEX)
  - Business Redesign Agent-Based Holistic Modelling System (BRAHMS)
- None of the models focuse on energy-related behavior in the building indoor environment, framing the cognitive processes of the ‘inside world’ that lead building occupants to perform actions in the ‘outside world’, such as interacting with control systems in the building spaces, when driven by needs from the ‘inside world’.

## Review of occupant behavior investigation methodologies
- This new approach accounts for the fact that occupants do not always make logical choices and act stochastically rather than deterministically
- Existing monitoring studies of drivers, needs, actions and systems, behavioral models, and simulation studies, have captured the principal aspects of energy-related human behavior within a building

### Monitoring studies
#### Field monitoring
#### Questionnaires and self-reporting

### Modeling studies
- Behavioral models are then developed to predict the probability of an occupant interacting with a building system. Implicit models are used to understand the driving forces behind the behavior itself or to predict the state of a building system or the occurrence of an occupant's action
- Explicit models are used to provide a personalized description (or future prediction) of the state of a building system or the actions of an agent

#### Implicit models
- Implicit models of energy-related human behavior include linear regression models, logistic regression models with a single variable or multiple variables.

#### Explicit models
- Explicit models of human behavior are commonly based on occupancy presence and movement data and are used to predict the probability distribution of an event (e.g. occupant being present in a space) or behavior (e.g. occupant moving within a space) to occur.

#### Data mining to support modeling studies
- Patterns of data discovered through data mining techniques may highlight commonsense knowledge, applicable to fit both direct and indirect models.

### Simulations
- Aim of predicting and leveraging the impacts of occupant behavior on 1) building energy performance, 2) comfort levels and 3) indoor air quality (IAQ).

## The DNAs occupant behavior framework
- Drivers represent the environmental factors from the outside world that stimulate occupants in their inside world to fulfill a physical, physiological or psychological need. Needs represent the physical and non-physical requirements of the occupant's inside world that must be met in order to ensure the satisfaction of the occupant with their environment. Actions are the interactions with systems or activities that an occupant can conduct to achieve environmental comfort. Actions connect occupants' inside-world needs with the environmental outside word. Systems refer to the equipment or mechanisms within the building outside world with which an occupant may interact to restore or maintain environmental comfort. As an example of the DNAs

### Drivers
- Building
- Occupant
- Environment
- System
- Time

### Needs

### Actions

### Systems

## Discussion

### What types of behavior are accounted for in the DNAs framework?
- Interactions between occupants and building systems can have a dramatic impact on global building performance in terms of comfort (thermal, visual, acoustical, IAQ), energy loads (heating, cooling, ventilation, lighting, plug-loads, electricity peak loads), technology efficiency, operational costs and occupant productivity.

### Why a framework to standardize the representation of energy-related behavior in buildings?
- The goal of the DNAs framework is to provide an ontology of energy-related occupant behavior in buildings to solve discrepancy issues mostly rooted in: (a) oversimplifying or ignoring human behavior in the building design and operation process, (b) a broken interface between human behavior and building system controls and, (c) lack of reliable technology and system controls performance.

### Which building types can be addressed when adopting the proposed ontology?
- Occupant behavior has been shown to have a profound impact on the energy performance of both residential and commercial buildings

### Who can use the DNAs framework, for what purposes and to what extent?
- The DNAs framework will be used to address issues held by building energy modelers, building designers, building engineers, building operators and managers, building utilities, and policy makers.

### When can the DNAs framework be used?
- The DNAs framework can benefit building energy performance during the whole building life cycle, including the design, operation, management and retrofit phases. During the design phase, the DNAs framework allows for more accurate prediction of actual building energy use.

### How can energy-related behavior be represented using the DNAs framework?
- The different applications of the described ontology aim to overcome some unbridged gaps in methods, models, and simulation tools, to represent the impact of energy-related occupant behavior on whole-building energy performance.
- The DNAs framework provides a cohesive ontology that can advance modeling methods specific to energy-related occupant behavior in buildings. Lastly, there is no common consensus as to the most effective tool to use to develop reliable behavioral simulations.
- The applicability and interoperability of these models are still affected by local disparities, coding languages and design issues.
- The proposed DNAs framework is intended to be integrated into current building energy modeling programs like EnergyPlus and other domains (ESP-r, TRNSYS, IDA ICE, DeST, DOE-2, etc.) or Functional Mock-up Interfaces (FMI) to support both model exchange and co-simulation of dynamic models using a combination of xml-files and compiled codes, within the structure of the XML Schema.

## Conclusion
- The DNAs framework described in this study presents an ontology providing a common technical language for the building simulation community to observe, model, and simulate energy-related occupant behavior in buildings.
- The drivers behind the occupant behavior that influence the energy performance of buildings; the needs of the occupants which must be met in order for the occupants to be comfortable and satisfied with their environment; the actions which occupants can take in order to satisfy their needs; and the building systems with which occupants can interact to perform the actions which affect building energy performance.
- The field of building occupant behavior modeling suffers from a lack of standardization in methods, models and simulations.
- The aim is to provide more robust descriptions of the motivations driving occupants to interact with the building envelope and building systems, in order to bring about desired comfort conditions.
- The framework is to allow the incorporation of more accurate behavioral models into building simulation tools to provide comparable metrics and results on: 1) the behavioral factors that impact building energy performance, 2) the potential energy savings from improved occupant behavior in buildings, and 3) the design of robust building operation scenarios, technologies, systems and retrofit strategies.
- The deployment of the DNAs framework and the obXML schema into current modeling practices must then face some of the intrinsic constraints of human behavior simulation in buildings
