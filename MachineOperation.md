### MachineOperation

This entity contains a harmonised description of a generic machine operation. This entity is primarily associated with the industry segment and related IoT applications. Each MachineOperation instance will be related to a specific Machine instance.

&lt;MachineOperation&gt;&lt;Generic Attributes&gt;

| Attribute Name | Attribute Type | Description                                                                   | Mandatory /Optional | May be Null |
|----------------|----------------|-------------------------------------------------------------------------------|--------------------|-------------|
| id             | Text           | Unique id of this instance of this entity.                                    | M                  | N           |
| type           | Text           | Must be equal to "**MachineOperation**".                                      | M                  | N           |
| dateCreated    | DateTime       | Entity creation timestamp.                                                    | M                  | N           |
| dateModified   | DateTime       | Timestamp of the last modification of the entity.                             | M                  | Y           |
| source         | Text           | A sequence of characters giving the source of the entity data as a URL.       | M                  | Y           |
| dataProvider   | Text           | A sequence of characters identifying the originator of the harmonised entity. | M                  | Y           |

&lt;MachineOperation&gt;&lt;Entity Specific Attributes&gt;

| Attribute Name  | Attribute Type | Description                                                                                                                                      | Mandatory /Optional | May be Null |
|-----------------|----------------|--------------------------------------------------------------------------------------------------------------------------------------------------|--------------------|-------------|
| refMachine      | Reference      | Refers to the specific machine instance that this machineOperation record relates to.                                                            | M                  | N           |
| operationType   | Text           | Defines the type of operation conducted/ requested. This will be one of a defined list of operation types specific to the machine/ machineModel. | M                  | N           |
| description     | Text           | A description of the operation conducted or applied.                                                                                             | O                  | Y           |
| result          | Text           | A description of the results of the operation. One of (“**ok**”, “**aborted**”).                                                                 | O                  | Y           |
| startDate       | DateTime       | The planned start date for the operation.                                                                                                        | M                  | Y           |
| endDate         | DateTime       | The planned end date for the operation.                                                                                                          | M                  | Y           |
| status          | Text           | A choice from an enumerated list describing the status. One of: <br/><br/> **planned, ongoing, finished, scheduled, cancelled.**                                                                                             | O                  | Y           |
| operator        | Person         | The operator performing this action encoded as a Schema.org person. <br/><br/> <https://schema.org/Person>                                                                                                                       | O                  | Y           |
| dateStarted     | DateTime       | Timestamp when the operation actually started to be performed.                                                                                   | O                  | Y           |
| dateFinished    | DateTime       | Timestamp when the operation actually finished.                                                                                                  | O                  | Y           |
| commandSequence | Text           | The command sequence executed/ requested for the machine in a representation format relevant to the machine.                                     | O                  | Y           |

#### MachineOperation JSON

The JSON code can be downloaded from:

<https://gist.github.com/GSMADeveloper/a2a2795c194831ac06c48222eb49e2ce>
```json
{
  "id": "27577638-bd8a-4732-b418-fc8b949a0b0f",
  "type": "MachineOperation",
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
  "refMachine": {
    "value": "2033a7c7-d31b-48e7-91c2-014dc426c29e",
    "type": "Reference"
  },
  "operationType": {
    "value": "tShirtPrint",
    "type": "Text"
  },
  "description": {
    "value": "Printing of 1000 T-shirts",
    "type": "Text"
  },
  "result": {
    "value": "ok",
    "type": "Text"
  },
  "startDate": {
    "value": "2016-08-20T10:18:16Z",
    "type": "DateTime"
  },
  "endDate": {
    "value": "2016-08-18T14:18:16Z",
    "type": "DateTime"
  },
  "status": {
    "value": "finished",
    "type": "Text"
  },
  "operator": {
    "value": {
      "name": "Fred Quimby",
      "jobTitle": "Print Supervisor"
    },
    "type": "Person"
  },
  "dateStarted": {
    "value": "2016-08-20T10:18:16Z",
    "type": "DateTime"
  },
  "dateFinished": {
    "value": "2016-08-18T14:18:16Z",
    "type": "DateTime"
  },
  "commandSequence": {
    "value": "Select inks. Prepare print masks. Print shirts. Clean print heads and rollers ",
    "type": "Text"
  }
}
```
