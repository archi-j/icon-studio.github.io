---
layout: post
title: "[Paper Reading] Occupant behavior models: A critical review of implementation and representation approaches in building performance simulation programs"
date: 2022-12-23 09:00:00 +0300
description: "2018_Occupant behavior models: A critical review of implementation and representation approaches in building performance simulation programs" # Add post description (optional)
img: 20221223_post_main.jpg # Add image post (optional) 280px, 350px, 470px, 700px, 940px
fig-caption: # Add figcaption (optional)
category: [PR]
tags: [Occupant Behavior, Building Performance Simulation, Review]
---

**Publication year:** 2018 <br>
**Authors:** Tianzhen Hong, Yixing Chen, Zsofia Belafi1, and Simona D’Oca<br>

## Introduction
- Occupant behavior (OB) in buildings refers to occupants’ presence and movement, and interactions with building systems that have an impact on building performance (thermal, visual, acoustic, and indoor air quality). The interactions include adjusting thermostat settings, opening or closing windows, dimming or turning on/off lights, pulling up or down window blinds, switching on or off plug loads, and consuming domestic hot water.
- Clearly, understanding and accurately modeling OB in buildings are crucial to reducing the gap between design and actual building energy performance, especially for low-energy buildings relying more on passive design features, occupant-controlled technologies, and occupant engagement.
- Presently, there is a significant disagreement between simulated results and actual building energy consumption, Discrepancies mainly arise from a lack of quantitative research truthfully representing energy-related OB in buildings.
- Advances in BPS over the last decades envisioned a switch from a deterministic approach to a stochastic approach in considering OB in buildings. Traditionally, OB is represented as oversimplified and predefined deterministic or static schedules or fixed settings and rules which are input into BPS programs resulting in deterministic and homogeneous results—ignoring the stochastic nature, dynamics, and diversity of OB.
- Probabilistic models of behavior can be derived from historical data of the indoor and outdoor environment conditions (e.g., air temperature and relative humidity, illuminance levels, CO2 concentration), occupancy presence and movements, and the operating conditions of the building systems. Through the machine learning process, the correlations can be established between some observed physical or situational environmental conditions and the observed human-building interaction.
- OB models are developed as probabilistic regression equations based on independent variables and metrics. The selection of different influencing variables for similar OB models makes it difficult to compare the models and incorporate them into BPS programs.
- A recent review of modeling and simulation approaches for OB in buildings discussed the problem of transferability of occupant models developed based on a selected observation study to different building models.
- This study critically reviewed approaches to the implementation and representation of OB models in eight popular BPS programs among the engineering and simulation community. Approaches to modeling occupant behavior have been reviewed (Yan et al. 2015), such as (1) Average value models (deterministic), Bernoulli models, Survival models, and agent-based models are used to predict state, and (2) Markov models and Survival models are used to predict events (state-transitions).

## Implementation of OB models in BPS programs
- The implementation of OB models in BPS programs, in this context, refers to simulation users or energy modelers choosing certain approaches and preparing inputs for the OB models to be included as part of a building energy model using a particular BPS program.
- For example, a deterministic occupant-driven control would determine occupant actions based on indoor and/or outdoor environmental conditions using a deterministic correlation function. On the other hand, a stochastic OB model is related to occupants performing specific actions with a probability related to environmental conditions (e.g., occupants feeling hot and opening a window) or events (e.g., entering or leaving a space).

### Four implementation approaches of OB models
- Direct input or control
  - The direct input or control approach defines occupant-related inputs using BPS program semantics—just as other model inputs (building geometry, constructions, internal heat gains, and HVAC systems) are defined.
  - In this approach, the user defines and inputs temporal schedules for thermostat settings (cooling and heating temperature set points), occupants, lighting, plug loads, and the HVAC system.
  - The direct input or control approach requires users to pre-calculate the schedules based on the correlations between the environmental conditions and the occupant actions of the OB models
  - It is a challenge, especially when some dynamic indoor parameters (i.e., air temperature) are used in both sides of the correlation function (e.g., turn on or off air conditioners when feeling hot or cold). Static set points (i.e., temperature set point) are typically used as an approximate to determine the occupant actions and generate the schedules in this approach, which may reduce OB model accuracy.
- Built-in OB models
  - The second method is to use the OB models already implemented in the BPS programs. The built-in OB models approach provides a simple way to model the specific OB models; however, currently, there are only limited built-in OB models in few BPS programs, which affects the flexibility of this approach.
- User function or custom code
  - the user can write functions or custom code, as part of a building energy model input file, to implement new building operation and supervisory controls or to overwrite existing or default ones
  - This approach provides flexibility by enabling users to change how a BPS program simulates a building energy model without having to recompile the source code of a BPS program. This approach allows both deterministic and stochastic OB models using built-in or user-defined stochastic mathematical functions.
- Co-Simulation
  - Co-simulation is a simulation methodology that allows distinct components to be simulated by different simulation tools running simultaneously and switching information in a combined routine
### Which implementation approach to choose for different OB model types
- Modelers may also choose to implement a data-driven deterministic control logic or customized code for the specific purpose of the simulation study.
- Probabilistic models typically are implemented as user functions or customized codes, or in a dedicated co-simulation environment.
- Overall the direct input or control is the approach most frequently used by most simulation users. The built-in OB models approach is limited to a few BPS programs (e.g., DeST and ESP-r). The user function approach is also limited to a few BPS programs (e.g., EnergyPlus, DOE-2, IDA ICE, and TRNSYS). The co-simulation approach is emerging as a more robust and interoperable approach to simulating OB, as more BPS programs (e.g., EnergyPlus and ESP-r) are adopting this approach.
### The implementation approaches used in the eight BPS programs
- The direct input or control approach is implemented in all eight BPS programs. The other three approaches show significant diversity within the BPS programs. Currently, EnergyPlus and ESP-r support co-simulation. Only DeST and ESP-r provide built-in OB models. User function or custom code is supported in EnergyPlus, DOE-2, IDA ICE, and TRNSYS.
### Strengths and weaknesses of the implementation approaches
- Strengths and weaknesses of each of the implementation approaches are discussed as follows, using four qualitative metrics
  - Ease of implementation or application refers to the degree of knowledge required from the modeler to implement the OB model into the BPS environments.
  - Flexibility is an indicator of the capability of the implementation approach to cover different control logics or model types.
  - Reusability hinges on the capability of one implementation approach to reiterate OB models for different uses, studies, or purposes.
  - Accuracy invokes the extent to which the simulation outcomes derived from the OB models implementation conform to the actual measurements or benchmark.
- The direct input or control approach is straightforward to implement and easy to use. Because of this reason, this implementation approach emerges today as the most commonly used among the engineering community. However, it is limited in terms of OB model representation, since the specific BPS program’s semantics for input determine a lack of reusability among simulation tools. Further, direct input or control approach has low flexibility because it is usually not robust enough to represent complex logics or algorithms for certain OB models.
- With the built-in OB models approach, OB results more flexibly represented with a good degree of ease of implementation. However, one of the drawbacks of this implementation approach is that users cannot create new types (equation forms or new input variables) of OB models or use new algorithms for the built-in OB models. Moreover, users can only choose those OB models that are already embedded in the simulation tool—hindering reusability of models and accuracy of simulation results.
- Regarding ease of implementation, the user-customized code and functions approach usually requires advanced user experience and deep knowledge of a particular BPS program to use such features correctly and efficiently. Another limitation—which hinders usability and reusability—is that most BPS programs are supporting user-written code that lacks a comprehensive debugging mechanism.
- The co-simulation approach provides the maximum flexibility regarding implementation of complex OB models in a separate software module that is independent of and interoperable with BPS programs. One unique requirement is that BPS programs have to implement FMI to support the co-simulation feature. Developing and testing OB models in FMUs for co-simulation also requires detailed knowledge of FMU and FMI, which are factors hindering the ease of implementation and the usability among modelers in the engineering and simulation community
### Application of OB models with BPS programs
- For stochastic OB models in BPS programs, the simulation process consists of three main steps. First, the OB model is implemented as probabilistic inputs of the BPS programs, according to one of the four selected approaches (direct input, built-in model, user function or custom code, and co-simulation).
- The simulation is then run a set of times (i.e., 20 or 100 times) with the BPS programs. For each run the simulated probability of behavior is paired with a uniformly distributed set of generated random numbers to determine the actual behavior condition—i.e., a space being occupied or an adaptive action being performed.
- The complexity of the OB simulation process, from the selection of the most appropriate model and approach to the choice of the most suitable application into a BPS program, can lead to the dangerous possibility of misleading simulation results.
## Representation of OB models in BPS programs
- OB models are currently represented using either the specific syntax of particular BPS programs or a common semantic data model, e.g., in the form of XML (eXtensible Markup Language)
### Specific input semantics in BPS programs
- The eight BPS programs use their syntax to represent OB models in either ASCII text format or binary format
### The IFC data models
- The IFC is an open and neutral ISO-certified (according to ISO 16739:2013) standard format for Building Information Modeling (BIM) data.The IFC data format has been used over the last 20 years to represent data models having different natures and domains.
- IFC never gained momentum among the simulation community due to its complexity and lack of human-and-machine readability. To partially overcome this drawback, since 2004, the XML-based ifcXML schema has been regulated by the international standard ISO 10303-28.
- Despite its enabling data transferability capacity, the ifcXML is only partially diffused in practice, due to the large size of typical ifcXML building model (an ifcXML file dimension is usually 300%–400% greater than that of an IFC file). At the current stage of development, IFC file format has not been used to represent any OB models.
### The XML-based data models
- The XML language has the great advantage of being a neutral exchange language able to represent data and models in a way that can easily be integrated into a diverse software environment. In the field of building engineering, several existing standards, and data models make use of the XML data format and structure to describe data content from heterogeneous sources among applications of the same software
- The gbXML’s primary goal was to enable the transmission of building information stored in CAD building models. By doing so, the gbXML aims to enable a two-way integrated interoperability and communication between a broad range of design and engineers’ building models. The gbXML has the advantage of representing one of the most widespread standard schemas for data standardization and exchange among the BPS programs.
- The purpose of the XML representation of OB data and models is to enable the international research community to access a unified schema that represents the OB phenomena in the built environment at a large scale. The obXML schema is grounded on an ontology of energy-related behavior in buildings integrally embedded into a DNAS framework. The topology of the DNAS framework was implemented in the obXML schema based on the main root element OccupantBehavior branching into five sub-elements: (1) Behaviors, (2) Buildings, (3) Occupants, (4) Seasons, and (5) TimeofDay
- The FMI is an independent standard that allows for component development and tool coupling, using a combination of XML and compiled C code. The FMI standard encompasses two main issues. First, it provides an explanation of how a modeling environment can generate C code and be utilized. Second, it technically describes the interface standard for coupling in a co-simulation environment
### Strengths and weaknesses of the representation approaches
- The text- or binary-based representation of OB models in BPS programs does not require separate semantics to describe OB models. However, it is subject to the limitations of inherent input semantics of each BPS program
- OB models coded for a specific BPS program cannot be reused by other BPS programs. It is also difficult for these models to share with users of the same BPS program as they are embedded and scattered in the whole input file of a building energy model.
- XML-based OB model representation, although requiring the use of an XML schema, provides more flexibility for users to develop their OB models that can be shared with a wide community of users and multiple BPS programs.

## Discussion
- First, to capture the complexity of OB models and to quantify their impact on building performance, a common semantic approach to representing OB models—one that can be shared with different building performance simulation programs is critical.
- Second, such common OB model protocol must overcome weaknesses of actual implementation and representation approaches
- as a general remark, despite the selected approach to implementing and representing behavior models in BPS programs, researchers conducting occupant behavior studies tend to have backgrounds in engineering and architecture.

## Conclusions
- A common occupant behavior data model implemented in the form of XML, JSON, or YAML is needed to provide a standardized representation of OB models, enabling their exchange between different BPS programs.
- A modular software implementation of OB models, such as functional mock-up units for co-simulation, adopting the standardized data model of occupant behavior, has advantages in providing a robust and interoperable integration with multiple BPS programs.
- The common data model representation and the co-simulation implementation approaches help standardize the input structures of OB models, enable collaborative development of a shared library of OB models, and allow for rapid and widespread integration of OB models in various BPS programs among the engineering and research community as a whole.
