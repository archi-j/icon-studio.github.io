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
- So far, IFC specification is provided as EXPRESS and XSD definitions [5] and IFC data files that are being exchanged between applications use three main data formats including “.ifc” using the STEP physical file structure, “.ifcXML” using the eXtensible Markup Language (XML) document structure, and “.ifcZIP” using the PKzip 2.04 g compression algorithm
- buildingSMART International has implemented the IFC standard using XML technologies as ifcXML specification [8,9]. XML is a platform independent language for representing data and has been used in the development of web service applications.
- the performance of web services have shown a significant decrease when using XML data because of the low efficiency of reading and parsing XML data during the execution of services
- Initially, XML was used in a wide range of AJAX developments, but gradually XML showed inadequacies because its performance reduces significantly when it is applied to interactive pages. In order to address the issues of XMLbased services, AJAX decreases the server workload by applying JavaScript at the client side.
- JSON is a native data for JavaScript and this feature makes JSON a proper format to be used for data exchanging in AJAX applications [10]. JSON is a key-value style lightweight data exchange format which is independent of any programming language and unlike XML it is easy for machines to parse and generate while it is also human readable
- This paper highlights that there is a need to provide guidelines on how to translate IFC data to JSON to indicate how IFC schema can be represented as JSON specification. Therefore, in this paper the main objective is to outline that IFC specification can be represented in JSON format.
