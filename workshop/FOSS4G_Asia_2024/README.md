# FOSS4G Asia 2024 Half-day workshop (15 Dec. 9:30-13:00), 
## Title: An introduction to OGC API–Moving Features with pygeoapi and MobilityDB

Reference: https://foss4g.asia/2024/workshop-list/

Moving feature data can represent a variety of phenomena, including vehicles, people, animals, weather patterns, and more. Conceptually, moving features are dynamic geospatial data that change location and possibly other characteristics over time. Most real-world objects can be represented as moving features, so it's important to have a structured way to represent them. Since most real-world objects can be represented as moving features, having a structured representation of moving features and using them in a standardized way is critical for application services.

OGC API–Moving Features–Part 1:Core (OGC API–MF) provides a standard and interoperable way to manage moving features data, which has valuable applications in transportation management, disaster response, environmental monitoring, and beyond. OGC API–MF also provides operations for filtering, sorting, and aggregating moving feature data based on location, time, and other properties. 

This workshop will get you started with OGC API–MF and open source-based implementations that address the following questions:

* What is the core concept of OGC API–MF (and OGC MF-JSON)?
* How do we implement OGC API–MF with pygeoapi and MobilityDB?
* How can we verify that OGC API–MF works properly with test codes?
* How can we visualize its results with STINUUM?

## Workshop schedule [Total 210 mins]

- [10 mins] Introduction of OGC Moving Features SWG
- [50 mins] What is the core concept of OGC API – MF (and OGC MF-JSON format) 
  - [40 mins] Explain OGC MF-JSON encoding and OGC API – MF design details. 
  - [10 mins] Introduce open sources related to MF-JSON and API – MF 
- [15 mins] Coffee Break
- [60 mins] How to implement OGC API – MF with pygeoapi and MobilityDB
  - [5 mins] A brief explanation of pygeoapi and install it (using Docker)
  - [10 mins] A brief explanation of MobilityDB and its functionality 
  - [15 mins] Describe how to extend pygeoapi to support OGC API – MF (with MobilityDB) 
  - [30 mins] Verify each API works properly using Swagger
- [15 mins] Coffee Break
- [60 mins] How can we visualize OGC moving features with STINUUM
  - [10 mins] A brief explanation of STINUUM and install it
  - [10 mins] Explain how to extend STINUUM using the MF-JSON
  - [20 mins] Practice visualization with different types of MF-JSON files
  - [20 mins] Connect with the installed pygeoapi to practice APIs (Post an existing MF-JSON file and visualize it)

The below open sources will be used in this workshop:
- *Server*: pygeoapi for supporting OGC API – MF, https://github.com/aistairc/pygeoapi-mf-api  
- *Database*: MobilityDB (and its Python driver, PyMEOS), https://github.com/MobilityDB 
- *Web Client*: STINUUM, https://github.com/aistairc/mf-cesium 

Each program will be installed using a Docker file.

Lastly, you can check many helpful information about OGC API – Moving Features here:
https://github.com/opengeospatial/ogcapi-movingfeatures
