---
layout: post
title: "[Paper Reading] The Mechanism and Challenges of Validating a Building Information Model regarding data exchange standards"
date: 2022-01-03 09:00:00 +0300
description: 2019_The Mechanism and Challenges of Validating a Building Information Model regarding data exchange standards # Add post description (optional)
img: 20220103_post_main.jpg # Add image post (optional) 280px, 350px, 470px, 700px, 940px
fig-caption: # Add figcaption (optional)
category: [PR]
tags: [BIM, Interoperability, Reading]
---

**Publication year:** 2019 <br>
**Authors:** Yong-Cheol Lee, Wawan Solihin, Charles M. Eastman <br>
**DOI:** [https://doi.org/10.1016/j.autcon.2018.12.025](https://doi.org/10.1016/j.autcon.2018.12.025)

## Introduction
- With the increasing number of requirements and complex structures of a building project, domain professionals need to iteratively exchange Building Information Modeling (BIM) data throughout a project. In addition,the Model View Definition (MVD), a subset of the IFC schema and a BIM data exchange standard for one discipline, requires an additional process to amend its specifications according to the updates of the IFC schema.
- These demanding modification processes prevent a consistent and coherent application of BIM data exchange standards.
- domain experts and software vendors employing MVD to develop IFC importing and exporting features of their BIM authoring and application tools frequently encounter problems pertaining to mapping processes between native object information and IFC.
- data currently have no proper method to examine and assess whether their BIM models that have been translated from IFC importing and exporting processes have syntactically correct and semantically accurate information without unintended geometric translation.
- since project participants have customized BIM authoring tools and applications for their particular work processes, translating diverse native object information into IFC information according to the MVD can result in heterogeneous BIM data and geometries, preventing domain professionals from obtaining accurate BIM data.

<img src="https://ars.els-cdn.com/content/image/1-s2.0-S0926580517311305-gr1_lrg.jpg" class="post_img" style="width:90%;" alt="BACnet device, object, and properties">


## BIM data validation regarding the Model View Definition
- The increasing demand of data exchanges during a project has led to a critical issue for interoperability, particularly pertaining to the quality, accuracy, and requirements of BIM data.
- An MVD facilitates seamless BIM data exchanges by describing the BIM data exchange processes of specific domain data among relevant project participants
- Drawing on knowledge of their domains, experts in diverse disciplines define the ER for MVD developers so that they can define an MVD that encompasses a set of BIM data exchange requirements.
- To avoid repetitive definitions of an MVD, an MVD developer employs a concept that is a unit of a requirement definition modularized according to an entity, an attribute, a relationship, and other necessary components. It can be defined by a concept template that includes attributes and their empty values as defined in the IFC schema.
- The implementation agreement of a concept definition contains detailed IFC object mapping information that helps software developers bind their native objects into IFC objects to develop their IFC interfaces.
- A consistent validation process should detect these semantic and syntactic errors, which can cause BIM data translation problems, information omissions, and unintended geometric translation, before these data are shared with project participants
- Domain experts and BIM software vendors refer to ER in an MVD to develop IFC importing and exporting features of BIM authoring tools and relevant applications. During this process, however, the IFC schema is subject to vague interpretation, frequently leading to unintended errors in the MVD development, and generates heterogeneous binding processes of BIM authoring tools that inconsistently map their native BIM objects onto IFC objects, or vice versa. These development processes of ER and IFC importing/exporting features may lead to the following problems: human errors, multiple interpretations, IFC-native object mapping errors, and other relevant issues.
- Even though IFC supports BIM data exchange with a consistent MVD standard such as coordination view 2.0 (CV 2.0), most BIM authoring software executes heterogeneous processes for IFC importing and exporting that generate unexpected and unintended problems because of inconsistent data translation processes.
- Capturing the causes of an error is difficult, particularly when BIM data are complicatedly defective.
- Illustrating the locations and the causes of errors according to defined ER requires an automated BIM validation process, which could also prevent the heterogeneous development of IFC interfaces according to model views.
- Global Testing and Documentation Server (GTDS) has hidden procedures and considerably time-consuming tests. To ensure the interoperability of BIM data exchange, the authors developed a validation framework, using rules categorized in the PC model views, on top of the IfcDoc tool, an MVD documentation and validation platform
- To ensure the interoperability of BIM data exchange, the authors developed a validation framework, using rules categorized in the PC model views, on top of the IfcDoc tool, an MVD documentation and validation platform
- particular, software vendors can use the validation platform to identify unreliable and inconsistent IFC mapping procedures of IFC translation interfaces developed on their BIM software so that they can significantly reduce the amount of time and effort they spend on debugging processes.
- This automated validation process and framework will enable project participants and software developers to confirm the quality, accuracy, and integrity of BIM data regarding the syntactic and semantic requirements defined in an MVD.

<img src="https://ars.els-cdn.com/content/image/1-s2.0-S0926580517311305-gr2_lrg.jpg" class="post_img" style="width:70%;" alt="BACnet device, object, and properties">


## BIM and IoT integration for different domains
- During this research project, which develops a formalized validation method using the PC BIM standard, the authors have identified several unexpected challenges and limitations.
- This research assessment process utilized the following MVD: The Precast Concrete MVD, Coordination View 2.0, and Construction Operations Building Information Exchange (COBie). The authors imported ER embedded in these MVDs to IfcDoc and used them as checking criteria to evaluate whether an IFC instance file has correct information as defined in an imported MVD or not.
- IFC schema structure developed for data exchange
  - The primary objective of the IFC schema is to provide a neutral format of BIM data that the AEC-FM industries can openly exchange and share. Thus, it has been designed and revised as a common BIM standard format for data exchange, not data modeling
  - Since a standard format should represent all domain knowledge with various representation methods of current BIM authoring tools and applications, its design should contain all possible data and representation methods for exchanging BIM data
  - As the IFC schema is subject to alternative definitions and interpretations of domain knowledge, its flexible data representation can be an obstacle to defining strict rules and robust validation processes regarding object attributes and references.
  - The primary problem of BIM data validation associated with the IFC schema is that the implementation of validation features currently developed on top of IfcDoc supports only the evaluation of syntactic and semantic constraints defined in an MVD, not accuracy or representation methods.
  - Even though IfcDoc currently validates BIM data regarding syntactic and semantic constraints, it has limitations such as its inability to directly evaluate accuracy and changes in transformed geometry. Thus, for evaluating BIM data, it is promising to adopt the integrated validation processes pertaining to syntax, semantics, and geometrical constraints that include program requirements.

<img src="https://ars.els-cdn.com/content/image/1-s2.0-S0926580517311305-gr4_lrg.jpg" class="post_img" style="width:70%;" alt="BACnet device, object, and properties">

- Scope of MVD validation
  - The development of a data validation framework demands a strict definition of the scope of checking.
  - Previous MVD validation studies did not clearly define the scope of the work and checking process for the following reasons.
  1. The lack of a robust standard for defining the requirements of data exchange has created an opportunity for domain professionals to establish requirements of MVDs with heterogeneous methods and processes.
  2. if an initial precast concrete BIM model has not been developed by a modeler to declare that its slab is “Precast Slab” as it is, when domain experts exchange BIM data, including IfcSlab, through various BIM authoring tools, this semantic data omission could be interpreted  by an MVD validation framework as an error of BIM data exchange

<img src="https://ars.els-cdn.com/content/image/1-s2.0-S0926580517311305-gr5_lrg.jpg" class="post_img" style="width:70%;" alt="BACnet device, object, and properties">

- Involvement of the IFC schema-level checking into the MVD validation
  - Of particular interest is the involvement of IFC schema-level syntax checking in the process of IFC  instance validation according to the MVD.
  - A STEP ISO 10303 Part 21 physical file (P21 file), referred to as an IFC instance file, must comply with the specifications of the IFC schema
  - As an MVD, however, is defined on top of the IFC schema, IFC instance validation according to the MVD must consider the fundamental syntactic constraints defined in the IFC schema and the EXPRESS language
  - the validation of the syntax level defined in the IFC schema and the EXPRESS language pertaining to uniqueness (in the checking of GUID and SET) and fundamental syntax checking such as OwnerHistory is slightly ambiguous.
  - the involvement of IFC syntactic constraint checking in MVD validation should be clearly determined, as it will provide consistent MVD validation without unnecessary checking processes.

<img src="https://ars.els-cdn.com/content/image/1-s2.0-S0926580517311305-gr6_lrg.jpg" class="post_img" style="width:80%;" alt="BACnet device, object, and properties">
<img src="https://ars.els-cdn.com/content/image/1-s2.0-S0926580517311305-gr8_lrg.jpg" class="post_img" style="width:80%;" alt="BACnet device, object, and properties">

- Ambiguous constraints and their priorities for checking sequence
  - An MVD should include all definitions of entities, attributes, and relationships required for the data exchange processes of a targeted domain.
  - The validation of IFC data regarding MVD specifications generally consists of mandatory and optional constraints.
    - Mandatory requirements must be satisfied by an IFC instance file. A concept definition can state that a BIM model must have a particular entity, attribute, or property for a designated data exchange.
    - In fact, since a BIM model can be flexibly defined according to project requirements, its validation rules do not require strict definition or execution as specified. Thus, the mandatory constraint might have to be updated to cover a broader requirement even though its range and scope have not been discussed.
  - Since this issue is closely related to the process of defining the scope of MVD validation, several cases of current MVDs and their specifications should be examined in order to formalize MVD requirements and validation rules. Furthermore, both mandatory and optional rules are related to the validation of the existence of objects from the perspective of MVD validation.
  - If several constraints are combined into one validation process, neither mandatory nor optional checking can easily be managed.
  - Another challenge is an implementation sequence of multiple rules.
    - Currently, IfcDoc executes validation features based on an IFC entity. It begins by identifying the IFC entities defined in an imported MVD and evaluates the same IFC entities of an imported BIM model.
    - Thus, to accurately evaluate one attribute, defined rules should be logically organized and checking processes should be sequentially ordered. The well-ordered sequence of rule types allows the efficient handling of complex relationships and numerous requirements of attribute validation. The priority of rule types, however, should be separately defined and implemented according to domains, exchanges, and evaluation entities.
- Diverse approaches to defining MVD and validation
  - IDM information is mapped onto the IFC format to create a subset of an IFC schema that is generally consumed by BIM software developers to build IFC importing/exporting interfaces and also used in the validation process. To define BIM data exchange requirements for diverse disciplines, however, domain professionals and MVD developers must understand the detailed steps of MVD development processes, including the IDM, exchange requirements, concept blocks/templates, and other necessary information
  - Although this MVD development process, depending on the dexterity or the capabilities of MVD developers, can be complicated, several domains have used various methods to develop documents with distinct structures and contents of the MVD and concepts
  - This heterogeneous IFC data mapping of BIM authoring software can result in syntactic and semantic errors. Thus, the development of consistent rulesets and robust validation processes requires gthe formalization of MVD processes and their details.

<img src="https://ars.els-cdn.com/content/image/1-s2.0-S0926580517311305-gr10_lrg.jpg" class="post_img" style="width:60%;" alt="BACnet device, object, and properties">

- Integrity of formalized rule logic and inconsistent structure of concept templates
  - Imperfection of rule sets and validation methods is one of critical limitations for establishing consistent a BIM checking approach using an MVD.
  - To provide a consistent BIM checking method, rules and corresponding validation processes should be categorized and generalized. As the IFC schema has been continuously updated for covering diverse domain knowledge, however, an MVD and its rules should be revised according to the IFC schema and new demands
  - As a result, a validation approach that should handle this broad area of MVD contents cannot be robustly established for satisfying the demands of data exchange specifications
  - Since diverse domain knowledge should be flexibly defined in an MVD, the reuse of a concept for defining other concepts is allowed; that is, since a concept is a modularized unit of knowledge, we can reuse it to represent several concepts to take an advantage of predefined definitions with a subtype entity as a root entity
  - Since diverse domain knowledge should be flexibly defined in an MVD, the reuse of a concept for defining other concepts is allowed; that is, since a concept is a modularized unit of knowledge, we can reuse it to represent several concepts to take an advantage of predefined definitions with a subtype entity as a root entity
- Geometry, topology and local placement checking
  - An MVD generally addresses semantics embedded in the subset of the IFC schema. Thus, an evaluation of geometry and topology is not executable in MVD validation processes.
  - The current version of the IfcDoc tool implements a semantic match that compares one value of a BIM model with that of an MVD to identify the accuracy of the translated semantics of BIM models. However, this process cannot guarantee that a BIM model will satisfy the requirements of data exchanges declared for an associated domain.
  - the authors believe that the integration of validation processes using an MVD and geometrical checking features should be developed and applied to accurately evaluate a BIM model according to ER.


## Conclusion
- The assurance of the accuracy and the interoperability of BIM data exchange requires formalized rulesets and a robust validation framework. Establishing a generalized checking process of BIM data according to the specifications of an MVD poses several limitations and challenges.
- The primary challenge involves the structure of the IFC schema, which must continuously be revised and updated so that it addresses diverse exchange definitions based on multiple types of domain knowledge
- Since the design of the IFC schema supports BIM data exchange, not BIM modeling, it should address diverse types of data types along with their various methods of representation.
- Another major challenge is the broad scope of defining a model view and validating an instance file according to its specifications. As a result, the definition is subject to multiple interpretations and diverse ways that domain professionals and software vendors can refer to when they define their domain knowledge.
- To address these limitations, it is required to consistently examine diverse approaches that can identify an explicit link between concept rules and formal information models. In addition, we should also investigate current MVDs and their associated rules, which may provide a stepping stone for reliable validation of BIM data exchange and consistent definitions of model view specifications.
