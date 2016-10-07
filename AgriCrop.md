### AgriCrop

This entity contains a harmonised description of a generic crop. This entity is primarily associated with the agricultural vertical and related IoT applications.

&lt;AgriCrop&gt;&lt;Generic Attributes&gt;

| Attribute Name | Attribute Type | Description                                                                   | Mandatory /Optional | May be Null |
|----------------|----------------|-------------------------------------------------------------------------------|--------------------|-------------|
| id             | Text           | Unique id of this instance of this entity.                                    | M                  | N           |
| type           | Text           | Must be equal to "**AgriCrop**".                                              | M                  | N           |
| dateCreated    | DateTime       | Entity creation timestamp.                                                    | M                  | N           |
| dateModified   | DateTime       | Timestamp of the last modification of the entity.                             | M                  | Y           |
| source         | URL            | A sequence of characters giving the source of the entity data as a URL.       | M                  | Y           |
| dataProvider   | Text           | A sequence of characters identifying the originator of the harmonised entity. | M                  | Y           |

&lt;AgriCrop&gt;&lt;Entity Specific Attributes&gt;

| Attribute Name     | Attribute Type     | Description                                                                                                                                                                                        | Mandatory /Optional | May be Null |
|--------------------|--------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------|-------------|
| name               | Text               | The name of this crop.                                                                                                                                                                             | M                  | N           |
| alternateName      | Text               | An alternative name for this crop.                                                                                                                                                                 | O                  | Y           |
| description        | Text               | A description of this crop.                                                                                                                                                                        | O                  | Y           |
| refAgriSoil        | Array of Reference | An array containing a JSON encoded sequence of characters that reference the unique Ids of the recommended soil(s).                                                                                | O                  | Y           |
| refAgriFertilizer  | Array of Reference | An array containing a JSON encoded sequence of characters that reference the unique Ids of the recommended fertiliser product(s).                                                                  | O                  | Y           |
| refAgriPest        | Array of Reference | An array containing a JSON encoded sequence of characters that reference the unique Ids of the pest(s) known to attack this crop.                                                                  | O                  | Y           |
| plantingInterval   | Array of Text      | An array containing a JSON encoded sequence of characters of the recommended planting interval date(s) for this crop. Using The ISO8601 sequence of characters for each repeating date interval: <br/><br/>**interval**, **description** <br/><br/>Where **interval** is in the form of start date/end date <br/>--MM-DD/--MM-DD<br/><br/> Meaning repeat each year from this start date to this end date.                                                                      | O                  | Y           |
| harvestingInterval | Array of Text      | An array containing a JSON encoded sequence of characters of the recommended harvesting interval date(s) for this crop. Using The ISO8601 sequence of characters for each repeating date interval: <br/><br/>**interval** , **description**<br/><br/>                                          Where **interval** is in the form of                                           start date/end date                                                         <br/> --MM-DD/--MM-DD <br/><br/>Meaning repeat each year between the specified start date and the specified end date.                                                                                                               | O                  | Y           |
| wateringFrequency  | Text               | A description of the recommended watering schedule. A choice from an enumerated list. One of: <br/><br/>**daily, weekly, biweekly, monthly, onDemand, other**                                                                                                                     | O                  | Y           |

#### AgriCrop JSON

The JSON code can be downloaded from:

<https://gist.github.com/GSMADeveloper/00685ca0edd54411cad5be84ee658da8>
```json
{
  "id": "df72dc57-1eb9-42a3-88a9-8647ecc954b4",
  "type": "AgriCrop",
  "dateCreated": {
    "value": "2016-08-22T19:20+00:00",
    "type": "DateTime"
  },
  "dateModified": {
    "value": "2016-08-22T19:20+00:00",
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
  "name": {
    "value": "Wheat",
    "type": "Text"
  },
  "alternateName": {
    "value": "Triticum aestivum",
    "type": "Text"
  },
  "description": {
    "value": "Spring wheat",
    "type": "Text"
  },
  "refAgriSoil": [
    "00411b56-bd1b-4551-96e0-a6e7fde9c840",
    "e8a8389a-edf5-4345-8d2c-b98ac1ce8e2a"
  ],
  "refAgriFertilizer": [
    "1b0d6cf7-320c-4a2b-b2f1-4575ea850c73",
    "380973c8-4d3b-4723-a899-0c0c5cc63e7e"
  ],
  "refAgriPest": [
    "10b52f07-079a-4390-8237-bf6a1c049a85",
    "66bdb09b-4fe0-4932-a267-f9eda4474d2a"
  ],
  "plantingInterval": [
    "-09-28/-10-12, Best Season",
    "-10-11/-10-18, Season OK"
  ],
  "harvestingInterval": [
    "-03-21/-04-01, Best Season",
    "-04-02/-04-15, Season OK"
  ],
  "wateringFrequency": {
    "value": "weekly",
    "type": "Text"
  }
}
```
