###  MachineModel

This entity contains a harmonised description of a generic machine model. This entity is primarily associated with the industry segment and related IoT applications. The machineModel includes a hierarchical structure that allows machine models to be grouped in a flexible way.

&lt;MachineModel&gt;&lt;Generic Attributes&gt;

| Attribute Name | Attribute Type | Description                                                                   | Mandatory /Optional | May be Null |
|----------------|----------------|-------------------------------------------------------------------------------|--------------------|-------------|
| id             | Text           | Unique id of this instance of this entity.                                    | M                  | N           |
| type           | Text           | Must be equal to "**MachineModel**".                                          | M                  | N           |
| dateCreated    | Date           | Entity creation timestamp.                                                    | M                  | N           |
| dateModified   | Date           | Timestamp of the last modification of the entity.                             | M                  | Y           |
| source         | Text           | A sequence of characters giving the source of the entity data as a URL.       | M                  | Y           |
| dataProvider   | Text           | A sequence of characters identifying the originator of the harmonised entity. | M                  | Y           |

&lt;MachineModel&gt;&lt;Entity Specific Attributes&gt;

| Attribute Name     | Attribute Type     | Description                                                                                                                                                                             | Mandatory /Optional | May be Null |
|--------------------|--------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------|-------------|
| name               | Text               | The name given to this machine model.                                                                                                                                                   | M                  | N           |
| description        | Text               | A description of this machine model.                                                                                                                                                    | O                  | Y           |
| manufacturerName   | Text               | The name of manufacturer of this machine model.                                                                                                                                         | O                  | Y           |
| brandName          | Text               | A description of this machine model brand name.                                                                                                                                         | O                  | Y           |
| version            | Text               | The manufacturer defined version number for the machine model.                                                                                                                          | O                  | Y           |
| category           | Array of Text      | An array of text based service categories which this machineModel supports. Examples include: <br/><br/> **robot, cnc, 2dPrinter, 3dPrinter, 3dScanner, lathe, injectionMolding, laserCutter, millingMachine, grindingMachine, stampingMachine, oven, kiln, packaging, mixer, dryer, fan, saw.**  | O                  | Y           |
| doc                | URL                | Reference to Product Data Sheet or other manufacturers documentation about this machine.                                                                                                | O                  | Y           |
| root               | Boolean            | A logical indicator that this machineModel is the root of a machineModel hierarchy. TRUE indicates it is the root, FALSE indicates that it is not the root.                             | O                  | Y           |
| refParentModel     | Array of Reference | An array containing a JSON encoded sequence of characters referencing the ids of other machine models which this is related to.                                                         | O                  | Y           |
| processDescription | Text               | A description of the industrial process carried out by this machine.                                                                                                                    | O                  | Y           |
| standardOperations | Array of Text      | Lists the standard set of operations supported by this machineModel.                                                                                                                    | O                  | Y           |

#### MachineModel JSON

The JSON code can be downloaded from:

<https://gist.github.com/GSMADeveloper/10d7c9ffca1e4d1e498203f85dc0991d>
```json
{
  "id": "e01f13d1-fea4-4cc4-92c9-0d9fadb2c509",
  "type": "MachineModel",
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
    "value": "CA1256b",
    "type": "Text"
  },
  "description": {
    "value": "Machine to screen print t-shirts",
    "type": "Text"
  },
  "manufacturerName": {
    "value": "ScreenOPrint, Inc.",
    "type": "Text"
  },
  "brandName": {
    "value": "QuickT",
    "type": "Text"
  },
  "version": {
    "value": "v1",
    "type": "Text"
  },
  "category": [
    "2dPrinter"
  ],
  "doc": {
    "value": "http://www.example.com",
    "type": "URL"
  },
  "root": {
    "value": "FALSE",
    "type": "Boolean"
  },
  "refParentModel": [
    "4146335f-839f-4ff9-a575-6b4e6232b734",
    "c44fc765-51a7-4f71-bf1e-22e874c35180"
  ],
  "processDescription": {
    "value": "Industrial printer used to mass print t-shirts",
    "type": "Text"
  },
  "standardOperations": [
    "print"
  ]
}
```
