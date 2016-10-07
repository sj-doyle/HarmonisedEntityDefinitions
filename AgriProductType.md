### AgriProductType

This entity contains a harmonised description of a generic agricultural product type. This entity is primarily associated with the agricultural vertical and related IoT applications. The AgriProductType includes a hierarchical structure that allows product types to be grouped in a flexible way.

&lt;AgriProductType&gt;&lt;Generic Attributes&gt;

| Attribute Name | Attribute Type | Description                                                                   | Mandatory /Optional | May be Null |
|----------------|----------------|-------------------------------------------------------------------------------|--------------------|-------------|
| id             | Text           | Unique id of this instance of this entity.                                    | M                  | N           |
| type           | Text           | Must be equal to "**AgriProductType**".                                       | M                  | N           |
| dateCreated    | DateTime       | Entity creation timestamp.                                                    | M                  | N           |
| dateModified   | DateTime       | Timestamp of the last modification of the entity.                             | M                  | Y           |
| source         | Text           | A sequence of characters giving the source of the entity data as a URL.       | M                  | Y           |
| dataProvider   | Text           | A sequence of characters identifying the originator of the harmonised entity. | M                  | Y           |

&lt;AgriProductType&gt;&lt;Entity Specific Attributes&gt;

| Attribute Name | Attribute Type     | Description                                                                                                                            | Mandatory /Optional | May be Null |
|----------------|--------------------|----------------------------------------------------------------------------------------------------------------------------------------|--------------------|-------------|
| name           | Text               | The name of this AgriProductType.                                                                                                      | M                  | N           |
| description    | Text               | A description of this AgriProductType.                                                                                                 | M                  | N           |
| root           | Boolean            | A logical indicator that this product is the root of a AgriProductType hierarchy. Logical TRUE indicates it is a root.                 | M                  | N           |
| refParentType  | Array of Reference | A JSON encoded sequence of characters referencing the unique ids of the AgriProductType groupings this AgriProductType is a member of. | O                  | Y           |

#### AgriProductType JSON

The JSON code can be downloaded from:

<https://gist.github.com/GSMADeveloper/e78f090452ce8f63adfba472fe43c5d7>
```json
{
  "id": "398aa5f4-6a81-4dea-9f85-e9869441a257",
  "type": "AgriProductType",
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
    "value": "Soft Fruits",
    "type": "Text"
  },
  "description": {
    "value": "Soft edible fruits",
    "type": "Text"
  },
  "root": {
    "value": "FALSE",
    "type": "Text"
  },
  "refParentType": [
    "b99c940d-7156-4280-9a2b-4a9e533cd20e"
  ]
}
```
