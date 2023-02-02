---
layout: post
title: "[Paper Reading] The impact of occupants’ behaviours on building energy analysis: A research review"
date: 2023-02-02 09:00:00 +0300
description: "2017_The impact of occupants’ behaviours on building energy analysis: A research review" # Add post description (optional)
img: 20230202_post_main.jpg # Add image post (optional) 280px, 350px, 470px, 700px, 940px
fig-caption: # Add figcaption (optional)
category: [PR]
tags: [Occupant Behavior, Behavioral Model, Review]
---

**Publication year:** 2017 <br>
**Authors:** Elham Delzendeh, Song Wu, Angela Lee, Ying Zhou<br>

## Introduction
- Government, businesses and wider society all have a pivotal role to address human impact (hence, occupant behaviour) on the environment. In this regard, predicting energy demand is becoming more important in the design and construction of buildings, from early design stages to post occupancy.
- Energy consumption of buildings is related to various factors including: the thermo-physical properties of the building elements, its construction technical details (energy-efficient building elements may not perform efficiently if poorly-constructed), climatic location characteristics, the quality (and maintenance) of the installed HVAC system, and occupants’ behaviour and activities towards energy utilization.
- The studies demonstrated that the actual energy consumption of buildings is sometimes up to 3 times greater than the estimated calculation. Thus, this performance gap is due to the difference between the building design and the as-built building in terms of the technical workmanship and installations, choice of equipment and material during the construction stage, and the energy behaviour of occupants, which has been disregarded in the energy simulation process.
- They concluded that human behaviour and occupant preferences as an important contributor of the gap between the predicted and actual building energy performance.
- Occupants’ behaviour as the most overlooked parameter that “might not be considered as part of the energy design” within the chain of design, construction, operation and maintenance.
- This paper aims to undertake a comprehensive review of existing studies in this area to identify research trends and gaps for future studies.

## Method and materials
### Occupant behaviour
- Occupant behaviour refers to the interaction with building systems in order to control the indoor environment for health, and to obtain thermal, visual and acoustic comfort inside buildings.
- PMV models integrate the impacts of temperature (air temperature and mean radiant temperature), humidity, air velocity, the metabolic heat rate and clothing thermal properties to predict the thermal comfort level.
- Occupants interact with control systems and building elements to reach their own personal desired level of comfort in different ways: use of building openings (e.g. opening and closing windows), use of lighting and controlling solar shading (e.g. adjusting blinds), use of HVAC systems (e.g. turning airconditioning on or off and adjusting thermostat temperature), use of hot water and electrical appliances.
- Thus, occupants profiling based on their energy behaviours could lead to more accurate assumptions in the energy analysis of buildings. However, a large-scale comprehensive study with significant quantitative data is needed to produce reliable energy profiles, which is presently not available.
- However, the calculation of the influence of an open window on building energy consumption requires complex air movement considerations that are not effectively accomplished in any of the existing studies.
- Use of hot water might have critical influence on the total energy consumption of a building; however, this requires further investigation to be conclusive.
- Studies on the inter-relationship between various energy behaviours of occupants are useful but currently limited and further analysis is much needed.
- Several studies have demonstrated that the consequences of occupants’ behaviours significantly increase the total energy consumption of buildings during non-working and unoccupied hours
- Human behaviour is a complex phenomenon; therefore, most human behaviour studies adopted probabilistic methods.
### Parameters influencing occupants’ energy behaviour
- Climatic (environmental, physical)
  - e.g., outdoor temperature, relative humidity, solar radiation, wind and rain.
  - If the room temperature increased gradually, more and more occupants would feel too warm and would open their windows.
  - These parameters are time/ date dependant, therefore, in many studies stochastic models are used to estimate the probability of potential outcomes.
- Building types (or type of activities)
  - The building type determines the type of activity, clothing type, production of metabolic heat, together with the occupants’ specific needs and expectations and their possible degree of interactions with building systems.
  - Some studies have investigated commercial and educational buildings with limited findings. There have been sparse studies undertaken on other public building types such as exhibitions and health centres.
- Social and personal (psychological and physiological)
  - e.g., users’ awareness of energy issues, gender, age, employment, family size and socio-cultural belonging, education and awareness-raising on people's energy attitude
  - Unfortunately, there is little evidence to suggest that the findings have been incorporated into building energy assessment tools. The authors believe that a multi-disciplinary approach is needed to bring together social scientists, energy modellers and construction engineers to tackle this complex problem
  - more detailed quantitative studies governing the sociology aspects of occupants’ behaviours are suggested as necessary by some scholars, which is essential to improve the accuracy of energy consumption predictions in buildings.
- Energy regulation and economical Parameters
  - e.g., energy price and employment
  - When occupants are directly responsible for pay energy bills they act more energy frugal
  - More than half of the respondents to their questionnaire indicated that energy costs as the main reason for avoiding the use of mechanical fans and accepting some level of discomfort.
  - Low-income occupants consumed more electricity for cooling in comparison to other households due to the inadequate thermal insulation of the buildings.
- State of occupants
  - e.g., arrival, presence in the space and departure
  - Occupants tended to adjust building systems and appliances more at arrival than at departure of a building.
- Architecture and interior design features
  - “sustainable interior design” describes the integration of sustainability principles in the interior design of space as part of building construction
  - The interior design of space can influence occupant behaviour in differing ways, including: visual quality of building openings (windows and doors), the architecture circulation and colours, material and compositions of interior spaces which may change occupants’ thermal perception
  - future research could extend to the urban design scale as the understanding of the impact of occupants’ energy behaviours on energy consumption on a larger scale improves the credibility of energy consumption policies made using more realistic data.
### Occupancy factor in energy simulation
- Energy simulation of a building is a mathematical analysis of the physical properties of the building elements, considering thermal and lighting aspects
- Current energy simulation engines such as TRNSYS, ESP-r, IES Virtual Environment or EnergyPlus, follow an almost similar procedure to calculate energy consumption in buildings. The final outputs are heating/ cooling/ ventilation design data, lighting data, CO2 emission, the total energy consumption and cost.
- Occupancy information in energy simulation tools
  - DesignBuilder: occupancy (to modify the density of people within each zone), activity factor, gender adjustments, clothing and use of computer and other equipment.
  - EcoDesigne: less occupancy inputs including occupant's presence schedule and type of activity that determines the human heat gain.
  - Autodesk Revit: limited to occupancy schedules
- Occupant's impact on building energy consumption is only considered in the occupancy section of energy simulation software. Input data regarding occupancy in energy simulation software is limited to occupants’ presence in fixed and scheduled patterns, and these do not reflect reality
- This research project and other similar studies, demonstrated that by neglecting occupants’ interactions with building systems in building energy calculations leads to inaccuracies.
- The consensus from researchers is that behavioural parameters should be fully incorporated into energy simulation tools in order to provide more accurate energy predictions

## Conclusion: current research limitations and recommendations for future studies
- Numerous studies have investigated the impact of occupants on the energy consumption in buildings with the need to reduce the performance gap between the predicted and actual energy consumption of buildings.
- There is an inherent demand for energy modellers, researchers and designers to improve the calculation of energy consumption of buildings by considering energy behaviour of occupants.
- Occupants’ motivations and reasons, and the various factors influencing their decisions to interact with building systems together, with the impacts of their actions on the total energy consumption of buildings, have to be studied in a multi-disciplinary approach to incorporate the factors from a sociology, psychology, economics, engineering and design perspectives.
- This paper reviewed more than 100 publications related to occupant energy behaviour in buildings. A summary of the key findings are:
  - Fewer number of studies have analysed commercial and educational buildings, while, some building types such as exhibitions, recreational and healthcare facilities have been given sparse attention and require further analysis.
  - Urban scale impact has not been investigated adequately, forming a highly recommended area for future research. The impact of interior design in terms of space layout, fixtures and fittings on occupants’ action scenarios, thermal perceptions, and consequently on their energy behaviour has been overlooked and requires further investigation.
  - The most recent behavioural methodologies suggest the consideration of not only the individual and personal characteristics of occupants, but also the particular features of their social context. However, only 10% of the reviewed papers have focused on both social and personal (socio-personal) factors
  - Some areas, such as the use of hot water has a significant impact on energy consumption in some building types (e.g. residential), have received scant attention in comparison but are considered to have a likely impact on energy use. Furthermore, future investigations about the inter-relationship between different energy behaviours of occupants are needed, which will generate more realistic assumptions in building energy predictions.
  - The findings, at present, have yet to offer significant improvements in predicting occupants’ energy behaviour in buildings. Particularly, the translation and integration of the findings of these studies into building energy simulation tools to reduce the gap between predicted and actual energy consumption in buildings still remain a significant research challenge in this area.
