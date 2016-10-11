### WeatherForecast

This entity contains a harmonised description of a Weather Forecast. This entity is primarily associated with the vertical segments of the environment and agriculture but is applicable to many different applications.

&lt;WeatherForecast&gt;&lt;Generic Attributes&gt;

| Attribute Name | Attribute Type | Description                                                                   | Mandatory /Optional | May be Null |
|----------------|----------------|-------------------------------------------------------------------------------|--------------------|-------------|
| id             | Text           | Unique id of this instance of this entity.                                    | M                  | N           |
| type           | Text           | Must be equal to "**WeatherForecast**".                                       | M                  | N           |
| dateCreated    | DateTime       | Entity creation timestamp.                                                    | M                  | N           |
| dateModified   | DateTime       | Timestamp of the last modification of the entity.                             | M                  | Y           |
| source         | Text           | A sequence of characters giving the source of the entity data as a URL.       | M                  | Y           |
| dataProvider   | Text           | A sequence of characters identifying the originator of the harmonised entity. | M                  | Y           |

&lt;WeatherForecast&gt;&lt;Entity Specific Attributes&gt;

| Attribute Name           | Attribute Type     | Description                                                                                                                                                                                                                                                                | Mandatory /Optional | May be Null |
|--------------------------|--------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------|-------------|
| location                 | geo:json           | The geo:json encoded map location (point or polygon), of this weather forecast.                                                                                                                                                                                            | M                  | N           |
| dateRetrieved            | DateTime           | The date and time the forecast was retrieved in ISO8601 UTC format.                                                                                                                                                                                                        | M                  | N           |
| dateIssued               | DateTime           | The date and time the forecast was issued by the meteorological bureau in ISO8601 UTC format.                                                                                                                                                                              |                    |             |
| weatherType              | Text               | The weather type. A choice from an enumerated list. One of:                                                <br/><br/> **notAvailable, clearNight, sunnyDay, partlyCloudy, mist, fog, cloudy, overcast, lightRainShower, drizzle, lightRain, heavy RainShower, heavyRain, sleetShower, sleet, hailShower, hail, lightSnow Shower, lightSnow, heavySnowShower,heavySnow, thunderShower, thunder.**  | M                  | N           |
| visibility               | Text               | A choice from an enumerated list. One of:                                                                    <br/><br/> **unknown, veryPoor, poor, moderate, good, veryGood, excellent.**                                                                                                                                                                                                           | M                  | N           |
| name                     | Text               | The name of the weather forecast location.                                                                                                                                                                                                                                 | M                  | Y           |
| validity                 | Text               | Includes the validity period for this forecast as a date/time range as a textvalue.                            <br/><br/> The **validity** is in the form of                                    <br/><br/> **validFrom/validTo**                                                  <br/><br/> **validFrom** -- The date and time the forecast is valid from expressed as an ISO8601 UTC format sequence of characters.                      <br/><br/> **validTo**: The date and time the forecast is valid to expressed as an ISO8601 UTC format sequence of characters. For example:                        <br/><br/> **YYYY-MM-DDThh:mmZ/YYYY-MM-DDThh:mmZ**                                                                                                                                                                                                                                     | O                  | Y           |
| dayMinimum               | Array of text      | Includes the attribute, value tuples:                                                                          <br/><br/> **temperature, feelsLikeTemperature, relativeHumidity**               <br/><br/> **temperature** -- The forecasted minimum temperature for the period in degrees Celsius.                                                              <br/><br/> **feelsLikeTemperature** – The forecasted feels like temperature for the period in degrees Celsius.                                                    <br/><br/> **relativeHumidity** -- The relative humidity expressed a number between 0 ≤ RelativeHumidity ≤ 1.                                                                                                                                                                          | O                  | Y           |
| dayMaximum               | Array of Text      | Includes the attribute, value tuples:                                                                          <br/><br/> **temperature, feelsLikeTemperature, relativeHumidity**                <br/><br/> temperature -- The forecasted maximum temperature for the period in degrees Celsius.                                                                  <br/><br/> feelsLikeTemperature – The forecasted feels like temperature for the period in degrees Celsius.                                                        <br/><br/> relativeHumidity -- The relative humidity expressed a number between 0 ≤ RelativeHumidity ≤ 1.                                                                                                                                                                              | O                  | Y           |
| address                  | PostalAddress      | The weather forecast location encoded as a Schema.org PostalAddress.                                            <br/><br/> [https://schema.org/PostalAddress](https://schema.org/Address)                                                                                                                                                                                                              | M                  | Y           |
| temperature              | Number             | The temperature expressed in degrees Celsius.                                                                                                                                                                                                                              | M                  | Y           |
| windDirection            | Number             | The wind direction expressed in degrees compared to geographic North (measured clockwise).                                                                                                                                                                                 | O                  | Y           |
| windSpeed                | Number             | The forecasted wind speed in m/s.                                                                                                                                                                                                                                          | O                  | Y           |
| uVIndexMax               | Number             | The maximum UV index for the period, based on the World Health Organization's UV Index measure.                                                                                                                                                                            | O                  | Y           |
| relativeHumidity         | Number             | The relative humidity expressed a number between                                                        <br/><br/> 0 ≤ RelativeHumidity ≤ 1.                                                                                                                                                                                                                                                   | O                  | Y           |
| precipitationProbability | Number             | The probability of precipitation, expressed as a number between                                      <br/><br/> 0 ≤ precipitationProbability ≤ 1.                                                                                                                                                                                                                                           | O                  | Y           |
| refPointOfInterest       | Array of Reference | A JSON encode sequence of characters referencing the unique ids of the associated group of pointOfInterests.                                                                                                                                                               | O                  | Y           |

#### WeatherForecast JSON

The JSON code can be downloaded from:

<https://gist.github.com/GSMADeveloper/c7beae7a0e9797d2358db6cf1c190fc2>
```json
{
  "id": "7453c443-290d-44ef-a60f-d4c087010c88",
  "type": "WeatherForecast",
  "dateCreated": {
    "value": "2016-08-08 T10:18:16Z ",
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
  "dateRetrieved": {
    "value": "2016-08-16T10:18:16Z",
    "type": "DateTime"
  },
  "dateIssued": {
    "value": "2016-08-10T10:18:16Z",
    "type": "DateTime"
  },
  "weatherType": {
    "value": "sunnyDay",
    "type": "Text"
  },
  "visibility": {
    "value": "Good",
    "type": "Text"
  },
  "name": {
    "value": "London City",
    "type": "Text"
  },
  "validity": {
    "value": "2016-08-10T10:18:16Z/2016-08-29T10:18:16Z",
    "type": "Text"
  },
  "dayMinimum": [
    "temperature, 30, CEL",
    "feelsLikeTemperature, 32, CEL",
    "relativeHumidity, 0.22, P1"
  ],
  "dayMaximum": [
    "temperature, 33, CEL",
    "feelsLikeTemperature, 328, CEL",
    "relativeHumidity, 0.52, P1"
  ],
  "address": {
    "type": "PostalAddress",
    "value": {
      "addressLocality": "London",
      "postalCode": "EC4N 8AF",
      "streetAddress": "25 Walbrook"
    }
  },
  "temperature": {
    "value": 30,
    "type": "Number"
  },
  "windDirection": {
    "value": 122,
    "type": "Number"
  },
  "windSpeed": {
    "value": 3,
    "type": "Number"
  },
  "uVIndexMax": {
    "value": 5,
    "type": "Number"
  },
  "relativeHumidity": {
    "value": 0.1,
    "type": "Number"
  },
  "precipitationProbability": {
    "value": 0.05,
    "type": "Number"
  },
  "refPointOfInterest": [
    "d0d88168-780c-11e6-b934-2b9831af3c6f"
  ]
}
```
