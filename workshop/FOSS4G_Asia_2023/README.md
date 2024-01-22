# FOSS4G Asia 2023 Half-day workshop (28 Nov. 14:00-18:00), 
## Title: OGC API – MF, an introduction with MF-API Server based on pygeoapi and MobilityDB

Reference: https://foss4g.asia/2023/workshop-schedule/

Moving feature data can represent various phenomena, including vehicles, people, animals, weather patterns, and more. Conceptually, Moving Features are dynamic geospatial data that change location and possibly other characteristics over time.

OGC API – Moving Features (OGC API – MF) provides a standard and interoperable way to manage such data, with valuable applications in transportation management, disaster response, environmental monitoring, and beyond. OGC API – MF also includes operations for filtering, sorting, and aggregating moving feature data based on location, time, and other properties.

This workshop will get you started with OGC API – MF and its implementation in MF-API Server that is based on pygeoapi and MobilityDB, covering the following questions:

* What is the core concept of OGC API – MF (and OGC MF-JSON format)? 
* How to implement OGC API – MF with pygeoapi and MobilityDB? 
* How can we visualize its results with STINUUM (with CesiumJS)? 
* How can we implement a new feature that hasn’t been implemented yet?

## Workshop schedule [Total 220 mins]

- [10 mins] Introduction of OGC Moving Features SWG (Kyoungsook KIM)
- [50 mins] What is the core concept of OGC API – MF (and OGC MF-JSON format)? (Taehoon)
  - [40 mins] Explain OGC MF-JSON encoding and OGC API – MF design details.
  - [10 mins] Introduce open sources related to MF-JSON and API – MF (STINUUM, MobilityDB, movingPandas)
- [15 mins] Break
- [65 mins] How to implement OGC API – MF with pygeoapi and MobilityDB? (AppTech)
  - [5 mins] A brief explanation of pygeoapi (overall architecture, etc.) and install MF-API Server (using Docker)
  - [10 mins] A brief explanation of MobilityDB and the function (and structure) used to handle temporal geometry and properRes.
  - [20 mins] Describe how you extended pygeoapi to support OGC API – MF (libraries to use OpenAPI and MobilityDB (pyMEOS, python-mobilitydb, etc.) and extension structure, etc.)
  - [30 mins] Verify that each API works properly using Swagger.
- [15 mins] Break
- [65 mins] How can we visualize its results with STINUUM? (Taehoon & Wijae)
  - [10 mins] A brief explanation of STINUUM and install it (using Docker)
  - [15 mins] Explain how STINUUM can be extended using the OGC API – MF
  - [20 mins] Practice visualization with different types of MF-JSON files
  - [20 mins] Connect with the installed MF-API Server to practice APIs (Post an existing MF-JSON file and visualize it)

The below open sources will be used in this workshop:
- MF-API Server based on pygeoapi: https://github.com/aistairc/mf-api
- MobilityDB (and its Python driver, PyMEOS, and MEOS): https://github.com/MobilityDB
- STINUUM: https://github.com/aistairc/mf-cesium

The installation of each program will use a Docker file.
Lastly, you can check many helpful information about OGC API – MF here:
https://github.com/opengeospaRal/ogcapi-movingfeatures
