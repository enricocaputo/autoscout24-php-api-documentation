# Resource - Publications

The Publications resource is a sub-resource of the Vehicle resource. It manages the complete lifecycle of the vehicle on AutoScout24 channels. Using this resource, a vehicle can be made available or inavailable on AutoScout24's marketplaces.

## Retrieve Channels

> ###Endpoint
> `GET` /vehicles/{vehicleId}/publications

> ###Request Example
> Retrieve the publication channels of a vehicle with id = 7e59591f-c5a3-974e-e452-2951040ae4ee:

```shell

curl https://api.autoscout24.com/vehicles/7e59591f-c5a3-974e-e452-2951040ae4ee/publications \
     -X GET \
     -H "X-AS24-Version: 1.1" \
     -H "Accept-Language: en-GB" \
     -H "Authorization: Bearer e7c00b24-9f5f-4909-88de-38f8d7ca08bf" 
```


Retrieve publication status of an existing vehicle.


Response shows whether at all and where a given vehicle has been published. Vehicles can be published to different publication channels (e.g. Publication channel ‘AS24’ means that the vehicle is visible on the AutoScout24 platform. Similarly,  publication channel 'AS24Dealer' means that the vehicle is visible on AutoScout24's dealer platform). In addition, the response message holds information about the URI of the vehicle on each published channel. **Please note that the URI might take some minutes before it becomes available.**


###Parameters

|Parameter Name|Type|Mandatory|Description|
|----|----|----|----|
|vehicleID|URI Parameter|Yes|Unique identifier for a given vehicle.|

###Headers

|Header Name|Data Type|Mandatory|Description|
|----|----|----|----|
|X-AS24-Version|String|Yes|Defines the API version used to serve the request. Current version number is 1.1|
|Accept-Language|String|No|Language used for returning results, e.g. en-GB. Please note that this header is also used to identify the marketplace URL of the vehicle's listing e.g. de-DE would return the URL of the vehicle on the German marketplace. Possible values are: de-DE , de-AT , fr-BE , fr-LU , fr-FR , nl-NL , nl-BE , es-ES , it-IT , en-GB. If the value of this header is not specified, then the default culture `en-GB` is used.|
|Authorization|String|Yes|The Bearer authentication token that was received via the OAuth authentication process.|


> ###Response Example

```json
{
  "_links": {
    "self": {
      "href": "/vehicles/7e59591f-c5a3-974e-e452-2951040ae4ee/publications"
    }
  },
  "_request": {
    "url": "/vehicles/7e59591f-c5a3-974e-e452-2951040ae4ee/publications",
    "body": null,
    "method": "GET"
  },
  "_response": {
    "type": "Success"
  },
  "_data": {
    "publicationchannels": [
      {
        "channelId": "AS24",
        "url": "http://ww3.autoscout24.de/classified/979814201"
      },
      {
        "channelId": "AS24Dealers",
        "url": "http://ww3.autoscout24.de/classified/979814201"
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
|_data|<a href="#publicationsData">Data</a>|The data object which contains the actual information that was asked for in the sent HTTP request. Below you can find the attributes that this object has.|

<span id="publicationsData"></span>

###Publication Data Object

The following table shows the fields that are contained in the `_data` object of the Response Payload:

|Field Name|Type|Description|
|----|----|----|
|publicationChannels|array, Enum|The array that has information of which channel the vehicle is published on. Possible values are: "AS24Dealers" and/or "AS24"|

### Error Codes

For the list of possible **error codes** in the `_response` object of the Response payload, please click <a href="#errors">here</a>.

##Publish a Vehicle

> ###Endpoint
> `POST` /vehicles/{vehicleId}/publications/{channelId}

> ###Request Example
> Publish the vehicle with id = 7e59591f-c5a3-974e-e452-2951040ae4ee on AutoScout24's platform :

```shell
curl https://api.autoscout24.com/vehicles/7e59591f-c5a3-974e-e452-2951040ae4ee/publications/AS24 \
     -X POST 
     -H "X-AS24-Version: 1.1" \
     -H "Accept-Language: en-GB" \
     -H "Authorization: Bearer e7c00b24-9f5f-4909-88de-38f8d7ca08bf" 
```

Publish an existing vehicle on a specific channel defined by its ID.

Vehicles can be published to different publication channels (e.g. Publication channel ‘AS24’ means that the vehicle is visible on the AutoScout24 platform. Similarly,  publication channel 'AS24Dealer' means that the vehicle is visible on AutoScout24's dealer platform). In addition, the response message holds information about the URI of the vehicle on each published channel. **Please note that the URI might take some minutes before it becomes available.**

###Parameters

|Parameter Name|Type|Mandatory|Description|
|----|----|----|----|
|vehicleID|URI Parameter|Yes|Unique identifier for a given vehicle.|
|channelId|URI Parameter|Yes|Unique identifier for the channel to publish the vehicle on. Possible values are: "AS24Dealers" or "AS24".|


###Headers

|Header Name|Data Type|Mandatory|Description|
|----|----|----|----|
|X-AS24-Version|String|Yes|Defines the API version used to serve the request. Current version number is 1.1|
|Accept-Language|String|No|Language used for returning results, e.g. en-GB. Please note that this header is also used to identify the marketplace URI of the vehicle's listing e.g. de-DE would return the URI of the vehicle on the German marketplace. Possible values are: de-DE , de-AT , fr-BE , fr-LU , fr-FR , nl-NL , nl-BE , es-ES , it-IT , en-GB. If the value of this header is not specified, then the default culture `en-GB` is used.|
|Authorization|String|Yes|The Bearer authentication token that was received via the OAuth authentication process.|

> ###Response Example

```json
{
  "_links": {
    "self": {
      "href": "/vehicles/7e59591f-c5a3-974e-e452-2951040ae4ee/publications"
    }
  },
  "_request": {
    "url": "/vehicles/7e59591f-c5a3-974e-e452-2951040ae4ee/publications/AS24",
    "body": null,
    "method": "POST"
  },
  "_response": {
    "type": "Success",
    "messages": [
      {
        "code": 10500,
        "messageType": "Info",
        "text": "Vehicle URL on PublicationChannel AS24 is: { http://ww3.autoscout24.de/classified/979814201 }. Please note that it might take a couple of minutes before the URI becomes available."
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


### Error Codes

For the list of possible **error codes** in the `_response` object of the Response payload, please click <a href="#errors">here</a>.

## Unpublish a Vehicle

> ###Endpoint
> `DELETE` /vehicles/{vehicleId}/publications/{chanelId}

> ###Request Example
> Unpublish the vehicle with id = 7e59591f-c5a3-974e-e452-2951040ae4ee from AutoScout24's platform :

```shell
curl https://api.autoscout24.com/vehicles/7e59591f-c5a3-974e-e452-2951040ae4ee/publications/AS24 \
     -X DELETE 
     -H "X-AS24-Version: 1.1" \
     -H "Accept-Language: en-GB" \
     -H "Authorization: Bearer e7c00b24-9f5f-4909-88de-38f8d7ca08bf" 
```

Unpublish existing vehicle from a specific publication channel.

###Parameters

|Parameter Name|Type|Mandatory|Description|
|----|----|----|----|
|vehicleID|URI Parameter|Yes|Unique identifier for a given vehicle.|
|channelId|URI Parameter|Yes|Unique identifier for the channel to publish the vehicle on. Possible values are: "AS24Dealers" or "AS24".|


###Headers

|Header Name|Data Type|Mandatory|Description|
|----|----|----|----|
|X-AS24-Version|String|Yes|Defines the API version used to serve the request. Current version number is 1.1|
|Accept-Language|String|No|Language used for returning results, e.g. en-GB.|
|Authorization|String|Yes|The Bearer authentication token that was received via the OAuth authentication process.|

> ###Response Example

```json
{
  "_links": {
    "self": {
      "href": null
    }
  },
  "_request": {
    "url": "/vehicles/7e59591f-c5a3-974e-e452-2951040ae4ee/publications/AS24",
    "body": null,
    "method": "DELETE"
  },
  "_response": {
    "type": "Success"
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


### Error Codes

For the list of possible **error codes** in the `_response` object of the Response payload, please click <a href="#errors">here</a>.
