### AgriParcelOperation

This entity contains a harmonised description of a generic operations performed on a parcel of land. This entity is primarily associated with the agricultural vertical and related IoT applications.

&lt;AgriParcelOperation&gt;&lt;Generic Attributes&gt;

| Attribute Name | Attribute Type | Description                                                                   | Mandatory /Optional | May be Null |
|----------------|----------------|-------------------------------------------------------------------------------|--------------------|-------------|
| id             | Text           | Unique id of this instance of this entity.                                    | M                  | N           |
| type           | Text           | Must be equal to "**AgriParcelOperation**".                                   | M                  | N           |
| dateCreated    | DateTime       | Entity creation timestamp.                                                    | M                  | N           |
| dateModified   | DateTime       | Timestamp of the last modification of the entity.                             | M                  | Y           |
| source         | Text           | A sequence of characters giving the source of the entity data as a URL.       | M                  | Y           |
| dataProvider   | Text           | A sequence of characters identifying the originator of the harmonised entity. | M                  | Y           |

&lt;AgriParcelOperation&gt;&lt;Entity Specific Attributes&gt;

| Attribute Name | Attribute Type               | Description                                                                                | Mandatory /Optional | May be Null |
|----------------|------------------------------|--------------------------------------------------------------------------------------------|--------------------|-------------|
| refAgriParcel  | Reference                    | A reference to the unique id of the AgriParcel related to this operation.                  | M                  | N           |
| operationType  | Text                         | A choice from an enumerated list describing the operation performed on the parcel. One of:<br/><br/>**fertiliser, inspection, pesticide, water, other.**                                        | O                  | Y           |
| description    | Text                         | A description of the operation.                                                            | O                  | Y           |
| result         | Text                         | A description of the results of the operation. One of (“ok”, “aborted”).                   | O                  | Y           |
| startDate      | DateTime                     | The planned start date for the operation.                                                  | M                  | Y           |
| endDate        | DateTime                     | The planned end date for the operation.                                                    | M                  | Y           |
| status         | Text                         | A choice from an enumerated list describing the status. One of:   <br/><br/>**planned, ongoing, finished, scheduled, cancelled.**                                       | O                  | Y           |
| operator       | Person                       | The operator performing this action encoded as a Schema.org person. <br/>                       <https://schema.org/Person>                                                                 | O                  | Y           |
| dateStarted    | DateTime                     | Timestamp when the operation actually started to be performed.                             | O                  | Y           |
| dateFinished   | DateTime                     | Timestamp when the operation actually finished.                                            | O                  | Y           |
| refAgriProduct | Reference                    | A reference to the unique id of the AgriProduct used.                                      | O                  | Y           |
| quantity       | ExtQuantitativeValue (Number) | The amount of water or product used encoded as a ExtQuantitativeValue.                     | O                  | Y           |
| waterSource    | Text                         | A choice from an enumerated list describing the water source. One of: <br/><br/>**rainfall, watering.**                                                                     | O                  | Y           |

#### AgriParcelOperation JSON

The JSON code can be downloaded from:

<https://gist.github.com/GSMADeveloper/52a05ec2f4d55181cec3f1aba6157a1d>
```json
{
  "id": "e1e9d3a3-074f-46f1-9375-52000d05a62b",
  "type": "AgriParcelOperation",
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
  "refAgriParcel": {
    "value": "318366a9-7643-4d8e-9a11-c76a8c29d8eb",
    "type": "Reference"
  },
  "operationType": {
    "value": "fertiliser",
    "type": "Text"
  },
  "description": {
    "value": "Monthly fertiliser application",
    "type": "Text"
  },
  "result": {
    "value": "Completed successfully ",
    "type": "Text"
  },
  "startDate": {
    "value": "2016-08-22T10:18:16Z",
    "type": "DateTime"
  },
  "endDate": {
    "value": "2016-08-28T10:18:16Z",
    "type": "DateTime"
  },
  "status": {
    "value": "ongoing",
    "type": "Text"
  },
  "operator": {
    "value": {
      "givenName": "John Smith",
      "jobTitle": "Tractor Operator"
    },
    "type": "Person"
  },
  "dateStarted": {
    "value": "2016-08-22T10:18:16Z",
    "type": "DateTime"
  },
  "dateFinished": {
    "value": "2016-08-28T10:18:16Z",
    "type": "DateTime"
  },
  "refAgriProduct": {
    "value": "a8f616b8-13fb-473a-8e61-b7a80c6c93ec",
    "type": "Reference"
  },
  "quantity": {
    "value": {
      "value": 40,
      "unitCode": "GM"
    },
    "type": "ExtQuantitativeValue"
  },
  "waterSource": {
    "value": "watering",
    "type": "Text"
  }
}
```
