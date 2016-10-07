### DeviceModel

This entity contains a harmonised description of a generic device model and is therefore applicable to all IoT segments and related IoT applications. The Device Model includes an optional hierarchical structure that allows device types to be grouped in a flexible way.

&lt;DeviceModel&gt;&lt;Generic Attributes&gt;

| Attribute Name | Attribute Type | Description                                                                   | Mandatory /Optional | May be Null |
|----------------|----------------|-------------------------------------------------------------------------------|--------------------|-------------|
| id             | Text           | Unique id of this instance of this entity.                                    | M                  | N           |
| type           | Text           | Must be equal to "**DeviceModel**".                                           | M                  | N           |
| dateCreated    | DateTime       | Entity creation timestamp.                                                    | M                  | N           |
| dateModified   | DateTime       | Timestamp of the last modification of the entity.                             | M                  | Y           |
| source         | Text           | A sequence of characters giving the source of the entity data as a URL.       | M                  | Y           |
| dataProvider   | Text           | A sequence of characters identifying the originator of the harmonised entity. | M                  | Y           |

&lt;DeviceModel&gt;&lt;Entity Specific Attributes&gt;

| Attribute Name       | Attribute Type     | Description                                                                                                                                                                                | Mandatory /Optional | May be Null |
|----------------------|--------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------|-------------|
| name                 | Text               | The name of this DeviceModel.                                                                                                                                                              | M                  | N           |
| doc                  | URL                | Reference to Product Data Sheet or other manufacturer’s documentation about this device model including where relevant, details of the accuracy, trueness, precision and units of measure. | O                  | Y           |
| category             | Array of Text      | A choice from an enumerated list defining the category of this device including: <br/><br/> **sensor, actuator, meter, appliance, heater, chiller, lighting, boiler, vessel, airHandlingUnit, consumer, other.**                                                                        | O                  | Y           |
| description          | Text               | A description of this DeviceModel .                                                                                                                                                        | O                  | Y           |
| manufacturerName     | Text               | The name of manufacturer of this DeviceModel.                                                                                                                                              | O                  | Y           |
| brandName            | Text               | A description of the brand name of this DeviceModel.                                                                                                                                       | O                  | Y           |
| root                 | Boolean            | A logical indicator that this DeviceModel is the root of a DeviceModel hierarchy. TRUE indicates it is the root, FALSE indicates that it is not the root.                                  | O                  | Y           |
| refParentDeviceModel | Array of Reference | An array containing a JSON encoded sequence of characters of the unique Ids of the device model groupings this device model is a member of.                                                | O                  | Y           |

#### DeviceModel JSON

The JSON code can be downloaded from:

<https://gist.github.com/GSMADeveloper/6ca009c7e08f6c54377ba758adbe7908>
```json
{
  "id": "e01f13d1-fea4-4cc4-92c9-0d9fadb2c509",
  "type": "DeviceModel",
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
    "value": "Sensor Model 501",
    "type": "Text"
  },
  "doc": {
    "value": "http://www.example.com",
    "type": "URL"
  },
  "category": [
    "sensor"
  ],
  "description": {
    "value": "Monomatics All Weather Temperature Sensor",
    "type": "Text"
  },
  "manufacturerName": {
    "value": "ACME Manufacturing, Inc.",
    "type": "Text"
  },
  "brandName": {
    "value": "SuperWidgets",
    "type": "Text"
  },
  "root": {
    "value": "FALSE",
    "type": "Boolean"
  },
  "refParentDeviceModel": [
    "4146335f-839f-4ff9-a575-6b4e6232b734",
    "c44fc765-51a7-4f71-bf1e-22e874c35180"
  ]
}
```
