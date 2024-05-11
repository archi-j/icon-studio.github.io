---
layout: post
title: "[Paper Reading] ROBOD, room-level occupancy and building operation dataset"
date: 2023-12-28 09:00:00 +0300
description: "2022_ROBOD, room-level occupancy and building operation dataset" # Add post description (optional)
img: 20231228_post_main.JPG # Add image post (optional) 280px, 350px, 470px, 700px, 940px
fig-caption: # Add figcaption (optional)
category: [PR]
tags: [Occupant Comfort, Occupant Behavior, Human-Building Interaction]
---

**Publication year:** 2022 <br>
**Authors:** Zeynep Duygu Tekler, Eikichi Ono, Yuzhen Peng, Sicheng Zhan, Bertrand Lasternas, and Adrian Chong<br>

## Introduction
- These models often require the systematic collection and analysis of various real-world inputs such as the buildings’ operational data, energy use and occupancy information to derive meaningful insights and develop effective strategies for reducing building energy use.
- At the same time, data-driven or machine learning-based models require a sufficient amount of training data to produce reliable prediction results.
- However, the collection of such real-world datasets is often challenging in reality:
    - Firstly, it requires the installation of different sensors within each room in the building, which can incur a considerable cost depending on the number of rooms and the size of the target building.
    - Secondly, the integration of the sensor data collected can also create additional hurdles due to the issues related to intermittent sensor failure and nonstandard sampling frequencies used by different sensor manufacturers.
    - Lastly, the collection of occupancy data, which is often performed in person or through surveillance cameras, is labour intensive and may also encounter resistance from the building occupants due to privacy concerns.
- The latest release of the ASHRAE Global Occupant Behaviour database provides a large compilation of different survey-based and in-situ-based datasets collected from multiple countries and covering various building types both in the commercial and residential sectors.
- Through the use of this dataset, researchers from different fields can benefit from various applications, including but not limited to occupancy prediction and occupant behaviour modelling, building simulation and control, energy forecasting, and building analytics.

## Methods

#### Building and room characteristics
- The building considered in this dataset is the School of Design and Environment 4 (SDE4) building located at the National University of Singapore (NUS). SDE4 is a 6-story academic building spanning 8,588 square meters and is accessible 24 hours every day.
- The five rooms include two different-sized lecture rooms (Room 1 and Room 2), an office space for administrative staff (Room 3), an office space for researchers (Room 4), and a library space for students (Room 5).
- Specific rooms such as Room 1, Room 2 and Room 5 are open for all university students and staff, and are not limited to those situated in the SDE4 building. On the other hand, Room 3 and Room 4 are only accessible by dedicated administrative staff and researchers that have an assigned seating in these rooms as an access card is required for entry.

#### Indoor environmental quality data
- The indoor environmental data represent the measurements for indoor environmental quality, which include VOC (volatile organic compound), sound pressure level, relative humidity, indoor air temperature, illuminance, PM2.5 (particulate matter), and CO2 concentration levels.

#### Wi-Fi data
- The Wi-Fi data represents the number of Wi-Fi-enabled devices connected to the routers installed in each room.
- To use the number of Wi-Fi connected devices to estimate the number of occupants in the room, several filtering steps could be introduced to differentiate between the stationary and mobile devices, before inferring the occupant count based on the number of mobile devices indirectly.

#### Energy data
- The energy data represents the energy consumption values of the building’s electrical end uses such as HVAC, lighting, plug loads, and ceiling fans. For HVAC energy consumption:
    - Room 1 and Room 2 are conditioned by Fan Coil Units (FCU), with the chilled water supplied by a district chiller plant and the supply airflow rate controlled by variable speed fans.
    - Room 3, Room 4, and Room 5 are conditioned by Air Handling Units (AHU), which are connected to multiple rooms in the building.
- The energy consumption data of lighting, plug loads, and ceiling fans are collected through electrical meters and the number of each end use (i.e., lighting, plug loads and ceiling fans)

#### HVAC operations data
- The HVAC operations data represent the different parameters and settings that the building’s HVAC system operates within.
- It should be noted that the building uses a dedicated outdoor air system for air supply, so the CO2 level of incoming air is identical to the outdoor CO2 level. Furthermore, there is no operable shading or windows in the study rooms, except for the operable windows in Room 4 which are rarely open based on our observations.
- The temperate setpoint in all rooms is conditioned by Proportional Integral Derivative (PID) control against the thermostat temperature setpoint set by the room occupants.

#### Outdoor weather data
- The outdoor weather data is measured by a local weather station installed on the roof of the study building.

#### Occupancy data
- The occupancy data contains both the occupant presence and number of occupants present in each room. This information was collected by monitoring the occupants’ movement through surveillance camera footage and manually counting the number of occupants.
- Due to the use of a passive monitoring approach to monitor occupancy within the study room, the impact of the Hawthorne effect is minimised as compared to the adoption of active monitoring approaches.

#### Data pre-processing
- These steps involve formatting the timestamp information for each data category to follow the same ISO 8601 date-time format (i.e., YYYY-MM-DD HH:MM +-HH:MM),

## Data records
- The data collection period spanned between 7 September and 23 December 2021, where the sensor data collected during the weekends were excluded.
- The chosen period allowed us to capture the changes in occupancy patterns and the building’s operation both during the regular semester and the semester break. Furthermore, there were also specific days during the data collection period when several of the sensors were not working correctly for certain rooms.

## Concluding remarks
- Through the conduct of this study, we have experienced several challenges along the way and have summarised their proposed solutions below to aid future studies in overcoming these challenges:
    - Minimising Hawthorne effect: The use of surveillance cameras over active monitoring approaches (i.e., wearable sensors and smartphone devices) was chosen to passively monitor the users’ presence information to minimise the study’s impact on the users’ behaviours and regular routines.
    - Protecting user privacy: Personal identifiers were not collected from the occupants at any point during the data collection process to protect their privacy.
    - Sensor failure: There were specific days during the data collection period where several sensors were not working correctly for certain rooms. As a result, this led to the data collected during these periods being dropped from the final dataset.
    - Missing data: Due to the presence of a small number of missing data records caused by intermittent sensor failure, an imputation algorithm based on the “missingpy” library was proposed to impute the missing data values.
    - Merging different data categories: To perform a successful merge of the different data categories, several data pre-processing steps were taken. These steps involve first down-sampling/up-sampling the data records from each data category to follow a 5-minute sampling interval before standardising the timestamp information for each data category to follow the same ISO 8601 date-time format.
