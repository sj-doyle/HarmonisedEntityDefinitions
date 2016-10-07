### AgriPest

This entity contains a harmonised description of a generic agricultural pest. This entity is primarily associated with the agricultural vertical and related IoT applications.

&lt;AgriPest&gt;&lt;Generic Attributes&gt;

| Attribute Name | Attribute Type | Description                                                                   | Mandatory /Optional | May be Null |
|----------------|----------------|-------------------------------------------------------------------------------|--------------------|-------------|
| id             | Text           | Unique id of this instance of this entity.                                    | M                  | N           |
| type           | Text           | Must be equal to "**AgriPest**".                                              | M                  | N           |
| dateCreated    | DateTime       | Entity creation timestamp.                                                    | M                  | N           |
| dateModified   | DateTime       | Timestamp of the last modification of the entity.                             | M                  | Y           |
| source         | Text           | A sequence of characters giving the source of the entity data as a URL.       | M                  | Y           |
| dataProvider   | Text           | A sequence of characters identifying the originator of the harmonised entity. | M                  | Y           |

&lt;AgriPest&gt;&lt;Entity Specific Attributes&gt;

| Attribute Name | Attribute Type     | Description                                                                                                                       | Mandatory /Optional | May be Null |
|----------------|--------------------|-----------------------------------------------------------------------------------------------------------------------------------|--------------------|-------------|
| name           | Text               | The name of this agricultural pest.                                                                                               | M                  | N           |
| alternateName  | Text               | Alternative name of this agricultural pest.                                                                                       | O                  | Y           |
| description    | Text               | A description of this agricultural pest.                                                                                          | O                  | Y           |
| refAgriProduct | Array of Reference | An array containing a JSON encoded sequence of characters referencing the unique ids of the recommended AgriProduct pesticide(s). | O                  | Y           |

#### AgriPest JSON

The JSON code can be downloaded from:

<https://gist.github.com/GSMADeveloper/cbab7c37630eb7ea87b503267d0696a1>
```json
{
  "id": "fb3f1295-500c-4aa3-b995-c909097d5c01",
  "type": "AgriPest",
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
  "name": {
    "value": "Grasshopper",
    "type": "Text"
  },
  "alternateName": {
    "value": "Chorthippus parallelus",
    "type": "Text"
  },
  "description": {
    "value": "Common European grasshopper",
    "type": "Text"
  },
  "refAgriProduct": [
    "7f1d962b-0d14-479b-a50a-baaef261263a"
  ]
}
```
