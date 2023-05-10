---
layout: post
title: "[Paper Reading] Rethinking the role of occupant behavior in building energy performance: A review"
date: 2023-05-08 09:00:00 +0300
description: "2018_Rethinking the role of occupant behavior in building energy performance: A review" # Add post description (optional)
img: 20230508_post_main.jpg # Add image post (optional) 280px, 350px, 470px, 700px, 940px
fig-caption: # Add figcaption (optional)
category: [PR]
tags: [Occupant Behavior, Building Energy, Review]
---

**Publication year:** 2018 <br>
**Authors:** Yan Zhang, Xuemei Bai, Franklin P. Mills, John C.V. Pezzey<br>

## Introduction
- The building sector accounted for nearly 40% of total global energy use and 33% of total GHG emissions in 2016, which would be even greater if the embodied energy use and related emissions are taken into account for the whole life cycle of buildings
- Energy consumption from buildings and activities in buildings is projected to increase by an average of 1.5% per year for the period of 2012–2040 under a business as usual scenario, and may double or even triple by 2050 from the level of 2010
- More and more researchers have come to realize the importance of occupant behavior in building energy performance, identifying occupant behavior as the main cause of the ineffectiveness of technology solutions and the unrealized savings of energy consumption in buildings.
- To date, the studies looking at occupant behavior and building energy performance mostly investigate into one or two specific kinds of energy-related behavior in one building or area. In addition, although researchers from different disciplines have delved into occupant behavior and energy use in buildings, often without common language, the findings usually lack comparability and are difficult to generalize beyond the specific context for each study. Thus, it is difficult to grasp a holistic understanding of occupant behavior and its impact on building energy performance.
- Specifically, these questions remain unanswered:
  1. What is the state-of-the-art understanding of occupant behavior in relation to energy use in buildings?
  2. How has the research evolved and what are the hot topics and research gaps?
  3. What kind of methodologies have been used for research?
  4. What is the range of energy saving potential of occupant behavior?

## Research landscape of occupant behavior and building energy performance
- Research on occupant behavior and building energy performance can be divided into five clusters, based on research purpose:
  1. One is to understand the environmental psychology of occupants by identifying and assessing the key factors that influence the energy-related behavior of building occupants. In this context, occupant behavior is viewed as a bridge or link between key influential factors and typical energy consumption patterns.
  2. The second cluster is about developing and testing intervention strategies and methods to reduce energy use. Information intervention appears to be an effective strategy that has been widely studied and applied across the world
  3. The third cluster is about characterizing occupant attitudes and assessing the effectiveness of energy policies. A key finding is the need to integrate occupant behavior into the current policy framework for building energy efficiency. Although installation of more energy efficient equipment is a common policy, increasing occupants’ awareness of energy-related behavior and thereby change their behavior is more cost-effective
  4. The fourth cluster focuses on evaluating the effectiveness of energy efficient technology and building design. This cluster of research uses occupant behavior models as an input when predicting the expected energy performance of building designs
  5. The last cluster has been developing predictive, quantitative models of occupant energy-related behavior. The significant gaps that have been identified between expected and actual energy consumption in many experiments suggest significant improvements are needed to understand the impact of occupant behavior on energy use.

## Understanding of energy-related occupant behavior
- A lack of understanding of energy-related occupant behavior (hereafter, occupant behavior) in buildings has long been one significant hindrance to improving building energy performance
- The International Energy Agency (IEA) in one of their reports attempted to define energy-related occupant behavior as “observable actions or reactions of a person in response to external or internal stimuli, or respectively actions or reactions of a person to adapt to ambient environmental conditions such as temperatures, indoor air quality and sunlight”
- Considering the complex and stochastic characteristics of occupant behavior, Chen et al. developed a three level system of definitions of occupant behavior for different research purposes in residential buildings:
  1. A simple-level definition with several parameters regarding the schedule of occupancy and domestic appliances for statistical analysis
  2. An intermediate-level definition with additional parameters about the set points of appliances and the operation schedule for case studies
  3. A complex-level definition with descriptions on the schedule, set points and control rules of three types of occupant behavior, i.e. occupancy, appliance operation, and window/shading operation, for detailed diagnostics/simulations of building energy performance.
- A substantial portion of the literature examined the occupant behavior in buildings with a particular focus on one or two specific types of behavior. Window opening behavior is one kind of energy-related behavior that has been widely discussed in studies.
- Apart from the window opening behavior, lighting control behavior also obtained exclusive attention from some researchers.
- Another type of behavior that has been frequently discussed is space heating/cooling behavior. This is largely because the energy use associated with space heating and cooling significantly contributes to the total final energy use of buildings, both residential and commercial (up to 73% in some cases, on average 34% and 40% in residential and commercial buildings, respectively)

## Research methods and data collection techniques
- Occupant behavior is complex and stochastic in nature and it is hard to accurately describe or predict in the context of building energy performance. A rather common technical framework of research can be identified, which is used in many studies on occupant behavior and building energy performance. The initial step of research is data collection of occupant behavior and other relevant variables, together with modeling of occupant behavior.
- Data on occupant behavior are generally acquired through two main approaches one is monitoring equipment installed within buildings (i.e. monitoring methods), and the other is depending on reports from occupants themselves (i.e. self-reports).
  - Typical monitoring methods include ultrasonic and passive infrared detection, CO2 sensors, camera-based technologies, and wireless network based systems.
    - e.g., Cameras and passive infrared (PIR) sensors, Wireless Sensor Networks (WSN), weather stations, meters for electricity and gas, radio-frequency identification (RFID), ultra-wideband (UWB), Wi-Fi and customized sensors
    - Pros: it can provide data with finer granularity.
    - Cons: Monitoring methods require both the installation of devices, such as sensors and meters, and the involvement of technical experts, which may incur significant costs and take a long period of time.
  - Reports from occupants usually encompass information and concerned details on occupants and their behaviors, and probably involve energy consumption and energy bills of buildings when the objective of research is to examine the effect of specific behavior on building energy consumption.
    - Pros: self-reports from occupants are easier to carry out, using either questionnaires or other survey tools, without large investments of money and experts’ knowledge.
    - Cons: a mismatch may emerge between actual and reported information when self-reports are used for analysis, which may affect the accuracy of the conclusions.

## Quantitative modeling of occupant behavior and building energy performance
- Occupant behavior can be represented quantitatively at a certain level, despite its stochastic and complex nature, by means of mathematical models. Occupant behavior can thus be integrated into building energy performance simulation and modeling to capture its impacts on energy and environmental performance of buildings

### Stochastic/probabilistic modeling
- Stochastic/probabilistic models capture and describe the probability that specific behavior occurs based on historical or statistical data
- Generally, there are three types of stochastic/probabilistic occupant behavior models commonly used: Markov chain models, Bernoulli process, and survival analysis.
- These models have been widely used to represent both occupancy and the actions occupants take to control their indoor environment.
- Due to the randomness and variability of occupant behavior, stochastic models are better in terms of validity and applicability for describing the actual interaction between occupants and building systems than deterministic models.

### Statistical methods
- Statistical methods are generally carried out by building numerical relationship between occupant behavior and indoor/outdoor environment conditions, electricity usage or time periods, with the results being expressed by occupancy state or the probability of studied behavior
- Statistical methods can better capture and describe occupant behavior in reality, but they require a larger sample size and data input of many variables, which could lead to a higher cost of field studies.

### Agent-based modeling
- Agent-based modeling (ABM) uses multi-agent systems, comprised of autonomous agents, to simulate agents’ interactions with each other and their external environments under specified rules. The rules are critical to the simulation as they define how agents interact with each other and their environment.
- Despite some improvements in the methodology of ABM, more comprehensive and holistic models are needed for further research in future.

### Data-mining approaches
- Data-mining has been used in many recent studies on occupant behavior. They require large databases and huge data storage. The application of data-mining to modeling occupant behavior follows its increasing use in studies of building energy performance as large volumes of data on building energy use and the energy consumed by specific appliances in buildings have become available.
- While a high level of accuracy of behavior pattern prediction can be achieved, the application of this category of methods has been limited to occupancy and appliance use in residential buildings, possibly as a result of insufficient data and restricted access to other behavior and energy use data.
- Data mining approaches are intended to overcome the shortcomings of the aforementioned traditional methods, particularly when dealing with big data streams, by offering reliable models of occupant behavior with the potential for rapid analysis and high replication

## Research gaps

### Occupant behavior needs to be understood within a systematic framework of research
- To date, research on occupant behavior seems to have focused on several specific behaviors, such as window opening behavior, lighting control behavior and space heating/cooling, with few studies including all relevant kinds of occupant behavior into the scope of research.
- Meanwhile, some studies estimated the energy-saving potential from behavioral change, but often focusing on one or two particular types of energy-related behavior, making it difficult to compare results and findings across case studies. This might lead to an underestimation of the overall impact of occupant behavior on building energy performance.
- Additionally, a systematic framework will enable researchers to model and capture the interaction between occupants and building energy systems from different perspectives with a unified evaluation system.

### Empirical evidence and data at a larger city scale are needed
- A significant shortcoming of occupant behavior research is that there are few data on behavior profiles and energy use in real-world buildings. In order to improve outcomes of simulation models, sufficient empirical data are needed to adjust and validate the modeling techniques.
- Empirical evidence and data are critical to occupant behavior and building energy performance research and more field surveys should be conducted to enhance existing studies as well as facilitate further analysis in this field.
- Understanding building energy performance beyond individual buildings and at a larger city scale is important for city scale policy making and implementation. However, based on our dataset of literature, little research explores occupant behavior in association with building energy performance at such scale.

### Occupant behavior needs to be understood in the context of socio-economic status and energy policy
- Much of the literature on simulation and modeling of occupant behavior puts almost exclusive focus on connecting occupant behavior with natural environmental factors, building characteristics and personal profiles, and largely leaving out the potential impact of socio-economic status.
- Evidence has shown that behavior-based policies (such as energy use feedback programs) could reduce household energy consumption with little financial investment by either governments or households
- Demographics and motivations of people in different contexts also have to be included in the policy-making of intervention programs for energy efficient behavior.

### The role of occupant behavior in the effectiveness of building energy efficiency policy remains unclear
- Building energy efficiency policy and its outcome is complex and multifaceted. Its effectiveness can be influenced by various factors such as response of the target group to policy, the conditions of stakeholders, the design and implementation process of policy, etcetera.

## Conclusions
- This paper identified the hot topics, overall research trends, and remaining research gaps by means of bibliometric analysis and in-depth review of literature to date.
- Four hot-topic research areas have been identified: 
  1. understanding of occupant behavior, especially specific behaviors affecting indoor thermal comfort, such as window opening behavior, lighting control behavior and space heating/cooling behavior
  2. research methods and energy data collection
  3. quantitative modeling of occupant behavior and building energy performance
  4. energy saving potential and behavioral strategies.
- The energy-saving potential of occupant behavior in building energy performance ranges between 10%−25% for residential buildings, and 5%−30% for commercial buildings.
