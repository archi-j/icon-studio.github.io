---
layout: post
title: "[Paper Reading] JavaScript Object Notation (JSON) data serialization for IFC schema in web-based BIM data exchange"
date: 2022-05-24 09:00:00 +0300
description: 2022_JavaScript Object Notation (JSON) data serialization for IFC schema in web-based BIM data exchangeg # Add post description (optional)
img: 20220524_post_main.jpg # Add image post (optional) 280px, 350px, 470px, 700px, 940px
fig-caption: # Add figcaption (optional)
category: [PR]
tags: [BIM, IFC, JSON]
---

**Publication year:** 2017 <br>
**Authors:** Kereshmeh Afsari, Charles M. Eastman, DanielCastro-Lacouture <br>
**DOI:** [https://doi.org/10.1016/j.autcon.2017.01.011](https://doi.org/10.1016/j.autcon.2017.01.011)


## Introduction
- Most importantly, while vendor specific data formats are quite diverse, they are based on multiple and different data schemas, and data standards for Cloud-based cross-platform data exchange purposes are limited.
- In the building industry, building data such as objects and processes is described in Industry Foundation Classes (IFC) data model schema to support a neutral data format for BIM tools interoperability. IFC schema defines a set of generic building objects with associated attributes and properties as well as multiple shape definition methods for the objects.
- So far, IFC specification is provided as EXPRESS and XSD definitions and IFC data files that are being exchanged between applications use three main data formats including “.ifc” using the STEP physical file structure, “.ifcXML” using the eXtensible Markup Language (XML) document structure, and “.ifcZIP” using the PKzip 2.04 g compression algorithm
- buildingSMART International has implemented the IFC standard using XML technologies as ifcXML specification. XML is a platform independent language for representing data and has been used in the development of web service applications.
- the performance of web services have shown a significant decrease when using XML data because of the low efficiency of reading and parsing XML data during the execution of services
- Initially, XML was used in a wide range of AJAX developments, but gradually XML showed inadequacies because its performance reduces significantly when it is applied to interactive pages. In order to address the issues of XMLbased services, AJAX decreases the server workload by applying JavaScript at the client side.
- JSON is a native data for JavaScript and this feature makes JSON a proper format to be used for data exchanging in AJAX applications. JSON is a key-value style lightweight data exchange format which is independent of any programming language and unlike XML it is easy for machines to parse and generate while it is also human readable
- This paper highlights that there is a need to provide guidelines on how to translate IFC data to JSON to indicate how IFC schema can be represented as JSON specification. Therefore, in this paper the main objective is to outline that IFC specification can be represented in JSON format.
- The ifcJSON schema and document developed in this paper can facilitate standardization of JSON-based BIM data and can have a major impact on interoperability of Web-based BIM applications by unifying BIM data representation based on both industry-wide standard i.e. IFC and Web compatible data format i.e. JSON. This approach to interoperability of Web-based BIM applications can expedite the production and revision of construction documents through using Web compatible BIM documents.

## IFC schema and data serialization
- IFC data model provides the basis for a common understanding of the building processes and the required information results from their execution. IFC represents an open specification by introducing object classes and provides a useful structure for data sharing among applications in a building construction or facility management project.
- The XML schema is automatically created from the EXPRESS representation of IFC schema by a language binding described by “XML representation of EXPRESS schemas and data”,defined as ISO10303 part 28 edition 2. Therefore, based on this procedure, ifcXML ensures to handle the same data consistently as IFC-EXPRESS and also the data files can be converted bi-directionally from “.ifc” to “.ifcXML”
- The EXPRESS IFC schema, the SPF format and ifcXML formats are each a particular implementation of the ISO standards [8] i.e. ISO 16739:2013. But so far JSON schema specification for IFC data model has not been developed.

## The need for JSON-based IFC specification
- JSON uses a text format that is independent of the language so its format is different from XML format that has closed tags. JSON data format supports high scalability and it creates more compact models than XML.
- Several research projects in the last few years have processed and analyzed JSON data. Most of these studies compared JSON with XML data in performing within web services. They showed that:
    - XML-based web service runs with low efficiency although XML language has good specification. Using JSON-style format for data exchange, compared to XML, can improve the performance of web service applications.
    - Results of a case study indicate that JSON is faster and uses fewer resources than the same XML data. JSON performs better than XML in being parsed, being serialized and being deserialized XML objects are analyzed as Document Object Mode (DOM) which takes a long time. XML requires extra libraries to retrieve data from DOM objects. But JSON objects are analyzed as string arrays which can perform much faster.
- Despite the many advantages of JSON, there has not been any implementation of IFC data model based on JSON data exchange format. Therefore, to use the benefits of JSON over XML in the building industry data exchanges, this study proposes the development of “ifcJSON”.
- BIM data and JSON serialization
  - As BIM data is gradually moving to the Cloud, several efforts in translating vendor specific BIM data to JSON format have already been initiated.
  - In this study, we emphasize on the need for a standardized JSON schema based on an industrywide open standard i.e. IFC schema and not based on a specificvendor schema convention. So, this study focuses on translating IFC specification to JSON schema and JSON document rather than serializing vendor specific BIM data into a JSON format.
  - This study proposes ifcJSON as the standardized JSON encoding of BIM data based on both JSON schema and IFC specification.
  - The detailed study of the source codes, schema definition and example files in BIMserver shows that although BIMserver uses some sort of converting IFC to JSON data, the schema is not a wellstructured IFC-based JSON schema for several reasons.
    - Firstly, this schema is not developed according to the JSON schema specification that is the latest Internet Engineering Task Force (IETF) documentation published for JSON specification.
    - Secondly, this schema does not address mapping of required and optional attributes
    - Thirdly, IFC schema definition based on JSON serialization in BIMserver is incomplete
  - Another JSON based schema definition used in solutions like bimJSON is inspired by GeoJSON. The bimJSON itself is still in development.
  - Although GeoJSON is an internet standard, so far there is no published schema definition for it and most importantly, there is no GeoJSON schema for building data.
  - GeoJSON is not suitable for a well-defined building data schema
    - firstly, since it is concerned with geographic data in the broadest sense it does not support complex geometry definition
    - secondly, since it only aims at serializing geographic data, other data than geometry definition should be specified within “properties” keyword and “properties” definition is too broad with no specification to address building data components and attributes like it is specified in IFC schema.

## Developing ifcJSON
- Methods for JSON encoding of IFC specification
  - In order to implement JSON encoding of IFC specification there are two major methodologies that can be applied: 1) to translate ifcXML to JSON serialization, or 2) to directly convert IFC EXPRESS specification to ifcJSON schema.
  - First method is to translate ifcXML specification to JSON serialization using XML to JSON translating algorithms.
    - The analysis of original XML data structure and translated JSON data structure shows that although the translation of data between XML and JSON can be applied, data mismatches will be caused and the data accuracy will decrease
    - “If the ifcXML schema is used to generate a model in a database implementation that is not compliant to the EXPRESS standard then certain conflicts or limitations may be encountered”
    - The methodology of translating ifcXML to ifcJSON is not accurate and effective, so it is not recommended.
  - Second method is to directly translate IFC EXPRESS to JSON serialization. However, there is no standardization on configuration of mapping between EXPRESS and JSON and there is no available methodology for automatic conversion between IFC EXPRESS and ifcJSON. Therefore, this study develops the methodology for implementing ifcJSON schema definition from IFC EXPRESS specification.
- ifcJSON4 implementation approach
  - Unlike ifcXML schema specification that is an automatic conversion from the EXPRESS (ISO 10303 part 1) representation of the IFC schema, there is no available methodology for automatic conversion between IFC EXPRESS and ifcJSON. In addition, there is no standardization on configuration of mapping between EXPRESS and JSON in general.
  - Then, the paper describes the data content of an ifcJSON document and its data validation process. The methodology for data model mapping in this paper (shown in Fig. 2) can be summarized in three main steps:
    - ifcJSON4 Schema development, which is the JSON schema definition that corresponds to the IFC4 EXPRESS definition. This is developed through the generation of a schema from the IFC4 EXPRESS source definition as well as JSON Schema specification defined by IETF.
    - ifcJSON document implementation, which is a JSON document that can be validated against the ifcJSON4 schema. Each ifcJSON document should be well structured and validated for formatting JSON data and it should also pass the validation against ifcJSON4 schema.
    - Data validation approach, which addresses three validation approaches including the validation of ifcJSON data for formatting, the validation of ifcJSON4 Schema against the original JSON Schema, and the validation of ifcJSON document data content against the ifcJSON4 schema.
  - JSON Schema “is a JSON media type for defining the structure of JSON data. JSON Schema is intended to define validation, documentation, hyperlink navigation, and interaction control of JSON data”
  - The content of the ifcJSON document described in this paper, can be represented in “.ifcjson” or “.json” format which is the exchange format for ifcJSON. This document should be validated both with a validator for formatting JSON data as well as against the ifcJSON4 schema.

<img src="https://ars.els-cdn.com/content/image/1-s2.0-S0926580517300316-gr2_lrg.jpg" class="post_img" style="width:90%;">

- ifcJSON4 application and evaluation
  - In addition to providing a data model mapping for ifcJSON, proposed implementation is applied in a use case to evaluate the data content of ifcJSON exchange model. There are three fundamental entity types in the IFC model as object definitions, relationships and property definitions and in this paper we focus on the representation of IFC object definition.
  - The use case selected in this study indicates the implementation of ifcJSON representation for object definition in precast concrete exchange model known as EMPC1. Precast Concrete BIM standard defines the specification of the Model View Definitions for twelve precast model exchanges and specifies EMPC1 as a subset of IFC schema.
  - The use case approach in this paper generates an ifcJSON document that contains three information groups, known as IFC concepts listed below to represent IFC object definition
    - Owner History Data: While owner history data is optional in IFC schema [19], EMPC1 requires history and identification data as exists in IfcOwnerHistory entity (Fig. 3) to be mandatory in the exchange model.
    - Geometry Representation Data: EMPC1 requires the model to use extruded geometry for representation of the building elements.
    - Product Placement Data: Product occurrences can be placed in 3D space relative to where they are contained. For building elements positioning is relative to the containing spatial structure. In IFC schema, ObjectPlacement attribute is optional but in EMPC1 the provision of product placement data of precast pieces is required.
<img src="https://ars.els-cdn.com/content/image/1-s2.0-S0926580517300316-gr3_lrg.jpg" class="post_img" style="width:60%;">
<img src="https://ars.els-cdn.com/content/image/1-s2.0-S0926580517300316-gr4_lrg.jpg" class="post_img" style="width:70%;">
<img src="https://ars.els-cdn.com/content/image/1-s2.0-S0926580517300316-gr5_lrg.jpg" class="post_img" style="width:70%;">

- Implementation challenges and limitations
  - The implementation of ifcJSON faces several challenges and issues listed below.
    - There is a lack of standardization on translating EXPRESS model to JSON data. There is no automated methodology, standard or guideline to guide mapping from EXPRESS to JSON.
    - There is no documentation on a methodology to convert the IFC source definition in EXPRESS into a JSON schema.
    - The validation of ifcJSON document needs to ensure that the document is well formed and that it is conformed to ifcJSON4 schema. Currently there is no tool that can handle these two validation methods at the same time. Therefore, these two validation approaches need to be done separately.
    - There is no tool for visualizing. ifcjson file in terms of the geometry representation and the attributes. Therefore, after generating the ifcJSON document and validating it, this document can be translated back to an SPF format in order to visualize model in model viewers (e.g. Solibri).
    - IFC EXPRESS specification includes data item for types, entities, rules and functions but ifcJSON implementation in this paper similar to the schema derivation logic in ifcXML implementation oses some constraints including rules, inverse relationships and derived attributes
    - some of the supertype/subtype dependencies are summarized in a way that it can manage limited number of entities to be implemented.
    - some of the EXPRESS datatypes such as defined datatypes and select datatypes have been reduced in accordance with the use case in this study to facilitate the generation of the ifcJSON schema.

## Data model mapping
- JSON Schema,ingeneral,defines a structure for what JSON data is required to provide and therefore its schema defines the validation and interaction control of JSON data
<img src="https://ars.els-cdn.com/content/image/1-s2.0-S0926580517300316-gr6_lrg.jpg" class="post_img" style="width:60%;">

- ifcJSON4 schema
  - The ifcJSON4 schema implemented in this paper has seven major properties (i.e. keywords) shown in Table 2 which follows the structure of JSON Schema and uses the latest published draft v4 specification
  - Implementing IFC types and entities
    - ifcJSON root represents IFC types under “definitions” and IFC entities under “properties” keywords.
    - instead of using the IfcAxis2Placement type, this representation can be used to refer to IfcAxis2Placement2D or IfcAxisPlacement3D.
    - Since IfcAxis2Placement2D and IfcAxis2Placement3D are main IFC entities, these are defined under “properties” in the ifcJSON4 schema root.
  - Attributes implementation
    - In IFC specification class of information i.e. IFC entities defined by common attributes and constraints. In ifcJSON schema, each IFC entity has a “properties” keyword that lists its attributes following JSON schema convention
    - In IFC specification two types of constraints is applied on attributes
      - First constraint which is the most general constraint is about the existence of attribute values: mandatory and optional attributes.
      - Second constraint that is applied on attributes in IFC specification is for aggregation data types such as Set, List, or Array, known as the existence constraint or cardinality constraints which is often refined by a minimal and maximal number of elements
- ifcJSON documents
  - An ifcJSON document is the exchange data for ifcJSON and should be validated against ifcJSON4 schema. The ifcJSON document consist of objects or an array of objects that represent IFC entity instances and its structure is defined by ifcJSON4 schema. Each data element that can be exchanged within an SPF file, can also be exchanged within an ifcJSON document.
  - Entity instance encoding
    - In EXPRESS, when encoding an SPF file, each entity instances are represented by an entity name which is encoded as a number sign “#” followed by a sequence of digit characters represented as a number. In this ifcJSON4 schema, “instanceId” property is defined to keep track of the instance references.
    - In JSON Schema, the “id” keyword defines a URI for the schema and subschemas can use “id” too to give themselves a document-local identifier
    - In ifcJSON schema developed in this paper, the “instanceId” keyword refers to the entity instances of the SPF file to provide the capabilities of translating JSON document to SPF file.
- Data validation
  - The ifcJSON documents developed in this paper, should be proved to be complete and well-formed. Therefore, this document needs to be validated with regard to two aspects: firstly, to check syntactic-based constraint according to JSON data formatting and secondly, for structural constraints defined in ifcJSON4 schema.
  - ifcJSON data validation for formatting
    - In order to validate ifcJSON data for formatting, this paper uses a JSON validator (e.g. http://jsonlint.com/) to validate the JSON data for correctness. This helps debugging JSON data and reports failure if the document is not well-formed due to incorrect JSON syntax. This validation technique should be applied to JSON document and also to ifcJSON4 schema which is a JSON document itself.
  - ifcJSON schema validation
    - JSON schema is used to validate the structure and data types of a piece of JSON. To validate the ifcJSON4 schema against current JSON schema, two approaches can be used.
      - This study uses the “JSON Schema Lint” which is a JSON schema validator to help write and test any JSON Schema that conform with the JSON schema Draft V4 specification.
      - An alternative approach is to use the methodology explained in Section 5.3.3. Since the ifcJSON4 Schema is an ifcJSON document itself, the methodology can be used to validate the ifcJSON4 schema against the main JSON schema draft V4.
    - In this paper, both of these approaches is applied for the schema validation.
  - ifcJSON data validation against ifcJSON4 schema
    - For validating the ifcJSON documents against the ifcJSON4 schema, JSON Schema validators should be used. There are some implementations of JSON Schema validators with specific functionalities. In this paper, “ajv” is used which is licensed by MIT and is available on GitHub that is an open source JSON schema validator for both node.js and browser. It implements full JSON schema draft V4 standard. ajv generates code to turn JSON schemas into JavaScript functions

## Use case approach
- the use case in this paper is the exchange model EMPC1 [32] in the precast concrete National BIM Standard. More specifically, a precast concrete column is used shown in Fig. 8
- ifcJSON4 schema and the ifcJSON document for this exchange model is described here for four data categories in the following Sections that respectively indicate the geometry data representation, object placement data, owner history data and the building element data for a precast concrete column that includes these three data categories.
<img src="https://ars.els-cdn.com/content/image/1-s2.0-S0926580517300316-gr8_lrg.jpg" class="post_img" style="width:70%;">

- Geometry representation data
  - For the ease of schema representation in this paper, the geometry representation entities in the ifcJSON4 schema have been limited to the entities required for the use case here. In IFC EXPRESS schema, IfcProductDefinitionShape.Representations is a list of IfcRepresentation entities.
  - Geometry data content
- Product placement data
  - In the IFC4 EXPRESS schema, product occurrences can be placed in 3D space relative to where they are contained. Placement is defined by a relative position (X, Y, Z coordinates), a horizontal reference direction, and a vertical axis direction
  - Placement data content
- Owner history data
  - In the IfcRoot which is the most abstract and root class for all IFC entity definitions, ownership is captured in “OwnerHistory” attribute using IfcOwnerHistory. OwnerHistory assigns the information about the current ownership of that object, such as owning actor and application
  - Owner history data content
- Precast column
  - The building element used in this use case is a precast column. In the IFC specification, a column is represented by either IfcColumnStandardCase or IfcColumn mostly used for columns with changing profile sizes along the extrusion
  - Precast column data content

## Results and discussions
<img src="https://ars.els-cdn.com/content/image/1-s2.0-S0926580517300316-gr9_lrg.jpg" class="post_img" style="width:80%;">
<img src="https://ars.els-cdn.com/content/image/1-s2.0-S0926580517300316-gr10_lrg.jpg" class="post_img" style="width:80%;">

## Limitations
- Similar to the limitations of ifcXML Schema [8] the ifcJSON Schema in this paper does not contain “Inverse” relationships and “derived attributes” that an EXPRESS schema can include. However, the implementation of JSON “$ref” keyword as shown in the above examples, can ensure the “Inverse” relationships in practice.
- Another limitation of the ifcJSON4 implementation in this paper is with regard to the uniqueness of GUIDs and also instanceIds. Generally, it is not possible to check the uniqueness of properties such as instanceIds and GUIDs in JSON schema. This paper recommends that the functionality of checking the uniqueness of values should be implemented as an added function in JavaScript code or an array of IDs.
- Additionally, there is currently no tools available that can visualize geometry data in ifcJSON. Therefore, for visualization purposes this study translates the ifcJSON document to SPF so that the data can be represented in model viewer tools.

## Conclusion
- This paper introduced ifcJSON and demonstrated that IFC Schema should and can be implemented in JSON format. JSON as a lightweight data exchange format has been proved to have higher parsing efficiency than XML and has been successful to replace XML in JavaScript-based web applications especially in AJAX applications.
- Most importantly, the study demonstrated that ifcJSON4 schema is a well-formed and valid JSON schema and the ifcJSON documents that can be generated based on ifcJSON4 schema are valid JSON documents.
- In fact, the major contribution of this paper is that ifcJSON is going to push the standardization efforts forward. Data exchange is a very important issue for making service based computing (i.e. Cloud computing) more efficiently and JSON data format supports high scalability.Therefore,ifcJSONdeveloped in this paper is anticipated to be widely used in Cloud-based Building Information Modeling solutions to improve interoperability of Cloud-BIM applications
- This standardization effort can be done by using IFC schema as the industry established open standard and JSON as an open standard and language independent data format.
- The result of this study has a major impact on interoperability of Webbased BIM applications by unifying BIM data representation based on both AEC industry standard.
- Recommendations and future work
  - the authors recommend that the ifcJSON implementation described in this paper, after further assessment, to be seriously considered for the full generation of the whole IFC schema in order to be added as a buildingSMART standards.
  - this study recommends to develop a methodology to generate ifcJSON from IFC EXPRESS automatically considering the methodology described in this paper. Also, an automated translation process for mapping between IFC SPF file and ifcJSON document would facilitate the translation of IFC data from EXPRESS to JSON.
  - Since the visualization of JSON geometry data is not possible within current applications, this study recommends current tools to add JSON functionalities to their application to be capable of using ifcJSON both on server and client side. This will facilitate the representation of ifcJSON geometry and attributes directly without the need to translate to EXPRESS.
  - it would be useful if application developers develop methodologies to convert their native bindings to ifcJSON directly without the need to use IFC EXPRESS data.
  - Future work should investigate the ifcJSON implementation for the relationships and property definitions in the IFC data model. Three fundamental entity types in the IFC model are object definitions, relationships and property definitions and in this paper, the ifcJSON representation is implemented only for object definition.
  - Similar to the tools that exist for the validation of the IFC SPF file against a specific MVD, future work needs to outline the methodologies for a validation technique that can check the validity of the ifcJSON document against the MVD requirements.
  - Future studies need to outline how JSON-LD constraints can be implemented in ifcJSON to introduce ifcJSON-LD schema and documents
  - it is anticipated that future study will deploy the ifcJSON developed in this paper for precast concrete in a Web application that uses ifcJSON resources for exchanging data within a structured framework.
