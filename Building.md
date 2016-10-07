### Building

This entity contains a harmonised description of a Building. This entity is associated with the vertical segments of smart homes, smart cities, industry and related IoT applications.

&lt;Building&gt;&lt;Generic Attributes&gt;

| Attribute Name | Attribute Type | Description                                                                   | Mandatory /Optional | May be Null |
|----------------|----------------|-------------------------------------------------------------------------------|--------------------|-------------|
| id             | Text           | Unique id of this instance of this entity.                                    | M                  | N           |
| type           | Text           | Must be equal to "**Building**".                                              | M                  | N           |
| dateCreated    | DateTime       | Entity creation timestamp.                                                    | M                  | N           |
| dateModified   | DateTime       | Timestamp of the last modification of the entity.                             | M                  | Y           |
| source         | Text           | A sequence of characters giving the source of the entity data as a URL.       | M                  | Y           |
| dataProvider   | Text           | A sequence of characters identifying the originator of the harmonised entity. | M                  | Y           |

&lt;Building&gt;&lt;Entity Specific Attributes&gt;

| Attribute Name         | Attribute Type                                      | Description                                                                                                                                  | Mandatory /Optional | May be Null |
|------------------------|-----------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------|--------------------|-------------|
| refBuildingType        | Reference                                           | Refers to the buildingType that this building is an instance of.                                                                             | M                  | N           |
| category               | Array of Text                                       | One or more categories relevant to the building with choices based on for example <http://wiki.openstreetmap.org/wiki/Map_Features#Building> | O                  | Y           |
| containedInPlace       | geo:json                                            | The geo:json encoded polygon of the building plot in which this building sits.                                                               | O                  | Y           |
| location               | geo:json                                            | The geo:json encoded polygon of this building.                                                                                               | M                  | N           |
| address                | PostalAddress                                       | The building PostalAddress encoded as a Schema.org PostalAddress.                <br/><br/> [https://schema.org/PostalAddress](https://schema.org/Address)                                                                                | M                  | Y           |
| owner                  | Array of references to Person(s) or Organization(s) | An array containing a JSON encoded sequence of characters referencing the unique Ids of the owner(s). <br/><br/> Related to a Schema.org person or organization.  <br/><br/> <https://schema.org/Person>                                            <br/> <https://schema.org/Organization>                                                                                                             | M                  | Y           |
| occupier               | Array of references to Person(s) or Organization(s) | An array containing a JSON encoded sequence of characters referencing the unique Ids of the occupiers(s). <br/><br/> Related to a Schema.org person or organization. <br/><br/> <https://schema.org/Person>                              <br/> <https://schema.org/Organization>                                                                                                             | M                  | Y           |
| refSubscriptionService | Array of Reference                                  | An array containing a JSON encoded sequence of characters of the unique Ids of the subscription service(s) related to this building.         | O                  | Y           |
| floorsAboveGround      | Number                                              | The number of floors above ground level in this building.                                                                                    | O                  | Y           |
| floorsBelowGround      | Number                                              | The number of floors below ground level in this building.                                                                                    | O                  | Y           |
| description            | Text                                                | An optional description of the entity.                                                                                                       | O                  | Y           |
| mapUrl                 | URL                                                 | A URL to a mapping service which shows the location of the building.                                                                         | O                  | Y           |
| notes                  | Array of Text                                       | Free format notes relating to the building e.g. published occupants, opening hours etc.                                                      | O                  | Y           |

#### Building JSON

The JSON code can be downloaded from:

<https://gist.github.com/GSMADeveloper/4994b9f4f6907a9a96bdb499899cc27f>
```json
{
  "id": "f95c06e3-776e-4a57-9b00-a85e3da145c1",
  "type": "Building",
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
  "refBuildingType": {
    "value": "8b1f2bf0-5093-4182-ad4b-224182bb3b9f",
    "type": "Reference"
  },
  "category": [
    "House"
  ],
  "containedInPlace": {
    "value": {
      "type": "Polygon",
      "coordinates": [
        [100,0],
        [101,0],
        [101,1],
        [100,1],
        [100,0]
      ]
    },
    "type": "geo:json"
  },
  "location": {
    "value": {
      "type": "Polygon",
      "coordinates": [
        [100,0],
        [101,0],
        [101,1],
        [100,1],
        [100,0]
      ]
    },
    "type": "geo:json"
  },
  "address": {
    "type": "PostalAddress",
    "value": {
      "addressLocality": "London",
      "postalCode": "EC4N 8AF",
      "streetAddress": "25 Walbrook"
    }
  },
  "owner": [
    "cdfd9cb8-ae2b-47cb-a43a-b9767ffd5c84",
    "1be9cd61-ef59-421f-a326-4b6c84411ad4"
  ],
  "occupier": [
    "9830f692-7677-11e6-838b-4f9fb3dc5a4f"
  ],
  "refSubscriptionService": [
    "b4fb8bff-1a8f-455f-8cc0-ca43c069f865onService1",
    "55c24793-3437-4157-9bda-667c9e1531fc"
  ],
  "floorsAboveGround": {
    "value": 7,
    "type": "Number"
  },
  "floorsBelowGround": {
    "value": 0,
    "type": "Number"
  },
  "description": {
    "value": "Office block",
    "type": "Text"
  },
  "mapUrl": {
    "value": "http://www.example.com",
    "type": "URL"
  },
  "notes": {
    "value": "Intelligent entry barrier system, intelligent air conditioning units",
    "type": "Text"
  }
}
```
