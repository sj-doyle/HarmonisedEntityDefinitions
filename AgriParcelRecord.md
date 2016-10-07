### AgriParcelRecord

This entity contains a harmonised description of the conditions recorded on a generic parcel of land. This entity is primarily associated with the agricultural vertical and related IoT applications.

&lt;AgriParcelRecord&gt;&lt;Generic Attributes&gt;

| Attribute Name | Attribute Type | Description                                                                   | Mandatory /Optional | May be Null |
|----------------|----------------|-------------------------------------------------------------------------------|--------------------|-------------|
| id             | Text           | Unique id of this instance of this entity.                                    | M                  | N           |
| type           | Text           | Must be equal to "**AgriParcelRecord**".                                      | M                  | N           |
| dateCreated    | DateTime       | Entity creation timestamp.                                                    | M                  | N           |
| dateModified   | DateTime       | Timestamp of the last modification of the entity.                             | M                  | Y           |
| source         | Text           | A sequence of characters giving the source of the entity data as a URL.       | M                  | Y           |
| dataProvider   | Text           | A sequence of characters identifying the originator of the harmonised entity. | M                  | Y           |

&lt;AgriParcelRecord&gt;&lt;Entity Specific Attributes&gt;

| Attribute Name      | Attribute Type                | Description                                                                                       | Mandatory /Optional | May be Null |
|---------------------|-------------------------------|---------------------------------------------------------------------------------------------------|--------------------|-------------|
| refAgriParcel       | Reference                     | Unique id of the AgriParcel to which this record relates.                                         | M                  | N           |
| location            | geo:json                      | The geo:json encoded polygon of this AgriParcelRecord.                                            | M                  | N           |
| soilTemperature     | ExtQuantitativeValue (Number)  | The observed soil temperature in degrees centigrade encoded as a ExtQuantitativeValue.            | O                  | Y           |
| temperature         | ExtQuantitativeValue (Number)  | The observed air temperature in degrees centigrade encoded as a ExtQuantitativeValue.             | O                  | Y           |
| soilMoistureVwc     | ExtQuantitativeValue (Number)  | Measured as Volumetric Water Content, VWC as a percentage. <br/><br/> 0 ≤soilMoistureVwc ≤ 100          <br/><br/>encoded as a ExtQuantitativeValue                                                                  | O                  | Y           |
| soilMoistureEc      | ExtQuantitativeValue (Number)  | Measured as              <br/><br/>Electrical Conductivity, EC in units of Siemens per meter (S/m) encoded as a ExtQuantitativeValue  | O                  | Y           |
| solarRadiation      | ExtQuantitativeValue (Number) | Measured in kW/m<sup>2</sup> encoded as a ExtQuantitativeValue.                                   | O                  | Y           |
| relativeHumidity    | ExtQuantitativeValue (Number)  | Relative Humidity a number between 0 and 1 <br/><br/> 0 ≤ relativeHumidity ≤ 1 encoded as a ExtQuantitativeValue.                                        | O                  | Y           |
| atmosphericPressure | ExtQuantitativeValue (Number)  | Atmospheric Pressure in units of Hecto Pascal encoded as a ExtQuantitativeValue.                  | O                  | Y           |
| description         | Text                          | Description of this AgriParcelRecord.                                                             | O                  | Y           |

#### AgriParcelRecord JSON

The JSON code can be downloaded from:

<https://gist.github.com/GSMADeveloper/bc089529b7966099cd11bc0e2b0bb283>
```json
{
  "id": "8f5445e6-f49b-496e-833b-e65fc97fcab7",
  "type": "AgriParcelRecord",
  "dateCreated": {
    "value": "2016-08-22T10:18:16Z",
    "type": "DateTime"
  },
  "dateModified": {
    "value": "2016-08-22T10:18:16Z",
    "type": "DateTime"
  },
  "source": {
    "value": "http://www.samplefarmproduct.com",
    "type": "URL"
  },
  "dataProvider": {
    "value": "OperatorA",
    "type": "Text"
  },
  "refAgriParcel": {
    "value": "d3676010-d815-468c-9e01-25739c5a25ed",
    "type": "Reference"
  },
  "location": {
    "value": {
      "type": "Polygon",
      "coordinates": [
        [100,0],
        [101,0],
        [101,1],
        [100,1],
        [100,0]
      ]
    },
    "type": "geo:json"
  },
  "soilTemperature": {
    "value": {
      "value": 27,
      "unitCode": "CEL"
    },
    "type": "ExtQuantitativeValue"
  },
  "temperature": {
    "value": {
      "value": 33,
      "unitCode": "CEL"
    },
    "type": "ExtQuantitativeValue"
  },
  "soilMoistureVwc": {
    "value": {
      "value": 8,
      "unitCode": "P1"
    },
    "type": "ExtQuantitativeValue"
  },
  "soilMoistureEc": {
    "value": {
      "value": 17,
      "unitCode": "D10"
    },
    "type": "ExtQuantitativeValue"
  },
  "solarRadiation": {
    "value": {
      "value": 15,
      "unitCode": "N78"
    },
    "type": "ExtQuantitativeValue"
  },
  "relativeHumidity": {
    "value": {
      "value": 0.15
    },
    "type": "ExtQuantitativeValue"
  },
  "atmosphericPressure": {
    "value": {
      "value": 101325,
      "unitCode": "PAL"
    },
    "type": "ExtQuantitativeValue"
  },
  "description": {
    "value": "North greenhouse. Planting zone A ",
    "type": "Text"
  }
}
```
