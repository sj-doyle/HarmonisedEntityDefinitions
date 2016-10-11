### VehicleType

This entity contains a harmonised description of a vehicleType it forms part of the description of a Vehicle. This entity is primarily associated with the Automotive vertical segment but might also be relevant to Industry, Smart City and Agriculture related IoT applications. Where practicable <https://schema.org/Vehicle> naming conventions have been adopted.

&lt;VehicleType&gt;&lt;Generic Attributes&gt;

| Attribute Name | Attribute Type | Description                                                                   | Mandatory /Optional | May be Null |
|----------------|----------------|-------------------------------------------------------------------------------|--------------------|-------------|
| id             | Text           | Unique id of this instance of this entity.                                    | M                  | N           |
| type           | Text           | Must be equal to "**VehicleType**".                                           | M                  | N           |
| dateCreated    | DateTime       | Entity creation timestamp.                                                    | M                  | N           |
| dateModified   | DateTime       | Timestamp of the last modification of the entity.                             | M                  | Y           |
| source         | Text           | A sequence of characters giving the source of the entity data as a URL.       | M                  | Y           |
| dataProvider   | Text           | A sequence of characters identifying the originator of the harmonised entity. | M                  | Y           |

&lt;VehicleType&gt;&lt;Entity Specific Attributes&gt;

| Attribute Name | Attribute Type | Description                    | Mandatory /Optional | May be Null |
|----------------|----------------|--------------------------------|--------------------|-------------|
| model          | Text           | The vehicle model identifier.  | M                  | N           |
| category       | Text           | The vehicle class identifier.  | M                  | N           |
| manufacturer   | Text           | The manufacturer’s identifier. | M                  | N           |

#### VehicleType JSON

The JSON code can be downloaded from:

<https://gist.github.com/GSMADeveloper/7be3126e94779c6467fb56e1b3b0935d>
```json
{
  "id": "33253089-9cea-4227-889e-61950965f6f9",
  "type": "VehicleType",
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
  "model": {
    "value": "M Class",
    "type": "Text"
  },
  "category": {
    "value": "SUV",
    "type": "Text"
  },
  "manufacturer": {
    "value": "Mercedes Benz",
    "type": "Text"
  }
}
```
