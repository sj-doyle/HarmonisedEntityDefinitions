### AgriProduct

This entity contains a harmonised description of a generic agricultural product. This entity is primarily associated with the agricultural vertical and related IoT applications.

&lt;AgriProduct&gt;&lt;Generic Attributes&gt;

| Attribute Name | Attribute Type | Description                                                                   | Mandatory /Optional | May be Null |
|----------------|----------------|-------------------------------------------------------------------------------|--------------------|-------------|
| id             | Text           | Unique id of this instance of this entity.                                    | M                  | N           |
| type           | Text           | Must be equal to "**AgriProduct**".                                           | M                  | N           |
| dateCreated    | DateTime       | Entity creation timestamp.                                                    | M                  | N           |
| dateModified   | DateTime       | Timestamp of the last modification of the entity.                             | M                  | Y           |
| source         | Text           | A sequence of characters giving the source of the entity data as a URL.       | M                  | Y           |
| dataProvider   | Text           | A sequence of characters identifying the originator of the harmonised entity. | M                  | Y           |

&lt;AgriProduct&gt;&lt;Entity Specific Attributes&gt;

| Attribute Name     | Attribute Type | Description                                                     | Mandatory /Optional | May be Null |
|--------------------|----------------|-----------------------------------------------------------------|--------------------|-------------|
| name               | Text           | The name of this agricultural product.                          | M                  | N           |
| refAgriProductType | Reference      | Unique id of this product type. Selected from AgriProductType.  | M                  | N           |
| description        | Text           | A description of this agricultural product.                     | O                  | Y           |
| manufacturerName   | Text           | The name of manufacturer of this agricultural product.          | O                  | Y           |
| brandName          | Text           | A description of this agricultural product brand name.          | O                  | Y           |
| supplierName       | Text           | The details of the local retailer of this agricultural product. | O                  | Y           |
| category           | Array          | A choice from an enumerated list. including: <br/><br/>**fertiliser, herbicide, pesticide, other**                      | O                  | Y           |

#### AgriProduct JSON

The JSON code can be downloaded from:

<https://gist.github.com/GSMADeveloper/73d3eb307e8b2431fed1b7c91248c32a>
```json
{
  "id": "410ee08d-805e-4aab-9fba-065533b7bd76",
  "type": "AgriProduct",
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
  "name": {
    "value": "Banana seedlings",
    "type": "Text"
  },
  "refProductType": {
    "value": "ec6de3dc-7668-11e6-9c73-f752f61f61f9",
    "type": "Reference"
  },
  "description": {
    "value": "Banana cultivar Musa acuminata",
    "type": "Text"
  },
  "manufacturerName": {
    "value": "ACME Banana Supplies Company Ltd",
    "type": "Text"
  },
  "brandName": {
    "value": "5ADay",
    "type": "Text"
  },
  "supplierName": {
    "value": "A&B Wholesaling Limited",
    "type": "Text"
  },
  "category": [
    "other"
  ]
}
```
