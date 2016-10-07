### BuildingType

This entity contains a harmonised description of a generic building type. This entity is associated with the vertical segments of smart home, smart cities, industry and related IoT applications. The building type includes a hierarchical structure that allows building types to be grouped in a flexible way.

&lt;BuildingType&gt;&lt;Generic Attributes&gt;

| Attribute Name | Attribute Type | Description                                                                   | Mandatory /Optional | May be Null |
|----------------|----------------|-------------------------------------------------------------------------------|--------------------|-------------|
| id             | Text           | Unique id of this instance of this entity.                                    | M                  | N           |
| type           | Text           | Must be equal to "**BuildingType**".                                          | M                  | N           |
| dateCreated    | DateTime       | Entity creation timestamp.                                                    | M                  | N           |
| dateModified   | DateTime       | Timestamp of the last modification of the entity.                             | M                  | Y           |
| source         | Text           | A sequence of characters giving the source of the entity data as a URL.       | M                  | Y           |
| dataProvider   | Text           | A sequence of characters identifying the originator of the harmonised entity. | M                  | Y           |

&lt;BuildingType&gt;&lt;Entity Specific Attributes&gt;

| Attribute Name | Attribute Type     | Description                                                                                                                                           | Mandatory /Optional | May be Null |
|----------------|--------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------|-------------|
| name           | Text               | The name of this BuildingType.                                                                                                                        | M                  | N           |
| description    | Text               | A description of this type.                                                                                                                           | O                  | Y           |
| root           | Boolean            | A logical indicator that this is the root of a BuildingType hierarchy. TRUE indicates it is the root, FALSE indicates that it is not the root.        | O                  | Y           |
| refParentType  | Array of Reference | An array containing a JSON encoded sequence of characters referencing the unique Ids of the building type groupings this BuildingType is a member of. | O                  | Y           |

#### BuildingType JSON

The JSON code can be downloaded from:

<https://gist.github.com/GSMADeveloper/e7553da5f75bc32e9f02024e7cdca0b1>
```json
{
  "id": "57b912ab-eb47-4cd5-bc9d-73abece1f1b3",
  "type": "BuildingType",
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
  "name": {
    "value": "House",
    "type": "Text"
  },
  "description": {
    "value": "Standard building type definition for a domestic house",
    "type": "Text"
  },
  "root": {
    "value": "FALSE",
    "type": "Boolean"
  },
  "refParentType": [
    "4146335f-839f-4ff9-a575-6b4e6232b734",
    "c44fc765-51a7-4f71-bf1e-22e874c35180"
  ]
}
```
