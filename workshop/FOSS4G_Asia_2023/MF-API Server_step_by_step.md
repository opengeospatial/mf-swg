# FOSS4G 2023 Workshop (How-to-implement-OGC-API)
Reference: https://github.com/ogi-ts-shimizu/FOSS4G2023Workshop_How-to-implement-OGC-API/blob/main/README.md

Additional material of the FOSS4G 2023 Seoul Half-day workshop <OGC API – MF, an introduction with MF-API Server based on pygeoapi and MobilityDB> "3. How to implement OGC API – MF with pygeoapi and MobilityDB?" section

Each section describes the commands and sample data used.

## Recommended PC specifications
- [x] HDD：At least 20GB free space
- [x] memory >= 6GB
- [x] Install **Docker** on local PC (https://www.docker.com/get-started)
- [x] (optional) Database Viewer **DBeaver** (https://dbeaver.io/)

---
## [5 mins] A brief explanation of pygeoapi (overall architecture, etc.) and install MF-API Server (using Docker)
Execute the following three commands in order at the command prompt

Step1
```bash
docker pull ghcr.io/taehoonk/mf-api-server:1.1
```

Step2
```bash
docker run -p 8085:8085 -p 25432:5432 -d --name mf-api-server ghcr.io/taehoonk/mf-api-server:1.1
```

Step3
```bash
docker exec mf-api-server ./run.sh
```

---
## [10 mins] A brief explanation of MobilityDB and the functions (and structure) used to handle TemporalGeometry and properties.
> [!NOTE] 
> * There are no commands or data to use.
---
## [20 mins] Describe how you extended pygeoapi to support OGC API – MF (libraries to use OpenAPI and MobilityDB (pyMEOS, python-mobilitydb, etc.) and extension structure, etc.)
> [!NOTE] 
> * There are no commands or data to use.
---
## [30 mins] Verify that each API works properly using Swagger
## MovingFeatureCollection
### No.1
#### **[POST]** MovingFeatureCollection
- Request body(application/json)
```json
{
  "title": "moving_feature_collection_sample1",
  "updateFrequency": 1000,
  "description": "FOSS4G2023 Seoul Workshop"
}
```
---
### No.2
#### **[GET]** MovingFeatureCollection
- collectionID
> [!NOTE] 
> * The last part of `location` link when POST response
![image](https://github.com/ogi-ts-shimizu/FOSS4G2023Workshop_How-to-implement-OGC-API/assets/120169253/934a7555-a796-4289-a7bf-a18d4c962204)
---
### No.3
#### **[PUT]** MovingFeatureCollection
- collectionID : The last part of `location` link when POST response
- Request body(application/json)
```json
{
  "title": "moving_feature_collection_sample2",
  "updateFrequency": 1000,
  "description": "FOSS4G2023 Seoul Workshop PUT test"
}
```
---
### No.4
#### **[DELETE]** MovingFeatureCollection
> [!NOTE] 
> Skip the DELETE request for the next demonstration

---
## MovingFeature
### No.5
#### **[POST]** MovingFeatures
- collectionID : ID of the response at the time of **MovingFeatureCollection**
- Request body(application/json) : 
```json
{
  "type": "Feature",
  "crs": {
    "type": "Name",
    "properties": {
      "name": "urn:ogc:def:crs:OGC:1.3:CRS84"
    }
  },
  "trs": {
    "type": "Link",
    "properties": {
      "type": "OGCDEF",
      "href": "http://www.opengis.net/def/uom/ISO-8601/0/Gregorian"
    }
  },
  "temporalGeometry": {
    "type": "MovingPoint",
    "datetimes": [
      "2011-08-14T22:10:00Z",
      "2011-08-14T22:20:00Z",
      "2011-08-14T22:30:00Z",
      "2011-08-14T22:40:00Z",
      "2011-08-14T23:00:00Z"
    ],
    "coordinates": [
      [
        139.757083,
        35.627701,
        0.5
      ],
      [
        139.757399,
        35.627701,
        2
      ],
      [
        139.757555,
        35.627688,
        4
      ],
      [
        139.757651,
        35.627596,
        4
      ],
      [
        139.757716,
        35.627483,
        4
      ]
    ],
    "interpolation": "Linear",
    "base": {
      "type": "glTF",
      "href": "http://www.opengis.net/spec/movingfeatures/json/1.0/prism/example/car3dmodel.gltf"
    },
    "orientations": [
      {
        "scales": [
          1,
          1,
          1
        ],
        "angles": [
          0,
          0,
          0
        ]
      },
      {
        "scales": [
          1,
          1,
          1
        ],
        "angles": [
          0,
          355,
          0
        ]
      },
      {
        "scales": [
          1,
          1,
          1
        ],
        "angles": [
          0,
          0,
          330
        ]
      },
      {
        "scales": [
          1,
          1,
          1
        ],
        "angles": [
          0,
          0,
          300
        ]
      },
      {
        "scales": [
          1,
          1,
          1
        ],
        "angles": [
          0,
          0,
          270
        ]
      }
    ]
  },
  "temporalProperties": [
    {
      "datetimes": [
        "2011-08-14T22:10:00Z",
        "2011-08-14T22:30:00Z",
        "2011-08-14T23:00:00Z"
      ],
      "length": {
        "type": "Measure",
        "form": "http://www.qudt.org/qudt/owl/1.0.0/quantity/Length",
        "values": [
          1,
          2.4,
          1
        ],
        "interpolation": "Linear"
      },
      "discharge": {
        "type": "Measure",
        "form": "MQS",
        "values": [
          3,
          4,
          5
        ],
        "interpolation": "Step"
      }
    },
    {
      "datetimes": [
        1465621816590,
        1465711526300
      ],
      "camera": {
        "type": "Image",
        "values": [
          "http://www.opengis.net/spec/movingfeatures/json/1.0/prism/example/image1",
          "iVBORw0KGgoAAAANSUhEU......"
        ],
        "interpolation": "Discrete"
      },
      "labels": {
        "type": "Text",
        "values": [
          "car",
          "human"
        ],
        "interpolation": "Discrete"
      }
    }
  ],
  "geometry": {
    "type": "LineString",
    "coordinates": [
      [
        139.757083,
        35.627701,
        0.5
      ],
      [
        139.757399,
        35.627701,
        2
      ],
      [
        139.757555,
        35.627688,
        4
      ],
      [
        139.757651,
        35.627596,
        4
      ],
      [
        139.757716,
        35.627483,
        4
      ]
    ]
  },
  "properties": {
    "name": "car1",
    "state": "test1",
    "video": "http://www.opengis.net/spec/movingfeatures/json/1.0/prism/example/video.mpeg"
  },
  "bbox": [
    139.757083,
    35.627483,
    0,
    139.757716,
    35.627701,
    4.5
  ],
  "time": [
    "2011-08-14T22:00:00Z",
    "2011-08-14T23:00:00Z"
  ]
}

```

---

### No.5-2
#### **[POST]** MovingFeatures
- collectionID : ID of the response at the time of **MovingFeatureCollection**
- Request body(application/json) : 
```json
{
  "type": "Feature",
  "crs": {
    "type": "Name",
    "properties": {
      "name": "urn:ogc:def:crs:OGC:1.3:CRS84"
    }
  },
  "trs": {
    "type": "Link",
    "properties": {
      "type": "OGCDEF",
      "href": "http://www.opengis.net/def/uom/ISO-8601/0/Gregorian"
    }
  },
  "temporalGeometry": {
    "type": "MovingPoint",
    "datetimes": [
      "2012-07-14T22:00:00Z",
      "2012-07-14T22:10:00Z",
      "2012-07-14T22:20:00Z",
      "2012-07-14T22:30:00Z",
      "2012-07-14T22:40:00Z"
    ],
    "coordinates": [
      [
        138.757083,
        34.627701,
        0.5
      ],
      [
        138.757399,
        34.627701,
        2
      ],
      [
        138.757555,
        34.627688,
        4
      ],
      [
        138.757651,
        34.627596,
        4
      ],
      [
        138.757716,
        34.627483,
        4
      ]
    ],
    "interpolation": "Linear",
    "base": {
      "type": "glTF",
      "href": "http://www.opengis.net/spec/movingfeatures/json/1.0/prism/example/car3dmodel.gltf"
    },
    "orientations": [
      {
        "scales": [
          1,
          1,
          1
        ],
        "angles": [
          0,
          0,
          0
        ]
      },
      {
        "scales": [
          1,
          1,
          1
        ],
        "angles": [
          0,
          355,
          0
        ]
      },
      {
        "scales": [
          1,
          1,
          1
        ],
        "angles": [
          0,
          0,
          330
        ]
      },
      {
        "scales": [
          1,
          1,
          1
        ],
        "angles": [
          0,
          0,
          300
        ]
      },
      {
        "scales": [
          1,
          1,
          1
        ],
        "angles": [
          0,
          0,
          270
        ]
      }
    ]
  },
  "temporalProperties": [
    {
      "datetimes": [
        "2011-07-14T22:00:00Z",
        "2011-07-14T22:30:00Z",
        "2011-07-14T23:00:00Z"
      ],
      "length": {
        "type": "Measure",
        "form": "http://www.qudt.org/qudt/owl/1.0.0/quantity/Length",
        "values": [
          1,
          2.4,
          1
        ],
        "interpolation": "Linear"
      },
      "discharge": {
        "type": "Measure",
        "form": "MQS",
        "values": [
          3,
          4,
          5
        ],
        "interpolation": "Step"
      }
    },
    {
      "datetimes": [
        1465621816590,
        1465711526300
      ],
      "camera": {
        "type": "Image",
        "values": [
          "http://www.opengis.net/spec/movingfeatures/json/1.0/prism/example/image1",
          "iVBORw0KGgoAAAANSUhEU......"
        ],
        "interpolation": "Discrete"
      },
      "labels": {
        "type": "Text",
        "values": [
          "car",
          "human"
        ],
        "interpolation": "Discrete"
      }
    }
  ],
  "geometry": {
    "type": "LineString",
    "coordinates": [
      [
        138.757083,
        34.627701,
        0.5
      ],
      [
        138.757399,
        34.627701,
        2
      ],
      [
        138.757555,
        34.627688,
        4
      ],
      [
        138.757651,
        34.627596,
        4
      ],
      [
        138.757716,
        34.627483,
        4
      ]
    ]
  },
  "properties": {
    "name": "car1",
    "state": "test1",
    "video": "http://www.opengis.net/spec/movingfeatures/json/1.0/prism/example/video.mpeg"
  },
  "bbox": [
    138.757083,
    34.627483,
    0,
    138.757716,
    34.627701,
    4.5
  ],
  "time": [
    "2012-07-14T22:00:00Z",
    "2012-07-14T23:00:00Z"
  ]
}

```

---

### No.6
#### **[GET]** MovingFeatures (/collections/{collectionId}/items)
- collectionID : ID of the response at the time of **MovingFeatureCollection**
- bbox : Empty
- datetime : ```2011-08-14T22:20:00Z```
- limit : 10
- subTrajectory : --

---
### No.6-2
#### **[GET]** MovingFeatures (/collections/{collectionId}/items)
- collectionID : ID of the response at the time of **MovingFeatureCollection**
- bbox : ```138.757083```
         ```34.627483```
         ```138.757716```
         ```34.627701```
- datetime : ```2010-01-01T00:00:00Z/..```
- limit : 10
- subTrajectory : --

---
### No.6-3
#### **[GET]** MovingFeatures (/collections/{collectionId}/items)
- collectionID : ID of the response at the time of **MovingFeatureCollection**
- bbox : Empty
- datetime : ```2011-08-14T22:15:00Z/2011-08-14T22:55:00Z```
- limit : 10
- subTrajectory : true

---
### No.7
#### **[GET]** MovingFeatures (/collections/{collectionId}/items/{mFeatureId})
- collectionId : ID of the response at the time of **MovingFeatureCollection**
- mFeatureId : ID of the response at the time of **MovingFeature**

> [!NOTE]
> The last part of `location` link when MovingFeatures POST response
![image](https://github.com/ogi-ts-shimizu/FOSS4G2023Workshop_How-to-implement-OGC-API/assets/120169253/c609d523-6f45-40b8-aec1-9b6903a8797f)
---
### No.8
#### **[DELETE]** MovingFeatures (/collections/{collectionId}/items/{mFeatureId})
> [!NOTE] 
> Skip the DELETE request for the next demonstration
---
## TemporalGeometryCollection
### No.9
#### **[POST]** TemporalGeometry(/collections/{collectionId}/items/{mFeatureId}/tgsequence)
- collectionId : ID of the response at the time of **MovingFeatureCollection**
- mFeatureId : ID of the response at the time of **MovingFeatures**
- Request body(application/json) : **Default Value**

---
### No.10
#### **[GET]** TemporalGeometry(/collections/{collectionId}/items/{mFeatureId}/tgsequence)
- collectionId : ID of the response at the time of **MovingFeatureCollection**
- mFeatureId : ID of the response at the time of **MovingFeatures**
- leaf : ```2011-08-14T22:30:00Z```
- bbox : Empty
- datetime : ```2010-01-01T00:00:00Z/..```
- limit : 10

---
### No.10-2
#### **[GET]** TemporalGeometry(/collections/{collectionId}/items/{mFeatureId}/tgsequence)
- collectionId : ID of the response at the time of **MovingFeatureCollection**
- mFeatureId : ID of the response at the time of **MovingFeatures**
- leaf : Empty
- bbox : Empty
- datetime : ```2011-08-14T22:15:00Z/2011-08-14T22:55:00Z```
- limit : 10
- subTrajectory : true

---
### No.11
#### **[DELETE]** TemporalGeometry(/collections/{collectionId}/items/{mFeatureId}/tgsequence/{tGeometryId})
- collectionId : ID of the response at the time of **MovingFeatureCollection**
- mFeatureId : ID of the response at the time of **MovingFeatures**
- tGeometryId : ID of the response at the time of **TemporalGeometry**

> [!NOTE] 
> * The last part of `location` link when POST response
![image](https://github.com/ogi-ts-shimizu/FOSS4G2023Workshop_How-to-implement-OGC-API/assets/120169253/d394eedd-efbe-4c97-845a-e5e909d4dd4b)

---
## TemporalProperties
### No.12
#### **[POST]** TemporalProperties(/collections/{collectionId}/items/{mFeatureId}/tproperties)
- collectionId : ID of the response at the time of **MovingFeatureCollection**
- mFeatureId : ID of the response at the time of **MovingFeatures**
- Request body(application/json)  : 
```json
{
  "temporalProperties": [
    {
      "datetimes": [
        "2015-07-14T22:01:01.450Z",
        "2015-07-14T23:01:01.450Z",
        "2015-07-15T00:01:01.450Z"
      ],
      "length": {
        "type": "Measure",
        "form": "http://www.qudt.org/qudt/owl/1.0.0/quantity/Length",
        "values": [
          1,
          2.4,
          1
        ],
        "interpolation": "Linear"
      },
      "discharge": {
        "type": "Measure",
        "form": "MQS",
        "values": [
          3,
          4,
          5
        ],
        "interpolation": "Step"
      }
    },
    {
      "datetimes": [
        1466380800000,
        1466383800000
      ],
      "camera": {
        "type": "Image",
        "values": [
          "http://www.opengis.net/spec/movingfeatures/json/1.0/prism/example/image1",
          "iVBORw0KGgoAAAANSUhEU......"
        ],
        "interpolation": "Discrete"
      },
      "labels": {
        "type": "Text",
        "values": [
          "car",
          "human"
        ],
        "interpolation": "Discrete"
      }
    }
  ]
}

```
---
### No.13
#### **[GET]** TemporalProperties(/collections/{collectionId}/items/{mFeatureId}/tproperties/)
- collectionId : ID of the response at the time of **MovingFeatureCollection**
- mFeatureId : ID of the response at the time of **MovingFeatures**
- leaf : Empty
- datetime : ```2011-08-14T22:15:00Z/2011-08-14T22:55:00Z```
- limit : 10
- subTemporalValue : true

---
### No.14
#### **[GET]** TemporalProperty(/collections/{collectionId}/items/{mFeatureId}/tproperties/{tPropertyName})
- collectionId : ID of the response at the time of **MovingFeatureCollection**
- mFeatureId : ID of the response at the time of **MovingFeatures**
- tPropertyName : length
- leaf : Empty
- datetime :  ```2010-01-01T00:00:00Z/..```
- subTemporalValue : true

---
### No.15
#### **[POST]** TemporalProperty(/collections/{collectionId}/items/{mFeatureId}/tproperties/{tPropertyName})
- collectionId : ID of the response at the time of **MovingFeatureCollection**
- mFeatureId : ID of the response at the time of **MovingFeatures**
- tPropertyName : length
- Request body(application/json) :
```json
{
  "datetimes": [
    "2011-12-15T08:00:00Z",
    "2011-12-15T08:10:00Z",
    "2011-12-15T08:20:00Z"
  ],
  "values": [
    0,
    20,
    50
  ],
  "interpolation": "Linear"
}
```

---
### No.16
#### **[DELETE]** TemporalProperty(/collections/{collectionId}/items/{mFeatureId}/tproperties/{tPropertyName})
- collectionId : ID of the response at the time of **MovingFeatureCollection**
- mFeatureId : ID of the response at the time of **MovingFeatures**
- tPropertyName : length

---
## References
- MF-API Server based on pygeoapi: https://github.com/aistairc/mf-api
- OGC API – MovingFeatures official GitHub repository: https://github.com/opengeospatial/ogcapi-movingfeatures
- MobilityDB (and its Python driver, PyMEOS, and MEOS): https://github.com/MobilityDB
- STINUUM（The installation of each program will use a Docker file.）: https://github.com/aistairc/mf-cesium
- OGC API – MF: https://ogcapi.ogc.org/movingfeatures/