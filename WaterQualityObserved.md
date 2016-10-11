### WaterQualityObserved

This entity contains a harmonised description of the water quality at a particular location and time. This entity is primarily associated with the vertical segments of agricultural and environment and related IoT applications.

&lt;WaterQualityObserved&gt;&lt;Generic Attributes&gt;

| Attribute Name | Attribute Type | Description                                                                   | Mandatory /Optional | May be Null |
|----------------|----------------|-------------------------------------------------------------------------------|--------------------|-------------|
| id             | Text           | Unique id of this instance of this entity.                                    | M                  | N           |
| type           | Text           | Must be equal to "**WaterQualityObserved**".                                  | M                  | N           |
| dateCreated    | DateTime       | Entity creation timestamp.                                                    | M                  | N           |
| dateModified   | DateTime       | Timestamp of the last modification of the entity.                             | M                  | Y           |
| source         | Text           | A sequence of characters giving the source of the entity data as a URL.       | M                  | Y           |
| dataProvider   | Text           | A sequence of characters identifying the originator of the harmonised entity. | M                  | Y           |

&lt;WaterQualityObserved&gt;&lt;Entity Specific Attributes&gt;

| Attribute Name | Attribute Type                 | Description                                                                                                                         | Mandatory /Optional | May be Null |
|----------------|--------------------------------|-------------------------------------------------------------------------------------------------------------------------------------|--------------------|-------------|
| refDevice      | Array of Reference             | A reference to the unique entity Ids of the devices that originated this observation data.                                          | M                  | N           |
| location       | geo:json                       | The geo:json encoded map location, that is related to this observation.                                                             | M                  | N           |
| dateObserved   | DateTime                       | The date and time of this observation in ISO8601 UTCformat.                                                                         | M                  | N           |
| measurand      | Array of Text                  | An array containing a JSON encoded sequence of characters of the measurand observed.                       <br/><br/> **measurand, valueObserved, unitcode, description.**               <br/><br/> Unitcode defined as in schema.org/QuantitativeValue               <br/><br/> The unit of measurement given using the UN/CEFACT Common Code (3 characters) – the unitcode.                                         <br/><br/><http://wiki.goodrelations-vocabulary.org/Documentation/UN/CEFACT_Common_Codes>  <br/><br/> see example below:                                                    <br/><br/> **"O2, 50,M1,The level of free non-compound oxygen present"**         <br/><br/> Possible examples of typical measurands, descriptions and unitcodes are presented below:                                                         <br/><br/> **O2. The level of free non-compound oxygen present. (*M1*) **        <br/>**CO. The level of free non-compound carbon monoxide present. (*M1*)**      <br/>**CO2. The level of free non-compound carbon dioxide present. (*M1*)**      <br/>**Hg. The level of compound mercury present. (*M1*)**                        <br/>**Chla. Concentration of chlorophyll A. (*H29*)**                            <br/>**PE. Concentration of pigment *phycoerythrin* which can be measured to estimate cyanobacteria concentrations specifically.(H29)**                   <br/>**PC. Concentration of pigment *phycocyanin* which can be measured to estimate cyanobacteria concentrations specifically. (*H29*)**              <br/>**NH4. Concentration of ammonium. (*M1*)**                                  <br/>**NH3. Concentration of ammonia. (*M1*)**                                 <br/>**Cl-. Concentration of chlorides. (*M1*)**                               <br/>**NO3-. Concentration of nitrates. (*M1*)**                                 <br/> etc.                                                                                                                                 | O                  | Y           |
| depth          | ExtQuantitativeValue (Number)  | Depth where the observation was taken. (*m*) encoded as a ExtQuantitativeValue.                                                     | O                  | Y           |
| pressure       | ExtQuantitativeValue (Number)  | Hydrostatic pressure where the observation was taken. (Pa) encoded as a ExtQuantitativeValue.                                       | O                  | Y           |
| conductivity   | ExtQuantitativeValue (Number)  | Electrical conductivity. (*S/m*) encoded as a ExtQuantitativeValue.                                                                 | O                  | Y           |
| conductance    | ExtQuantitativeValue (Number)  | Specific conductivity / 25 ºC /. (*S/m*) encoded as a ExtQuantitativeValue.                                                         | O                  | Y           |
| temperature    | ExtQuantitativeValue (Number)  | The temperature expressed in degrees Celsius encoded as a ExtQuantitativeValue.                                                     | O                  | Y           |
| tss            | ExtQuantitativeValue (Number)r | Total suspended solids. (*M1*) encoded as a ExtQuantitativeValue                                                                    | O                  | Y           |
| tds            | ExtQuantitativeValue (Number)  | Total dissolved solids. (*M1*) encoded as a ExtQuantitativeValue.                                                                   | O                  | Y           |
| turbidity      | ExtQuantitativeValue (Number)  | Amount of light scattered by particles in the water column. (*FTU*). encoded as a ExtQuantitativeValue.                             | O                  | Y           |
| salinity       | ExtQuantitativeValue (Number)  | Derived from the conductivity measurement. (*parts per thousand, ppt*) encoded as a ExtQuantitativeValue.                           | O                  | Y           |
| pH             | ExtQuantitativeValue (Number)  | pH measurement (typically a number between *0 and 14*) encoded as a ExtQuantitativeValue.                                           | O                  | Y           |
| orp            | ExtQuantitativeValue (Number)  | Oxidation-Reduction potential (*mV*) encoded as a ExtQuantitativeValue.                                                             | O                  | Y           |
| cdom           | ExtQuantitativeValue (Number)  | Color dissolved organic matter (*RFU*) encoded as a ExtQuantitativeValue.                                                           | O                  | Y           |

#### WaterQualityObserved JSON

The JSON code can be downloaded from:

<https://gist.github.com/GSMADeveloper/5252d6628d7a06472c7e7fc366b7ee23>
```json
{
  "id": "72a30ca8-888e-49a2-8d8d-a5bebc19e98b",
  "type": "WaterQualityObserved",
  "dateCreated": {
    "value": "2016-08-08T10:18:16Z",
    "type": "DateTime"
  },
  "dateModified": {
    "value": "2016-08-08T10:18:16Z",
    "type": "DateTime"
  },
  "source": {
    "value": "http://www.example.com",
    "type": "URL"
  },
  "dataProvider": {
    "value": "OperatorA",
    "type": "Text"
  },
  "refDevice": [
    "2033a7c7-d31b-48e7-91c2-014dc426c29e"
  ],
  "location": {
    "value": {
      "type": "Point",
      "coordinates": [
        -104.99404,
        39.75621
      ]
    },
    "type": "geo:json"
  },
  "dateObserved": {
    "value": "2016-08-16T10:18:16Z",
    "type": "DateTime"
  },
  "measurand": [
    "O2, 50, M1, Oxygen concentration"
  ],
  "depth": {
    "value": {
      "value": 4,
      "unitCode": "MTR"
    },
    "type": "ExtQuantitativeValue"
  },
  "pressure": {
    "value": {
      "value": 10202,
      "unitCode": "PAL"
    },
    "type": "ExtQuantitativeValue"
  },
  "conductivity": {
    "value": {
      "value": 10,
      "unitCode": "D10"
    },
    "type": "ExtQuantitativeValue"
  },
  "conductance": {
    "value": {
      "value": 25,
      "unitCode": "D10"
    },
    "type": "ExtQuantitativeValue"
  },
  "temperature": {
    "value": {
      "value": 15,
      "unitCode": "CEL"
    },
    "type": "ExtQuantitativeValue"
  },
  "tss": {
    "value": {
      "value": 200,
      "unitCode": "M1"
    },
    "type": "ExtQuantitativeValue"
  },
  "tds": {
    "value": {
      "value": 150,
      "unitCode": "M1"
    },
    "type": "ExtQuantitativeValue"
  },
  "turbidity": {
    "value": {
      "value": 343,
      "unitCode": "FTU"
    },
    "type": "ExtQuantitativeValue"
  },
  "salinity": {
    "value": {
      "value": 220
    },
    "type": "ExtQuantitativeValue"
  },
  "pH": {
    "value": {
      "value": 5
    },
    "type": "ExtQuantitativeValue"
  },
  "orp": {
    "value": {
      "value": 225,
      "unitCode": "2Z"
    },
    "type": "ExtQuantitativeValue"
  },
  "cdom": {
    "value": {
      "value": 22,
      "unitCode": "RFU"
    },
    "type": "ExtQuantitativeValue"
  }
}
```
