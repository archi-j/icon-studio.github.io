---
layout: post
title: "[Paper Reading] BIM-supported sensor placement optimization based on genetic algorithm for multi-zone thermal comfort and IAQ monitoring"
date: 2022-03-28 09:00:00 +0300
description: 2022_BIM-supported sensor placement optimization based on genetic algorithm for multi-zone thermal comfort and IAQ monitoring # Add post description (optional)
img: 20220328_post_main.jpg # Add image post (optional) 280px, 350px, 470px, 700px, 940px
fig-caption: # Add figcaption (optional)
category: [PR]
tags: [BIM, IoT, Reading]
---

**Publication year:** 2022 <br>
**Authors:** Jack C.P.Cheng, Helen H.L.Kwok, Alison T.Y.Li, Jimmy C.K.Tong, Alexis K.H.Lau <br>
**DOI:** [https://doi.org/10.1016/j.buildenv.2022.108997](https://doi.org/10.1016/j.buildenv.2022.108997)


## Introduction
- Most of the previous studies are conducted in a single room. However, the rooms are connected with each other in multi-zone environments, such as an office floor [8]. Temperature and CO2 concentration distribution vary in different regions in a multi-zone environment. The layout and setting of a mechanical ventilation and air conditioning (MVAC) system contribute to these variations and may spread the impact to adjacent regions. Studying a multi-zone environment is therefore crucial for considering the MVAC system of the floor as a whole in IAQ monitoring.
- Since tenant areas on a typical office floor are usually rented to different companies with different rental terms, variations in room partitions, layouts and occupancy inside tenant areas are significant as renovations are performed by these tenants when they move into the tenant areas. After the sensors are installed, it is difficult for the facility manager of the building to change sensor placements as this may disrupt the business operations of the tenants. An approach to generate sensor placement considering different seasonal factors, ventilation system settings and occupancy is needed.
- With the aid of IoT technology, CFD simulations were conducted to evaluate the thermal comfort of an indoor environment. By coupling CFD simulations and wireless sensor measurement, the CFD model is validated with sensor data and the predicted mean vote value of the model room was estimated.
- The purpose of this study is to develop a methodology to optimize temperature and CO2 sensor placement for thermal comfort and IAQ monitoring in a multi-zone environment, with consideration of different scenarios.
- This study illustrated how BIM technology was adopted to support a sensor placement program that uses CFD simulations and machine learning for sensor placement optimization. BIM technology helps to create accurate geometry for multi-zone CFD simulations, and the mesh created can be used to support sensor placement.

## Methodology
- This study proposed the methodology as shown in Fig. 1 to optimize sensor placement on a typical office floor. The BIM model of the studied floor was first created to provide geometric information for CFD simulations. The CFD simulations were validated with field measurement results.
- Based on the validated model, a scenario study was conducted to estimate temperature and CO2 concentration distributions on the floor under different seasons, MVAC system settings and occupancy cases. The CFD results and the floor mesh were then imported into the sensor placement program to create optimal sensor placement for each scenario. To evaluate the generated sensor placements, they were checked whether the sensors were accurately placed such that significant changes in temperature and CO2 concentration on the floor can be monitored.
- The significant changes are defined based on the simulated results from the scenario study. The simulated results under different seasons, MVAC system settings and occupancy cases were used to quantify the impact on temperature and CO2 concentration. The use of relative differences makes the proposed methodology easier to be applied in other buildings as the ventilation settings.
- BIM-based CFD simulations for scenario study
  - BIM technology was adopted to provide geometric information for CFD simulation. To represent the studied building environment accurately, the BIM model consists of building components such as walls, floors, ceilings, curtain walls and doors.
  - Moreover, an indoor airflow CFD simulation requires inlets, outlets, heat sources and studied air pollutant emitters. The BIM model therefore includes air diffusers, occupants and any other heat or air pollutant sources that exist in the studied region.
- Sensor placement using machine learning
  - To optimize sensor placement under different scenarios, machine learning algorithms were implemented with CFD results and mesh as inputs. To obtain the optimal sensor placement strategy, the solution sets undergo filtering, synchronization, crossover and mutation process in each iteration.
  - Value Encoding is used in this study. Every chromosome is a solution set that consists of 3D coordinates of all the sensors to be placed in the studied indoor environment. Multiple random solution sets of the sensor positions were initially selected from the mesh of the validated CFD model.
  - The sensors which are close to regions with significant percentage differences in simulated results are preferred. To identify these regions, weight k-nearest neighbor is applied to identify the first k closest points to the coordinates of sensor placement.
  - To generate children for the next iteration, uniform crossover is implemented as genes are randomly copied from the first or the second parent. Each gene is the 3D coordinates of a sensor and is chosen from either parent with equal probability.
- Sensor placement optimization

<img src="https://ars.els-cdn.com/content/image/1-s2.0-S0360132322002396-gr1_lrg.jpg" class="post_img" style="width:90%;">
<img src="https://ars.els-cdn.com/content/image/1-s2.0-S0360132322002396-gr2_lrg.jpg" class="post_img" style="width:80%;">

## Case study
- The proposed methodology was illustrated with an office floor of floor area 2600 m2 in a 36-floor commercial building in Hong Kong.
- The studied floor has two PAUs installed. There are four different locations on the studied floor: tenant area, corridor, lobby and toilet. These locations have different ventilation settings and layouts.
- BIM model creation
  - The BIM model of the entire floor of 28/F was created using Autodesk Revit based on design drawings and field observations
  - The models were imported into ANSYS SpaceClaim in SAT format to extract volume and geometric information for CFD simulation
- Scenario study
  - Scenario study during different times of day and different days of the year
    - CFD simulations were conducted during different times of the day and different days of the year to study how time variations affect sensor placement of temperature sensors. In the validated CFD model, the time period considered in the solar analysis is the time period when field measurement was performed. As all the scenario studies are based on the validated case, the solar analysis of different seasons was conducted using the same time period during the day as the validated case.
    - To estimate the solar heat gained and distributed by curtain walls, a solar analysis was conducted on the BIM model of the whole building using Autodesk Insight
    - The simulation was based on geometric, semantic, orientation and location of the BIM model, as well as weather data from the nearby weather station.
  - Scenario study under different MVAC system settings
    - How temperature and CO2 concentration vary under different MVAC system settings, including FCU temperature and PAU speed, was simulated.
    - Instead of setting the same supply temperature on all FCUs on the floor, a proportional adjustment will be made for the scenario study.
    - The assumptions made are as follows: (1) Air inside the floor was well-mixed under the steady-state; (2) Mass and energy were conserved in the system; and (3) The floors were assumed to be air-tight such that air only enters the floor through the PAUs and exits the floor via the exhaust diffuser in the toilet.
  - Scenario study under different occupancy settings
    - To study how occupancy affects temperature and CO2 sensor placement, two different occupancy cases were included in this study: 10% occupancy and full occupancy.
  - Sensor placement generation based on scenario study
    - The simulation results from the scenario study were imported into the GA-based sensor placement optimization program
    - To consider the simulated temperature and CO2 concentration results in 15 nearest locations to the sensors, the value of k is set to be 15 in this study. The sensing range of the sensors was assumed to be 5 m.
    - Based on the chart, the termination criteria are determined to be: (1) there is no change in results in five iterations; or (2) 50 iterations are completed.
    - Three different number of sensor cases were included in the coverage checking: (1) 10 sensors; (2) 20 sensors; and (3) 30 sensors.
    - Based on the scenarios considered in this study, the optimal sensor placements for temperature and CO2 concentration monitoring were generated using k-means clustering

<img src="https://ars.els-cdn.com/content/image/1-s2.0-S0360132322002396-gr3_lrg.jpg" class="post_img" style="width:70%;">
<img src="https://ars.els-cdn.com/content/image/1-s2.0-S0360132322002396-gr4_lrg.jpg" class="post_img" style="width:60%;">
<img src="https://ars.els-cdn.com/content/image/1-s2.0-S0360132322002396-gr5_lrg.jpg" class="post_img" style="width:70%;">

## Data analysis
- Sensor placement coverage checking
  - The coverage checking was conducted according to the sampling point requirements from LEEDv4 and HKIAQ
  - Fig. 7 shows the generated sensor placements using 10 sensors, 20 sensors and 30 sensors. Among the three placements, the placements using 20 sensors and 30 sensors have at least one sensor placed at each monitoring location.
  - Therefore, this study uses 20 sensors to monitor temperature and CO2 concentration distribution on the floor under different seasons, MVAC system settings and occupancy cases.
- Sensor placement accuracy checking
  - Based on the coverage checking results, 20 sensors were placed in all cases. This is to calculate the percentage of the results points with ≥20% difference in simulated results were within 5 m sensing range of the sensors placed in the generated sensor placements.
  - The more significant percentage changes occur in the regions, the more likely the sensors are placed nearby. The sensors placed in these regions will be able to sense fluctuations in temperature and CO2 concentration and hence they are sensible to the indoor environment change under different scenarios.
- Optimal sensor placements generated by different approaches
  - To optimize the placement of 20 sensors on the floor, k-means clustering with k = 20 was conducted to divide the preliminary sensor placements into 20 segments and the centroids in the segments are the optimal locations of the sensors. As for the sensor placement generated using random distribution, the coordinates of 20 sensors are randomly generated based on the 194,280 possible sensor locations.
  - For regular distribution, k-means clustering with k = 20 was conducted to divide the 194,280 possible sensor locations into 20 segments. The centroids in the segments are the optimal locations of the sensors
- Coverage and accuracy checking of sensor placement using different approaches
  - 20 sensors were placed in all cases. Except the one generated by random distribution, all cases have at least 1 sensor in each region and they pass the coverage checking.
  - In general, the optimal sensor placements perform the best and over 70% of the regions with percentage changes of more than 20% in temperature and CO2 concentration are within the sensing range in all scenarios.

<img src="https://ars.els-cdn.com/content/image/1-s2.0-S0360132322002396-gr7_lrg.jpg" class="post_img" style="width:80%;">
<img src="https://ars.els-cdn.com/content/image/1-s2.0-S0360132322002396-gr8_lrg.jpg" class="post_img" style="width:60%;">
<img src="https://ars.els-cdn.com/content/image/1-s2.0-S0360132322002396-gr9_lrg.jpg" class="post_img" style="width:80%;">
<img src="https://ars.els-cdn.com/content/image/1-s2.0-S0360132322002396-gr10_lrg.jpg" class="post_img" style="width:80%;">

## Results and discussion
- Impact of time variations on temperature sensor placement
- Impact of MVAC system settings on sensor placement
  - Impact of MVAC system settings on temperature sensor placement
  - Impact of MVAC system settings on CO2 sensor placement
- Impact of occupancy on temperature and CO2 sensor placement
  - Impact of occupancy on temperature sensor placement
  - Impact of occupancy on CO2 sensor placement
- Impact of rooms on sensor placement
- Implications
  - This study optimized temperature and CO2 sensor placement in a typical office floor for thermal comfort. In the optimal sensor placements for both temperature and CO2, corridor has the greatest number of sensors placed per m2
  - How the air circulates along the corridor and how the air exchange between office, lift lobby and toilets are ignored. The simulated results in this suggests corridor is an important region for sensor monitoring as it can be influenced by ventilation systems in adjacent regions significantly.
  - As occupants release CO2 from their noses, significant variations in CO2 concentration have been observed and hence the generation CO2 sensor placement is greatly affected by the CO2 concentration distribution on nose level.
  - CFD results from scenario study show that the variations of temperature and CO2 concentration is significant in multi-zone environment. The spatial variations in temperature and CO2 concentration exceed 20%.
  - if only six sensors are used, majority of the significant variations of temperature and CO2 concentration on the floor cannot be monitored. This shows that the number of sensors suggested by the standards is insufficient for IAQ monitoring and more research should be conducted to improve the standards.
  - The illustrative example demonstrates how sensors placement can be optimized using BIM technology. The developed simulation-based approach can be applied in new and existing commercial buildings, without the need of continuous field measurement data.
- Limitations
  - The energy-saving insulation effect of walls, doors and windows was not considered due to the lack of information from the building management company. However, the insulation effect can be considered using the proposed methodology by changing the thermal conductance value of the boundary conditions that represent walls, doors and windows.
  - Steady-state CFD simulations were conducted, and hence any human motion-induced flow variation was out of the scope of the study.
  - Due to limited information in the occupied tenant areas, the airflow variations due to furniture and room partitions inside the tenant areas were not taken into consideration in this study. Other indoor heat and CO2 emission sources inside the tenant areas were not considered.
  - Only the CO2 concentration and temperature were considered for sensor placement. Other common air pollutants, such as particular matter (PM), and thermal comfort parameters, such as humidity, were not investigated.

## Conclusion and future study
- This paper presented how to optimize sensor placement using BIM, CFD and GA for thermal comfort and IAQ. A generic approach was developed to optimize placements of sensors detecting temperature and CO2, which are the important parameters of thermal comfort and IAQ, respectively.
- How to overcome limited information of the inaccessible regions by applying the conservation equations as well as considering the MVAC layout of the floor and sources of heat and CO2 emission are also illustrated.
- The methodology was illustrated using a validate CFD model of an office floor. The generated sensor placements satisfied the sampling requirements from LEEDv4 and HKIAQ.
- By checking the optimal sensor placements generated with the CFD results from the scenario study, more than 70% of the regions with percentage change greater than 20% in temperature and CO2 are within the sensing range of the sensors.
- Several limitations of this study are observed: (1) human movement was ignored and (2) furniture inside tenant areas was excluded. Future study should consider other machine learning algorithms, other building types, other pollutants, as well as include furniture and room partitions inside tenant areas.
- Since tenant areas on a typical office floor are usually rented to different companies with different rental terms, variations in room partitions, layouts and occupancy inside tenant areas are significant as renovations are performed by these tenants when they move into the tenant areas. After the sensors are installed, it is difficult for the facility manager of the building to change sensor placements as this may disrupt the business operations of the tenants. An approach to generate sensor placement considering different seasonal factors, ventilation system settings and occupancy is needed.
- With the aid of IoT technology, CFD simulations were conducted to evaluate the thermal comfort of an indoor environment. By coupling CFD simulations and wireless sensor measurement, the CFD model is validated with sensor data and the predicted mean vote value of the model room was estimated
- The purpose of this study is to develop a methodology to optimize temperature and CO2 sensor placement for thermal comfort and IAQ monitoring in a multi-zone environment, with consideration of different scenarios.
- This study illustrated how BIM technology was adopted to support a sensor placement program that uses CFD simulations and machine learning for sensor placement optimization. BIM technology helps to create accurate geometry for multi-zone CFD simulations, and the mesh created can be used to support sensor placement.
