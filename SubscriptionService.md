### SubscriptionService

This entity contains a harmonised description of a subscription service. This entity is primarily associated with the Smart Home vertical segment and related IoT applications.

&lt;SubscriptionService&gt;&lt;Generic Attributes&gt;

| Attribute Name | Attribute Type | Description                                                                   | Mandatory/Optional | May be Null |
|----------------|----------------|-------------------------------------------------------------------------------|--------------------|-------------|
| id             | Text           | Unique id of this instance of this entity.                                    | M                  | N           |
| type           | Text           | Must be equal to "**SubscriptionService**".                                   | M                  | N           |
| dateCreated    | DateTime       | Entity creation timestamp.                                                    | M                  | N           |
| dateModified   | DateTime       | Timestamp of the last modification of the entity.                             | M                  | Y           |
| source         | Text           | A sequence of characters giving the source of the entity data as a URL.       | M                  | Y           |
| dataProvider   | Text           | A sequence of characters identifying the originator of the harmonised entity. | M                  | Y           |

&lt;SubscriptionService&gt;&lt;Entity Specific Attributes&gt;

| Attribute Name | Attribute Type | Description                      | Mandatory/Optional | May be Null |
|----------------|----------------|----------------------------------|--------------------|-------------|
| description    | Text           | The description of this service. | M                  | N           |
| offer          | Offer          | Encoded as Schema.org offer.<br/><br/> <https://schema.org/Offer>        | M                  | Y           |

#### SubscriptionService JSON

The JSON code can be downloaded from:

<https://gist.github.com/GSMADeveloper/1631ff51b1aa49a0422741f9b5631ecf>
```json
{
  "id": "a1e76f95-c627-4ec4-86dc-483431d25352",
  "type": "SubscriptionService",
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
  "description": {
    "value": "Broadband supply service",
    "type": "Text"
  },
  "offer": {
    "type": "Offer",
    "value": {
      "priceCurrency": "USD",
      "price": 1000,
      "description": "100 mbps fibre broadband service"
    }
  }
}
```
