###  Machine

This entity contains a harmonised description of an industrial machine for example for use in CAM (Computer Aided Manufacturing). This entity provides an essentially static description of a generic automation machine. This entity is primarily associated with the industry segment in the automated manufacturing industry, including CNC (Computer Numerical Control) machines, 3D printers and all kinds of industrial robots.

&lt;Machine&gt;&lt;Generic Attributes&gt;

| Attribute Name | Attribute Type | Description                                                                   | Mandatory /Optional | May be Null |
|----------------|----------------|-------------------------------------------------------------------------------|--------------------|-------------|
| id             | Text           | Unique id of this instance of this entity.                                    | M                  | N           |
| type           | Text           | Must be equal to "**Machine**".                                               | M                  | N           |
| dateCreated    | DateTime       | Entity creation timestamp.                                                    | M                  | N           |
| dateModified   | DateTime       | Timestamp of the last modification of the entity.                             | M                  | Y           |
| source         | Text           | A sequence of characters giving the source of the entity data as a URL.       | M                  | Y           |
| dataProvider   | Text           | A sequence of characters identifying the originator of the harmonised entity. | M                  | Y           |

&lt;Machine&gt;&lt;Entity Specific Attributes&gt;

| Attribute Name         | Attribute Type     | Description                                                                                                                              | Mandatory /Optional | May be Null |
|------------------------|--------------------|------------------------------------------------------------------------------------------------------------------------------------------|--------------------|-------------|
| refMachineModel        | Reference          | Refers to the machineModel that this machine is an instance of.                                                                          | M                  | N           |
| serialNumber           | Text               | The serial number assigned by the manufacturer.                                                                                          | M                  | N           |
| assetIdentifier        | Text               | An asset identifier (e.g. asset tag number) assigned by the owner.                                                                       | O                  | Y           |
| manufacturerCountry    | Text               | The country where this machine instance was manufactured.                                                                                | O                  | Y           |
| dateManufactured       | DateTime           | The ISO8601 sequence of characters at which the machine was manufactured in UTC.                                                         | M                  | N           |
| dateInstalled          | DateTime           | The ISO8601 sequence of characters at which the machine was installed in UTC.                                                            | M                  | N           |
| dateFirstUsed          | DateTime           | The ISO8601 sequence of characters at which the machine was first used in UTC.                                                           | M                  | N           |
| online                 | Boolean            | Identifies the communication status of the machine, online if set to TRUE.                                                               | O                  | Y           |
| installationNotes      | Text or URL        | Notes relating to this machine installation.                                                                                             | O                  | Y           |
| location               | geo:json           | The geo:json encoded location, of this machine.                                                                                          | M                  | N           |
| refBuilding            | Reference          | Refers to the building instance into which this machine is installed.                                                                    | O                  | Y           |
| owner                  | Array of Reference | An array containing a JSON encoded sequence of characters referencing the unique Ids of the owner(s). <br/><br/> Related to a Schema.org person or organization. <br/><br/><https://schema.org/Person> <br/><https://schema.org/Organization>                                                                                                         | O                  | Y           |
| refSubscriptionService | Array of Reference | An array containing a JSON encoded sequence of characters of the unique Ids of any subscription service(s) associated with this machine. | O                  | Y           |
| description            | Text               | An optional description of this machine.                                                                                                 | O                  | Y           |

#### Machine JSON

The JSON code can be downloaded from:

<https://gist.github.com/GSMADeveloper/aaa70bd157da04b6246d35525a7ffbcc>
```json
{
  "id": "9166c528-9c98-4579-a5d3-8068aea5d6c0",
  "type": "Machine",
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
  "refMachineModel": {
    "value": "00b42701-43e1-482d-aa7a-e2956cfd69c3",
    "type": "Reference"
  },
  "serialNumber": {
    "value": "123456789",
    "type": "Text"
  },
  "assetIdentifier": {
    "value": "1234567",
    "type": "Text"
  },
  "manufacturerCountry": {
    "value": "UK",
    "type": "Text"
  },
  "dateManufactured": {
    "value": "2016-08-21T10:18:16Z",
    "type": "DateTime"
  },
  "dateInstalled": {
    "value": "2016-08-22T10:18:16Z",
    "type": "DateTime"
  },
  "dateFirstUsed": {
    "value": "2016-08-22T10:18:16Z",
    "type": "DateTime"
  },
  "online": {
    "value": "TRUE",
    "type": "Boolean"
  },
  "installationNotes": {
    "value": "http://www.example.com/installationNote1.txt",
    "type": "URL"
  },
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
  "refBuilding": {
    "value": "8683b757-649c-49e0-ac89-ad392c9a0d0c",
    "type": "Reference"
  },
  "owner": [
    "247d402f-3e0b-4e7c-a2c0-335590c27f90",
    "a7995eb7-6bec-4176-b2e8-af545e2bb3b9"
  ],
  "refSubscriptionService": [
    "92158a14-f6c6-4d29-85d1-5d305cc87982",
    "3c6bac7b-9398-4529-8d89-766435b7490b"
  ],
  "description": {
    "value": "Industrial machine to create plastic bottles",
    "type": "Text"
  }
}
```
