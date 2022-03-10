---
layout: post
title: "[Paper Reading] Development of an IoT and BIM-based automated alert system for thermal comfort monitoring in buildings"
date: 2022-03-07 09:00:00 +0300
description: 2021_Development of an IoT and BIM-based automated alert system for thermal comfort monitoring in buildings # Add post description (optional)
img: 20220307_post_main.jpg # Add image post (optional) 280px, 350px, 470px, 700px, 940px
fig-caption: # Add figcaption (optional)
category: [PR]
tags: [BIM, IoT, Reading]
---

**Publication year:** 2021 <br>
**Authors:** Mojtaba Valinejadshoubi, Osama Moselhi, Ashutosh Bagchi, Ashraf Salem <br>
**DOI:** [https://doi.org/10.1016/j.scs.2020.102602](https://doi.org/10.1016/j.scs.2020.102602)


## Introduction
- Factors such as indoor environmental conditions may affect workers’ comfort, consequently, their health and well-being, and their productivity (Sakellaris et al., 2016).
- indoor air quality (IAQ) and thermal comfort are the most critical factors contributing to worker productivity, satisfaction, and well-being.
- The study presented in Sepp¨anen and Fish (2006) showed that maximum productivity was observed at 21.6 ◦C, although adaptive comfort theory suggests optimum productivity can be attained over a broader range of indoor temperatures (De Dear & Brager, 1998).
- According to ASHRAE Standard 55, various factors influence the thermal comfort level, including air temperature, radiant temperature, air velocity, relative humidity, occupant’s
clothing insulation, and occupant’s activity level.
- Due to low velocity, according to indoor climate studies (Kantor & Unger, 2011; Langner, Scherber, & Endlicher, 2013; Matzarakis & Amelung, 2008), air temperature is approximately equal to the radiant temperature in, air temperature is approximately equal to the radiant temperature in indoor environments.
- The Canadian Centre for Occupational Health and Safety (CCOHS) suggested that the humidity levels should be kept between 30 % and 70 %.
- The relationship between building spaces and their IAQ is more challenging to observe in tabular information than in the 3D model.
- It is important to note that the state of a building may change during its operational phase, and there is no robust standard to check if the building preserves its performance characteristics despite the changes in maintenance state, occupants’ numbers, activities, and seasons.
- It is advantageous to enable BIM models to provide real-time information through the monitoring process. Hence, this will allow the facility managers to interact with the built environment in real-time and provide a better user interface than a traditional thermal condition monitoring system.
- As discussed later, the literature shows some weaknesses in existing methods of thermal comfort monitoring
  - lack of automation and data retrieval (Rania and Isam, 2019; Wu & Liu, 2020)
  - challenges in the continuous object tracking in IoTs in smart cities (Chauhdary, Hassan, Alqarni, Alamri, & Bashir, 2019)
  - limited computer implementation (Cahill, Menzel, & Flynn, 2012; Del Grosso, Basso, Ruffini, Fagini, & Cademartori, 2017; Smarsly & Tauscher, 2016; Sternal & Dragos, 2016)
  - lack of integration of sensor-based alarm systems into BIM models for thermal comfort monitoring in buildings during the operational phase
- The present work attempts to address some of these issues to narrow the research gap by integrating BIM and IoT technologies to automate thermal comfort monitoring
- The primary purpose of this integration is to benefit from the rich User Interface (UI) of BIM-based software and to supplement BIM models with real-time temperature and humidity sensor values.
- The proposed system sends alerts, notifications and all essential information such as room ID, room name, room location, occupancy, etc., using a cloud-based service to the building supervisors and facility manager to remotely acquire just the thermal condition status of monitored spaces to take necessary actions if the operating temperature exceeds the pre-defined
thresholds.


## Literature review
- The study conducted by Rio, Ferreira, and Pocas-Martins (2012) revealed that accomplishing the dynamic monitoring system of a building to provide sensor data to BIM is not part of
the BIM functionality and is still challenging. They concluded that BIM standards need to be extended to allow them to represent monitoring-related information.
- The study conducted by Wang, Fu, and Yang (2017) found that applying BIM in monitoring systems can improve the effectiveness of monitoring processes and decision making. Failure to integrate the data with a BIM model of the building will hinder the facility manager’s ability to intuitively identify potential problems
- Although BIM is desired to be a dynamic workbench for managing all data related to a building project, there are still many challenges in the management of performance data using existing data specifications (e.g., IFC) such as the size of data sets, levels of detail, and interoperability with existing formats employed to store historical performance data
(Gerrish, Ruikar, Cook, Johnson, & Phillip, 2015).


## Thermal comfort assessment and monitoring
- Table 2 shows the acceptable temperature ranges in hot and cold seasons based on more than 80 % occupants’ satisfaction according to ASHRAE Standard 55-2017, which is widely used in North America.
- Some thermal comfort indices, such as the Predictive Mean Vote (PMV) are used to predict thermal comfort. PMV index is used in the Standard ISO 7740. The PMV considers four physical variables (air temperature, air velocity, mean radiant temperature, and relative humidity) and two personal variables (clothing insulation and activity level of the occupant).
- The factors which cause a discrepancy between the predicted and actual occupant thermal comfort level are inaccurate measurements of the person’s characteristics (Clothing surface temperature (tcl) and Metabolic rate of the occupants (M)). Therefore, the PMV model’s accuracy depends on accurately monitoring and controlling the airspeed and accurate measurement of clothing insulation, which could be challenging in practical applications
- Computerized BMS is usually used to monitor climate conditions and manage the HVAC system. BMS can also provide temperature and relative humidity data for analysis (Northeast Document Conservation Center, 2012).
- Analog and digital input signals tell the BMS what temperature, humidity, etc., are. BMS deployment usually involves installing sensors, software, a network, and cloud-based data storage
mostly applied to decrease energy use and save money. However, BMS is complicated and requires specific installation, programming, and maintenance.
- BMS is a customized system applied to large buildings or groups of buildings. However, most buildings, particularly modular buildings, are categorized as low-rise or mid-rise building. For instance, high-rise buildings make up only 10 percent of the US commercial
- One of the main challenges of BMS is in the data visualization stage, in which 2D vector graphics are used, which is not fully interactive and can only be manipulated by a trained operator (Reeser, Jankowski, & Kemper, 2015).
- Therefore, integrating BIM with BMS data can be useful in order to help managers and users perform visual browsing of spatial data and to make building performance information more readily accessible to all building stakeholders, which can both boost energy management awareness and support decision-making during the operating stage


## Research methodology
- The proposed method is comprised of three main components: the IoT system, relational database, and BIM. Each is described in detail below.
  - The first component, the IoT system, is a smartboard associated with a microcontroller. Waspmote microcontroller is used to communicate air temperature and humidity data in individual rooms. The smartboard is connected to temperature and humidity sensors for collecting the thermal comfort data in a specified time interval.
  - The second component is a relational database developed in the MySQL environment to house and update the captured sensors data. The microcontroller can be coded to store and transfer sensors data to the database at predetermined time intervals. In this study, the microcontroller is coded to send the sensors’ measurements and their measurement time to an online MySQL database via ZigBee every 5 min
  - The third component is the BIM-based model of a building. The BIM model is used as a central model to visualize and monitor the thermal comfort levels of rooms remotely and increase the monitoring process’s speed. Every 5 min, when the MySQL tables are automatically updated based on the new sensor data, the BIM model is also updated. To link between MySQL database (physical sensors data) and the BIM model (virtual sensors), nine modules were developed and coded in Dynamo to automatically read temperature and humidity values stored in the database, sort the data, update the BIM model with latest real-time sensor data, and send data to the cloud using a cloud-based collaboration and data exchange services application like Flux, Konstru or Speckle to send notifications to building supervisors and the facility manager through their wireless devices
- As shown in Fig. 3, the temperature and humidity values, measured by the microcontroller, are sent to a cloud-based database through a smart board and ZigBee module.
- The monitoring data is managed in a pre-designed database and are transferred to the BIM model and a cloud-based system through a specially designed workflow to let facility managers or building supervisors to monitor different spaces in a building remotely and identify the technical reasons for possible issues through their PC and wireless-connected devices.

<img src="https://ars.els-cdn.com/content/image/1-s2.0-S2210670720308192-gr2_lrg.jpg" class="post_img" style="width:80%;" alt="BACnet device, object, and properties">
<img src="https://ars.els-cdn.com/content/image/1-s2.0-S2210670720308192-gr3_lrg.jpg" class="post_img" style="width:60%;" alt="BACnet device, object, and properties">


## The system framework
- Hardware configuration of the system
- Development of the BIM model
- MySQL database
- Extracting parameters from the BIM model
- Connecting the BIM model to the database
- Automatic reading of sensor values from MySQL database server
- Updating the virtual sensors parameters in the BIM model
- Defining the conditional statements and updating room parameters

<img src="https://ars.els-cdn.com/content/image/1-s2.0-S2210670720308192-gr5_lrg.jpg" class="post_img" style="width:70%;" alt="BACnet device, object, and properties">
<img src="https://ars.els-cdn.com/content/image/1-s2.0-S2210670720308192-gr7_lrg.jpg" class="post_img" style="width:80%;" alt="BACnet device, object, and properties">


## System implementation
- The test was conducted on the 10th of November 2018. At each time interval, one temperature and one humidity data points were recorded. The system recorded Forty-nine data points during the test (four hours) to validate the proposed method.
- In the developed workflow for integrating BIM into thermal comfort monitoring, Periodic mode was used with the time interval of 300,000 milliseconds (5 min.) to automatically read and extract data from the MySQL database, update the BIM model and send the thermal condition info to the MySQL and cloud-based database every 5 min.
- As shown in Fig. 13, the instrumented office room’s working range condition in the BIM model is ‘Normal!’ and ‘Too Hot!’, respectively, in the first- and eighteenth-time intervals. Therefore, the room was highlighted in red in the time interval eighteen. As observed, the maximum temperature value was measured at 26.0 ◦C at 11:25 AM.
- Fig. 16 illustrates the temperature variations in the instrumented office during the monitoring period. As shown, the temperature level exceeded the acceptable threshold thirteen times. As shown in Fig. 16, at thirteen data points (mostly at noon), the temperature level exceeded the acceptable threshold, and the thermal condition of the instrumented room was not ideal (Too Hot).

<img src="https://ars.els-cdn.com/content/image/1-s2.0-S2210670720308192-gr12_lrg.jpg" class="post_img" style="width:80%;" alt="BACnet device, object, and properties">
<img src="https://ars.els-cdn.com/content/image/1-s2.0-S2210670720308192-gr13_lrg.jpg" class="post_img" style="width:80%;" alt="BACnet device, object, and properties">
<img src="https://ars.els-cdn.com/content/image/1-s2.0-S2210670720308192-gr16_lrg.jpg" class="post_img" style="width:80%;" alt="BACnet device, object, and properties">
<img src="https://ars.els-cdn.com/content/image/1-s2.0-S2210670720308192-gr17_lrg.jpg" class="post_img" style="width:80%;" alt="BACnet device, object, and properties">


## Policy implication
- To make energy standards and policies more effective for existing buildings, one method is developing and using new and efficient technologies
- The system can record the number of discomforts cases in each room and integrate it with the occupants’ satisfaction level, analyzed by a daily computer-based questionnaire, to generate energy policies and alerts about the HVAC system performance or building envelop-related issues leading to future savings on renovation projects
- Using information extracted from the developed system, policymakers can consider the risk of thermal discomfort on energy consumption and, consequently, on their policy outcome in the rooms with high thermal discomfort cases.


## Discussion
- Recent services such as Amazon CloudWatch and Google provide cloud services for data analytics, including platforms for data visualization. Although these kinds of services can collect data and create alarms and graphs, they are not flexible and cannot facilitate interaction between the building data model and sensor data.
- In small- and medium-sized buildings where the BMS may not be used, or in buildings where the only purpose is to monitor the environmental quality factor (e.g., thermal comfort) of space not to control the electrical and mechanical components, the developed monitoring system can be an alternative one as a powerful data-driven asset management tool to provide a smart technology for energy savings and creating a healthy and productive workplace, especially in office buildings.
- The benefits of using the IoT system to transmit temperature and humidity data, as opposed to passing them over the wire, are increasing the flexibility and decreasing the installation complexity and cost.
- BIM was utilized to replace HMI in BMS, which currently uses 2D vector graphics for data visualization. The integration of BIM into thermal comfort monitoring would improve the
building’s maintenance plan by helping the facility managers inspect the monitored environments of the building inside the 3D model, while it is impossible to do this type of inspection within the conventional HMI interface
- for any reason that may cause thermal discomfort, whether HVAC failures or heat loss due to cracks in building envelopes, a rich BIM model information would help the facility
managers seek a proper and fast possible solution providing an effective maintenance planning.
- The present study attempts to fill the gaps found in the literature, as discussed in Table 1, such as the lack of automation (Asl, Zarrinmehr, Bergin, & Yan, 2015; Wehbe & Shahrour, 2019; Wu & Liu, 2020), lack of data retrieval system (Natephra & Motamedi, 2019), and the lack of computer implementation and validation (Del Grosso et al., 2017; Emad, Wei, & Philip, 2017; Natephra et al., 2017; Smarsly & Tauscher, 2016; Sternal & Dragos, 2016) in the thermal comfort monitoring
- However, there are some limitations in this work, which are as follows:
  - Further studies are required to conduct a large-scale investigation and review its integration with the facility managers and other stakeholders to test the system for its reliability, reproducibility, robustness, and ease of use.
  - The system developed here was tested with a limited number of sensors. The system can also be expanded to use different sensors for other purposes,


## Conclusion
- BIM’s ability to visualize the monitored information is expected to assist building supervisors and facility managers in locating spaces experiencing thermal comfort problems.
- The integration of BIM and IoT through a specially designed database and modules developed in a visual programming environment provides an effective visualization of office spaces associated with indoor air temperature and humidity levels.
- The system developed in this study was implemented, and its capabilities were illustrated through a case study. The system was able to detect the time and location of the office room, experiencing thermal discomfort based on targeted thresholds.
- The system could detect and record thirteen thermal discomfort cases that exceeded the thermal threshold value during the test.
- When sensor values crossed over the defined temperature level thresholds, the system highlighted the room in Red on the BIM model and generated text alarms.
- Using measurement history tables in the designed database, facility managers can retrieve and visualize the previously-stored sensor values from the central database, which can be used for future investigations, pattern analysis, and building controls optimization.
- Although installing sensors on HVAC systems can monitor real-time temperature changes, the developed system can be used to make HVAC systems intelligent and manage them.
- The developed system can be used to detect defects in HVAC systems that avoid the high costs of the system’s failure.
- The use of the developed system can help facility managers take timely actions related to occupants’ thermal comfort and avoid property damage and hazardous situations.
- Such an approach (by taking real-time and accurate thermal data) can lead to better policymaking, which may help decision-makers or urban planners revise the existing guidelines, protocols, or building regulations.
