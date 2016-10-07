### AirQualityObserved

This entity contains a harmonised description of the air quality observed at a particular location and time. This entity is primarily associated with the vertical segment of the environment and may also be used in smart homes, smart cities, agriculture, industry and related IoT applications.

&lt;AirQualityObserved&gt;&lt;Generic Attributes&gt;

| Attribute Name | Attribute Type | Description                                                                   | Mandatory/Optional | May be Null |
|----------------|----------------|-------------------------------------------------------------------------------|--------------------|-------------|
| id             | Text           | Unique id of this instance of this entity.                                    | M                  | N           |
| type           | Text           | Must be equal to "**AirQualityObserved**".                                    | M                  | N           |
| dateCreated    | DateTime       | Entity creation timestamp.                                                    | M                  | N           |
| dateModified   | DateTime       | Timestamp of the last modification of the entity.                             | M                  | Y           |
| source         | Text           | A sequence of characters giving the source of the entity data as a URL.       | M                  | Y           |
| dataProvider   | Text           | A sequence of characters identifying the originator of the harmonised entity. | M                  | Y           |

&lt;AirQualityObserved&gt;&lt;Entity Specific Attributes&gt;

| Attribute Name | Attribute Type     | Description                                                                               | Mandatory/Optional | May be Null |
|----------------|--------------------|-------------------------------------------------------------------------------------------|--------------------|-------------|
| refDevice      | Array of Reference | An array of references to the unique ids of the devices that originated this observation. | O                  | N           |
| location       | geo:json           | The geo:json encoded polygon or point location, of this observation.                      | M                  | N           |
| dateObserved   | DateTime           | The date and time of this observation in ISO8601 UTCformat.                               | M                  | N           |
| measurand      | Array of Text      | An array containing a JSON encoded sequence of characters of the measurand observed. <br/><br/> **measurand** , **observedValue**, **unitcode**, **description**. <br/><br/> Unitcode defined as in schema.org/QuantitativeValue <br/> The unit of measurement given using the UN/CEFACT Common Code (3 characters)  <br/><br/> <http://wiki.goodrelations-vocabulary.org/Documentation/UN/CEFACT_Common_Codes> <br/><br/> Example:         <br/>**"CO,500,M1,Carbon Monoxide"**                                             <br/>**"NO,45,M1,Nitrogen Monoxide"**                                        <br/>**"NO2,69,M1,Nitrogen Dioxide"**                                        <br/>**"NOx,139,M1,Nitrogen oxides"**                                            <br/>**"SO2,11,M1,Sulfur Dioxide"**                                                             | M                  | Y           |

#### AirQualityObserved JSON

The JSON code can be downloaded from:

<https://gist.github.com/GSMADeveloper/95ae1e455d471443c1a7af72e26e3fe2>
```json
{
  "id": "c9f32b35-a185-48e2-835f-c521efc294ab",
  "type": "AirQualityObserved",
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
    "5c9fb9dd-fc13-4fda-8f4c-f99a04f6f858"
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
    "value": "2016-08-08T10:18:16Z",
    "type": "DateTime"
  },
  "measurand": [
    "CO, 500, M1, Carbon monoxide concentration",
    "CO2, 1500, M1, Carbon dioxide concentration"
  ]
}
```
