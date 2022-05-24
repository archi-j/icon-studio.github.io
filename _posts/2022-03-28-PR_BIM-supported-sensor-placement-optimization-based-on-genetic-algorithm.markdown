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
- ifcJSON4 implementation approach
- ifcJSON4 application and evaluation
- Implementation challenges and limitations

## Data model mapping
- ifcJSON4 schema
  - Implementing IFC types and entities
  - Attributes implementation
- ifcJSON documents
  - Entity instance encoding
- Data validation
  - ifcJSON data validation for formatting
  - ifcJSON schema validation
  - ifcJSON data validation against ifcJSON4 schema

## Use case approach
- Geometry representation data
  - Geometry data content
- Product placement data
  - Placement data content
- Owner history data
  - Owner history data content
- Precast column
  - Precast column data content

## Results and discussions

## Limitations

## Conclusion
- Recommendations and future work
