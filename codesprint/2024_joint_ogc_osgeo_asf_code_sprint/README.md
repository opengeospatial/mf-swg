# 2024 Joint OGC – OSGeo – ASF Code Sprint, OGC API  – Moving Features Activity
## Overview
The OGC Moving Features SWG will participate in the [2024 Joint OGC – OSGeo – ASF Code Sprint (2024 Feb. 26 - 28)](https://opengeospatial.github.io/dev-ogc-sprint-landing-23/).

If you want to get more information about this code sprint, please refer to the [event wiki page](https://github.com/opengeospatial/developer-events/wiki/2024-Joint-OGC-%E2%80%93-OSGeo-%E2%80%93-ASF-Code-Sprint). 

We will be working primarily on the [OGC API - Moving Feature](https://ogcapi.ogc.org/movingfeatures/), but if it's related to moving features, we'd love to hear from you.

This page summarizes the goal, schedule, and outcomes of the activities related to the code sprint. 


## Tasks
In this code sprint, OGC Moving Features SWG will cover the following tasks:

*Documentation*
- Validation against the designed [Core APIs](https://opengeospatial.github.io/ogcna-auto-review/22-003.html#toc13)
- Validation of the designed APIs against the [Abstract Test Suite (ATS)](https://opengeospatial.github.io/ogcna-auto-review/22-003.html#toc36)

*Development*
- Further implementation of APIs not supported by [MF-API Server](https://github.com/aistairc/mf-api) (queryable API part)
- Refactoring the MF-API server to the latest [pygeoapi](https://github.com/geopython/pygeoapi).
- Add OGC API - Moving Features as one of [pygeoapi's providers](https://docs.pygeoapi.io/en/stable/data-publishing/index.html#providers-overview)

And AOB!

### On-site OGC API - Moving Features member
If you have any questions about the OGC API - Moving Features during the code sprint, feel free to ask us!

* Taehoon Kim (Co-editor of the OGC API - Moving Features), [✉️](mailto:kim.taehoon@aist.go.jp), discord: @taehoonkim5747
* Wijae Cho (Developer), [✉️](mailto:cho-wijae@aist.go.jp), discord: @WijaeCho#3486

### [Note] Previous workshop materials
If you're new to OGC API - Moving Features, we recommend reading the [materials from the previous workshop](https://github.com/opengeospatial/mf-swg/tree/main/workshop/FOSS4G_Asia_2023). 

It includes tutorials using [MF-API Server](https://github.com/aistairc/mf-api) and [STINUUM (web client)](https://github.com/aistairc/mf-cesium/tree/mf-cesium_api), so you can easily and quickly get started with OGC API - Moving Features!

## Schedule
The code sprint will be held on Western European Time (WET/UTC/GMT). 

You can check [here](https://www.timeanddate.com/worldclock/meetingtime.html?day=26&month=2&year=2024&p1=224&p2=179&p3=16&p4=44&p5=240&p6=136&iv=0) the time in other locations.  

This is the schedule for the main track.

| Date       | Time          | Day/ Activity                           | Discord channel                                             |
|------------|---------------|-----------------------------------------|-------------------------------------------------------------|
| 2024-02-20 |               | **Day #0 (pre-event): Welcome Webinar** |                                                             |
|            | 14:00 - 15:00 | Pre-event webinar                       | V:🏛 [#Main Stage](https://discord.gg/3pezeR98Ks)           |
| 2024-02-26 |               | **Day #1: Kick-Off**                    |                                                             |
|            | 09:00 - 10:00 | Welcome session                         | V:🏛 [#Main Stage](https://discord.gg/3pezeR98Ks)           |
|            | 10:00 - 12:30 | Introduce OGC API - Moving Features     | On-site                                                     |
|            | 12:30 - 13:30 | Lunch                                   | 🍜                                                          |
|            | 13:30 - 17:00 | Additional implementation of APIs       | On-site                                                     |
|            | 17:00 - 18:00 | Early dinner                            | 🍜                                                          |
|            | 18:00 - 20:00 | Additional implementation of APIs       | On-site                                                     |
|            | 20:00 - 21:00 | Daily Brief Back                        | V:🏛 [#Main Stage](https://discord.gg/3pezeR98Ks)           |
| 2024-02-27 |               | **Day #2**                              |                                                             |
|            | 09:00 - 10:00 | Additional implementation of APIs       | On-site                                                     |
|            | 10:00 - 10:30 | Stand-up                                | V:🏛 [#Main Stage](https://discord.gg/3pezeR98Ks)           |
|            | 10:30 - 12:30 | Additional implementation of APIs       | On-site                                                     |
|            | 12:30 - 13:30 | Lunch                                   | 🍜                                                          |
|            | 13:30 - 17:00 | Refactoring the MF-API server           | On-site                                                     |
|            | 17:00 - 18:00 | Early dinner                            | 🍜                                                          |
|            | 18:00 - 20:00 | Refactoring the MF-API server           | On-site                                                     |
|            | 20:00 - 21:00 | Daily Brief Back                        | V:🏛 [#Main Stage](https://discord.gg/3pezeR98Ks)           |
| 2024-02-28 |               | **Day #3: Final Day**                   |                                                             |
|            | 09:00 - 10:00 | Refactoring the MF-API server           | On-site                                                     |
|            | 10:00 - 10:30 | Stand-up                                | V:🏛 [#Main Stage](https://discord.gg/3pezeR98Ks)           |
|            | 10:30 - 13:00 | Refactoring the MF-API server           | On-site                                                     |
|            | 13:00 - 14:00 | Lunch                                   | 🍜                                                          |
|            | 14:00 - 15:00 | Preparing Demo                          | On-site                                                     |
|            | 15:00 - 17:00 | Demos & Wrap-up                         | V::📣 [GotoMeet](http://www.gotomeeting.com/join/570724997) |

## Project and Working Group Pitches

[![Video](https://img.youtube.com/vi/bFOj7U44CpU/0.jpg)](https://www.youtube.com/embed/bFOj7U44CpU?si=FJfYgJOxcNpYeI9u)

## Daily Summary Report
### 24-02-26
- (ongoing) Further implementation of APIs not supported by [MF-API Server](https://github.com/aistairc/mf-api) (queryable API part)
  - [The TemporalGeometry Query Resources](https://opengeospatial.github.io/ogcna-auto-review/22-003.html#_3dd02e21-5ed6-4ad3-bbb4-098f18e0a04d) need to be implemented.
  - We try to implement three functions (Distance, Velocity, and Acceleration) using MobilityDB functions
  - [x] Distance: Using [cumulativeLength](https://mobilitydb.github.io/MobilityDB/master/ch08s04.html) function
  - [x] Velocity: Using [speed](https://mobilitydb.github.io/MobilityDB/master/ch08s04.html) function
  - [ ] Acceleration: NOT YET IMPLEMENTED 
  - Extend OpenAPI file (*.yml) for the [queryable APIs](https://opengeospatial.github.io/ogcapi-movingfeatures/openapi/openapi-movingfeatures-1.html#tag/TemporalGeometryQuery)
  - Result: [Commit](https://github.com/aistairc/mf-api/commit/357eb2c802ddf251d7b0e55df9d6486d179c3d8f)
### 24-02-27
TBD
### 24-02-28
TBD