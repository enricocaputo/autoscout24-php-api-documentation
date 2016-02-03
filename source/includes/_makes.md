# Resource - Makes

The Makes resource offers the needed endpoints to retrieve information about the available makes that are supported by the AutoScout24 marketplace.

## Retrieve Makes List

> ###Endpoint
> `GET` /makes

> ###Request Example
> Get the list of makes that AutoScout24 supports.

```shell

curl https://api.autoscout24.com/makes \
     -X GET \
     -H "X-AS24-Version: 1.1" \
     -H "Accept-Language: en-GB" 
```

Retrieve a list of supported vehicle makes.

- Response shows whether a given make is of *vehicleType* ‘C’ (= Car) and/or *vehicleType* ‘B’ (= Bike).

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
      "href": "/makes"
    },
    "makes": [
      {
        "href": "/makes/50001"
      },
      {
        "href": "/makes/51637"
      },
	...
      {
        "href": "/makes/16394"
      }
    ]
  },
  "_request": {
    "url": "/makes",
    "body": null,
    "method": "GET"
  },
  "_response": {
    "type": "Success"
  },
  "_data": {
    "makes": [
      {
        "id": 50001,
        "name": "A.T.U",
        "vehicleType": [
          "B"
        ]
      },
      {
        "id": 51637,
        "name": "Access",
        "vehicleType": [
          "B"
        ]
      },
	...
      {
        "id": 16394,
        "name": "ZAZ",
        "vehicleType": [
          "C"
        ]
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
|_data|<a href="#makesData">Data</a>|The data object which contains the actual information that was asked for in the sent HTTP request. Below you can find the attributes that this object has.|

<span id="makesData"></span>

###Makes Data Object

The following table shows the fields that are contained in the `_data` object of the Response Payload:

|Field Name|Type|Description|
|----|----|----|
|makes|array, <a href="#makeObject1">Make</a>|An array that holds the make objects.|

<span id="makeObject1"></span>
###Make Object

|Field Name|Type|Description|
|----|----|----|----|
|id|Integer|The unique identifier of the make object.|
|name|String|The name of the vehicle's make.|
|vehicleType|array, Enum|An array of enumeration values to identify whether the make manufactures Cars ("C"), Bikes ("B"), or both.|

### Error Codes

For the list of possible **error codes** in the `_response` object of the Response payload, please click <a href="#errors">here</a>.

##Retrieve Make's Information

> ###Endpoint
> `GET` /makes/{makeId}

> ###Request Example
> Retrieve the information of the BMW make that has the id = 13 :

```shell
curl https://api.autoscout24.com/makes/13 \
     -X GET \
     -H "X-AS24-Version: 1.1" \
     -H "Accept-Language: en-GB" 
```

Retrieve details of a given make.

Response shows whether a given make is of vehicleType ‘C’ (= Car) and/or vehicleType ‘B’ (= Bike).

###Parameters

|Parameter Name|Type|Mandatory|Description|
|----|----|----|----|
|makeId|URI Parameter|Yes|Unique identifier for a given make.|

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
      "href": "/makes/13"
    }
  },
  "_request": {
    "url": "/makes/13",
    "body": null,
    "method": "GET"
  },
  "_response": {
    "type": "Success",
    "objectId": "13"
  },
  "_data": {
    "make": {
      "id": 13,
      "name": "BMW",
      "vehicleType": [
        "B",
        "C"
      ]
    }
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
|_data|<a href="#makeData">Data</a>|The data object which contains the actual information that was asked for in the sent HTTP request. Below you can find the attributes that this object has.|

<span id="makeData"></span>

###Make Data Object

The following table shows the fields that are contained in the `_data` object of the Response Payload:

|Field Name|Type|Description|
|----|----|----|
|make|<a href="#makeObject2">Make</a>|The object that holds information about the requested make.|

<span id="makeObject2"></span>
###Make Object

|Field Name|Type|Description|
|----|----|----|----|
|id|Integer|The unique identifier of the make object.|
|name|String|The name of the vehicle's make.|
|vehicleType|array, Enum|An array of enumeration values to identify whether the make manufactures Cars ("C"), Bikes ("B"), or both.|

### Error Codes

For the list of possible **error codes** in the `_response` object of the Response payload, please click <a href="#errors">here</a>.

