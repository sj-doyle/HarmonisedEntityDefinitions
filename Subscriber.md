### Subscriber

This entity contains a harmonised description of a subscriber to a service. This entity is primarily associated with the Smart Home vertical segment and related IoT applications.

&lt;Subscriber&gt;&lt;Generic Attributes&gt;

| Attribute Name | Attribute Type | Description                                                                   | Mandatory/Optional | May be Null |
|----------------|----------------|-------------------------------------------------------------------------------|--------------------|-------------|
| id             | Text           | Unique id of this instance of this entity.                                    | M                  | N           |
| type           | Text           | Must be equal to "**Subscribe**r".                                            | M                  | N           |
| dateCreated    | DateTime       | Entity creation timestamp.                                                    | M                  | N           |
| dateModified   | DateTime       | Timestamp of the last modification of the entity.                             | M                  | Y           |
| source         | Text           | A sequence of characters giving the source of the entity data as a URL.       | M                  | Y           |
| dataProvider   | Text           | A sequence of characters identifying the originator of the harmonised entity. | M                  | Y           |

&lt;Subscriber&gt;&lt;Entity Specific Attributes&gt;

| Attribute Name       | Attribute Type     | Description                                                                                                                                                  | Mandatory/Optional | May be Null |
|----------------------|--------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------|-------------|
| subscriptionId       | Reference          | A reference to the unique id of the subscription service.                                                                                                    | M                  | N           |
| startDate            | DateTime           | The start date time for this subscription as an ISO8601 sequence of characters in UTC.                                                                       | O                  | Y           |
| endDate              | DateTime           | The end date time for this subscription as an ISO8601 sequence of characters in UTC.                                                                         | O                  | Y           |
| duration             | Number             | The duration of the subscription in calendar months.                                                                                                         | O                  | Y           |
| category             | Array of Text      | The category of subscription. A selection from an enumerated list including: <br/><br/> **prepay, postpay, utility, broadband, electric, gas, heat, water, landline, mobile, tv, security, financial, energy management, other.**                     | O                  | Y           |
| averageMonthly Usage | Number             | Average monthly usage of the subscription service.                                                                                                           | O                  | Y           |
| subscribed           | Array of Reference | An array containing a JSON encoded sequence of characters referencing the unique ids of those persons or organisations that have subscribed to this service. <br/><br/> Related to a Schema.org person or organization. <br/><br/> <https://schema.org/Person>   <br/><https://schema.org/Organization>                                                                                                                             | O                  | Y           |

#### Subscriber JSON

The JSON code can be downloaded from:

<https://gist.github.com/GSMADeveloper/a2be9b6079309c8ea2d7a6830c31c306>
```json
{
  "id": "c1716dea-6a4d-4171-a733-916123942f09",
  "type": "Subscriber",
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
  "subscriptionId": {
    "value": "65b1ccb0-ee32-41c1-9746-7ba83fb0f0f1",
    "type": "Reference"
  },
  "startDate": {
    "value": "2016-08-22T10:18:16Z",
    "type": "DateTime"
  },
  "endDate": {
    "value": "2016-08-28T10:18:16Z",
    "type": "DateTime"
  },
  "duration": {
    "value": 12,
    "type": "Number"
  },
  "category": [
    "utility"
  ],
  "averageMonthlyUsage": {
    "value": 28,
    "type": "Number"
  },
  "subscribed": [
    "31dd0e29-45b6-476f-9756-a70f8141dcf3"
  ]
}
```
