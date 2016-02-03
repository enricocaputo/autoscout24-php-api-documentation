# Resource - References

The References resource offers the needed endpoints to retrieve information about the enumerated fields needed to communicate with the AutoScout24 RESTful API.

## Retrieve References List

> ###Endpoint
> `GET` /references

> ###Request Example
> Get the list of reference types and fields that are supported by AutoScout24:

```shell

curl https://api.autoscout24.com/references \
     -X GET \
     -H "X-AS24-Version: 1.1" \
     -H "Accept-Language: en-GB" 
```


Retrieve reference information for enumerated fields like vehicle BodyColor, DriveType, VehicleBody, available ad products or supported cultures for returning results.

Information for the following reference types can be obtained:

- Availability
- BodyColor
- Country
- Culture
- DriveType
- EfficiencyClass
- EmissionsSticker
- Equipment
- FuelCategory
- FuelType
- IncludedService
- InteriorColor
- PollutionClass
- PriceType
- Product
- PublicationChannel
- Transmission
- Upholstery
- VehicleBody
- VehicleOfferType
- VehicleType


###Headers

|Header Name|Data Type|Mandatory|Description|
|----|----|----|----|
|X-AS24-Version|String|Yes|Defines the API version used to serve the request. Current version number is 1.1|
|Accept-Language|String|No|Language used for returning results, e.g. en-GB.|

> ###Response Example

```json

{
  "_links": {
    "self": {
      "href": "/references"
    }
  },
  "_request": {
    "url": "/references",
    "body": null,
    "method": "GET"
  },
  "_response": {
    "type": "Success"
  },
  "_data": {
    "references": [
      {
        "id": "1",
        "name": "Immediately",
        "vehicleType": null,
        "referenceType": "Availability",
        "country": null
      },
      {
        "id": "2",
        "name": "Available from",
        "vehicleType": null,
        "referenceType": "Availability",
        "country": null
      },
	...
	,
      {
        "id": "1",
        "name": "HU/AU neu",
        "vehicleType": [
          "B",
          "C"
        ],
        "referenceType": "IncludedService",
        "country": [
          "DE"
        ]
      },
      {
        "id": "2",
        "name": "APK tot",
        "vehicleType": [
          "B",
          "C"
        ],
        "referenceType": "IncludedService",
        "country": [
          "NL"
        ]
      },
	...
      {
        "Id": "B",
        "ReferenceType": "VehicleType",
        "Name": "Bike",
        "CountryId": null,
        "VehicleType": null
      },
      {
        "Id": "C",
        "ReferenceType": "VehicleType",
        "Name": "Car",
        "CountryId": null,
        "VehicleType": null
      }
    ]
  }
}
```

###Response Payload Parameters

The HTTP response message that's received has the following body attributes:

|Field Name|Type|Description|
|----|----|----|
|_links|Object|The links object that has all the hypermedia links of the requested resource.|
|_request|<a href="#request-object">Request</a>|An object that contains information about the sent HTTP request message. This object is mostly needed for debugging, logging, and monitoring purposes.|
|_response|<a href="#response-object">Response</a>|An object that contains information about what happened on the server e.g. it gives information if the request was processed successfully.|
|_data|<a href="#referencesData">Data</a>|The data object which contains the actual information that was asked for in the sent HTTP request. Below you can find the attributes that this object has.|

<span id="referencesData"></span>

###References Data Object

The following table shows the fields that are contained in the `_data` object of the Response Payload:

|Field Name|Type|Description|
|----|----|----|
|references|array,<a href="#referenceObject">Reference</a>|An array that holds the reference objects.|

<span id="referenceObject"></span>
###Reference Object

|Field Name|Type|Description|
|----|----|----|----|
|id|Integer|The unique identifier of the reference object.|
|ReferenceType|Enum|Enumeration value of what Reference Type this object is. Values of the enumeration are: (Availability, BodyColor, Country, Culture, DriveType, EfficiencyClass, EmissionsSticker, Equipment, FuelCategory, FuelType, IncludedService, InteriorColor, PollutionClass, PriceType, Product, PublicationChannel, Transmission, Upholstery, VehicleBody, VehicleOfferType, VehicleType)|
|name|String|The name of the reference object.|
|vehicleType|array, Enum|An array of enumeration values to identify whether the value is for Cars ("C"), Bikes ("B"), or both. If the value is null, it means that vehicleType is not applicable to the Reference Type.|
|country|array, Enum|An array of the countries to which this reference instance can exist. A null value indicates that the country is not applicable for the refernce type.|

### Error Codes

For the list of possible **error codes** in the `_response` object of the Response payload, please click <a href="#errors">here</a>.
