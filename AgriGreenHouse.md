### AgriGreenHouse

This entity contains a harmonised description of the conditions recorded within a generic greenhouse, a type of AgriParcel. This entity is primarily associated with the agricultural vertical and related IoT applications.

&lt;AgriGreenHouse&gt;&lt;Generic Attributes&gt;

| Attribute Name | Attribute Type | Description                                                                   | Mandatory /Optional | May be Null |
|----------------|----------------|-------------------------------------------------------------------------------|--------------------|-------------|
| id             | Text           | Unique id of this instance of this entity.                                    | M                  | N           |
| type           | Text           | Must be equal to "**AgriGreenHouse**"                                         | M                  | N           |
| dateCreated    | DateTime       | Entity creation timestamp.                                                    | M                  | N           |
| dateModified   | DateTime       | Timestamp of the last modification of the entity.                             | M                  | Y           |
| source         | URL            | A sequence of characters giving the source of the entity data as a URL.       | M                  | Y           |
| dataProvider   | Text           | A sequence of characters identifying the originator of the harmonised entity. | M                  | Y           |

&lt;AgriGreenHouse&gt;&lt;Entity Specific Attributes&gt;

| Attribute Name          | Attribute Type                | Description                                                                                                | Mandatory /Optional | May be Null |
|-------------------------|-------------------------------|------------------------------------------------------------------------------------------------------------|--------------------|-------------|
| refAgriParcel           | Reference                     | Reference to the Unique id of the AgriParcel to which this record relates.                                 | M                  | N           |
| refWeatherObserved      | Reference                     | A JSON encoded sequence of characters that reference the unique id of the related weather observed record. | O                  | Y           |
| relativeHumidity        | ExtQuantitativeValue (Number) | The inside relative humidity expressed as a number between 0 and 1.<br/><br/>   0 ≤ relativeHumidity ≤ 1  <br/><br/>  Encoded as a ExtQuantitiativeValue                                              | O                  | Y           |
| refAgriParcelRecord     | Array of Reference            | Related AgriParcelRecords for this greenhouse.                                                             | O                  | Y           |
| leafTemperature         | ExtQuantitativeValue (Number)  | The average greenhouse air temperature in degrees centigrade.  <br/><br/>                    Encoded as a ExtQuantitiativeValue.                                                               | O                  | Y           |
| co2                     | ExtQuantitativeValue (Number)  | The inside C02 concentration in mg/L.  <br/><br/>                                                      Encoded as a ExtQuantitativeValue.                                                         | O                  | Y           |
| dailyLight              | ExtQuantitativeValue (Number) | Daily Accumulated light measured in kW/m<sup>2</sup>    <br/><br/>                                            Encoded as a ExtQuantitativeValue.                                                     | O                  | Y           |
| drainFlow               | ExtQuantitativeValue (Number) | The observed drain flow rate in litres per second encoded as a                                     ExtQuantitativeValue.                                                                             | O                  | Y           |
| refWaterQualityObserved | Array of Reference            | Reference to the id(s) of the WaterQualityObserved records relating to this greenhouse.                    | O                  | Y           |

#### AgriGreenHouse JSON

The JSON code can be downloaded from:

<https://gist.github.com/GSMADeveloper/ba3f1acd21bd476600ad0f4a21f1260b>

```json
{
  "id": "ad500806-05ea-4ab6-812a-7a315d98e88d",
  "type": "AgriGreenHouse",
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
    "value": "c8b475e5-84a8-4346-ad79-cde1d2a4028b",
    "type": "Reference"
  },
  "refWeatherObserved": {
    "value": "c720cec5-ac6f-40b7-8e89-becb75702d0d",
    "type": "Reference"
  },
  "relativeHumidity": {
    "value": {
      "value": 0.4,
      "unitCode": "RA",
      "timestamp": "2016-08-22T19:20+00:00"
    },
    "type": "ExtQuantitativeValue"
  },
  "refAgriParcelRecord": [
    "8c3a525d-b42e-4048-bcdd-a119d8ddb0a5",
    "178d74c1-e6fe-4042-b955-2c164fc90b83"
  ],
  "leafTemperature": {
    "value": {
      "value": 22,
      "unitCode": "CEL",
      "timestamp": "2016-08-22T19:20+00:00"
    },
    "type": "ExtQuantitativeValue"
  },
  "co2": {
    "value": {
      "value": 28,
      "unitCode": "M1",
      "timestamp": "2016-08-22T19:20+00:00"
    },
    "type": "ExtQuantitativeValue"
  },
  "dailyLight": {
    "value": {
      "value": 24,
      "unitCode": "N78",
      "timestamp": "2016-08-22T19:20+00:00"
    },
    "type": "ExtQuantitativeValue"
  },
  "drainFlow": {
    "type": "ExtQuantitativeValue",
    "value": {
      "value": 33,
      "maxValue": 50,
      "minValue": 25,
      "unitCode": "G51",
      "unitText": "Litre per second",
      "timestamp": "2016-08-22T19:20+00:00"
    }
  },
  "refWaterQualityObserved": [
    "49f86e0b-bb90-4751-a1c3-d5a891920807"
  ]
}
```
