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
