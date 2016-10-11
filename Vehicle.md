### Vehicle

This entity contains a harmonised description of a Vehicle. This entity is primarily associated with the Automotive vertical segment but might also be relevant to Industry, Smart City and Agriculture related IoT applications. Where practicable <https://schema.org/Vehicle> naming conventions have been adopted.

&lt;Vehicle&gt;&lt;Generic Attributes&gt;

| Attribute Name | Attribute Type | Description                                                                   | Mandatory /Optional | May be Null |
|----------------|----------------|-------------------------------------------------------------------------------|--------------------|-------------|
| id             | Text           | Unique id of this instance of this entity.                                    | M                  | N           |
| type           | Text           | Must be equal to "**Vehicle**".                                               | M                  | N           |
| dateCreated    | DateTime       | Entity creation timestamp.                                                    | M                  | N           |
| dateModified   | DateTime       | Timestamp of the last modification of the entity.                             | M                  | Y           |
| source         | Text           | A sequence of characters giving the source of the entity data as a URL.       | M                  | Y           |
| dataProvider   | Text           | A sequence of characters identifying the originator of the harmonised entity. | M                  | Y           |

&lt;Vehicle&gt;&lt;Entity Specific Attributes&gt;

| Attribute Name              | Attribute Type                | Description                                                                                                                                                                                                                                           | Mandatory /Optional | May be Null |
|-----------------------------|-------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------|-------------|
| refVehicleType              | Array of Reference            | A JSON encode sequence of characters referencing the Id of the vehicleType entity which describes this vehicle in more detail.                                                                                                                        | M                  | N           |
| fuelType                    | Text                          | A choice from an enumerated list describing the power source. One of:<br/><br/> **gasoline, petrol(unleaded), petrol(leaded), petrol, diesel, electric, hydrogen, lpg autogas, cng, biodiesel, ethanol, hybrid electric/petrol, hybrid electric/diesel, other** | M                  | N           |
| displacement                | Number                        | A number indicating the cylinder capacity of the engine in litres                                                                                                                                                                                     | O                  | Y           |
| fuelEconomy                 | Number                        | A number indicating the fuel economy index.                                                                                                                                                                                                           | O                  | Y           |
| vehicleModelDate            | DateTime                      | The ISO8601 sequence of characters indicating the year of release.                                                                                                                                                                                    | O                  | Y           |
| dateDiscontinued            | DateTime                      | The ISO8601 sequence of characters indicating the year which the vehicle was discontinued.                                                                                                                                                            | O                  | Y           |
| vechileIdentificationNumber | Text                          | The VIN (vehicle identification number) of the vehicle.                                                                                                                                                                                               | O                  | Y           |
| mileageFromOdometer         | ExtQuantitativeValue (Number) | The total distance the car has travelled according to the on-board odometer in kilometres or miles,    <br/><br/>references Schema.org Vehicle/ mileageFromOdometer.                                                                                                                                                                                                    | O                  | Y           |

#### Vehicle JSON

The JSON code can be downloaded from:

<https://gist.github.com/GSMADeveloper/f28833b6c5c51c3e79fa6f7dfa1a7864>
```json
{
  "id": "1fa179a6-b507-4857-ad72-eb5513ef05c6",
  "type": "Vehicle",
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
  "refVehicleType": [
    "23821045-33d4-46ec-b777-98f461bf4856",
    "2ff57791-ebfb-4086-ab61-60b5beed605d"
  ],
  "fuelType": {
    "value": "Diesel",
    "type": "Text"
  },
  "displacement": {
    "value": 3,
    "type": "Number"
  },
  "fuelEconomy": {
    "value": 22,
    "type": "Number"
  },
  "vehicleModelDate": {
    "value": "2016-08-18T10:18:16Z",
    "type": "DateTime"
  },
  "dateDiscontinued": {
    "value": "2016-08-23T10:18:16Z",
    "type": "DateTime"
  },
  "vehicleIdentificationNumber": {
    "value": "2T2GK31U08C041124",
    "type": "Text"
  },
  "mileageFromOdometer": {
    "value": {
      "value": 33015,
      "unitCode": "NMI"
    },
    "type": "ExtQuantitativeValue"
  }
}
```
