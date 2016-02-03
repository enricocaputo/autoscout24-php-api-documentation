# Resource - Models

The Models resource is a sub-resource of the Makes resource. It offers the needed endpoints to retrieve information about the available models of each make that are supported by the AutoScout24 marketplace.

## Retrieve Makes List

> ###Endpoint
> `GET` /makes/{makeId}/models

> ###Request Example
> Get the list of models of BMW which has the ID = 13:

```shell

curl https://api.autoscout24.com/makes/13/models \
     -X GET \
     -H "X-AS24-Version: 1.1" \
     -H "Accept-Language: en-GB" 
```


Retrieve a list of supported vehicle models for a given vehicle make.

- Response shows whether a given make is of *vehicleType* ‘C’ (= Car) and/or *vehicleType* ‘B’ (= Bike).

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
      "href": "/makes/13/models"
    },
    "models": [
      {
        "href": "/makes/13/models/71021"
      },
      {
        "href": "/makes/13/models/50161"
      },
      ...
      {
        "href": "/makes/13/models/21073"
      }
    ]
  },
  "_request": {
    "url": "/makes/13/models",
    "body": null,
    "method": "GET"
  },
  "_response": {
    "type": "Success"
  },
  "_data": {
    "models": [
      {
        "id": 71021,
        "make": 13,
        "name": "100 CS",
        "vehicleType": "B"
      },
      {
        "id": 50161,
        "make": 13,
        "name": "C1",
        "vehicleType": "B"
      },
      ...
      {
        "id": 21073,
        "make": 13,
        "name": "Others",
        "vehicleType": "C"
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
|_data|<a href="#modelsData">Data</a>|The data object which contains the actual information that was asked for in the sent HTTP request. Below you can find the attributes that this object has.|

<span id="modelsData"></span>

###Models Data Object

The following table shows the fields that are contained in the `_data` object of the Response Payload:

|Field Name|Type|Description|
|----|----|----|
|models|array, <a href="#modelObject1">Model</a>|An array that holds the model objects.|

<span id="modelObject1"></span>
###Model Object

|Field Name|Type|Description|
|----|----|----|----|
|id|Integer|The unique identifier of the model object.|
|make|Integer|The unique identifier of the make.|
|name|String|The name of the vehicle's model.|
|vehicleType|Enum|Enumeration to identify whether the model is a Car ("C") or a Bike ("B").|

### Error Codes

For the list of possible **error codes** in the `_response` object of the Response payload, please click <a href="#errors">here</a>.

##Retrieve Model's Information

> ###Endpoint
> `GET` /makes/{makeId}/models/{modelId}

> ###Request Example
> Retrieve the information of the BMW model 730 that has the ID = 1659 :

```shell
curl https://api.autoscout24.com/makes/13/models/1659 \
     -X GET \
     -H "X-AS24-Version: 1.1" \
     -H "Accept-Language: en-GB" 
```


Retrieve details of a given model.

- Response shows whether a given make is of *vehicleType* ‘C’ (= Car) and/or *vehicleType* ‘B’ (= Bike).

###Parameters

|Parameter Name|Type|Mandatory|Description|
|----|----|----|----|
|makeId|URI Parameter|Yes|Unique identifier for a given make.|
|modelId|URI Parameter|Yes|Unique identifier for a given model.|

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
      "href": "/makes/13/models/1659"
    }
  },
  "_request": {
    "url": "/makes/13/models/1659",
    "body": null,
    "method": "GET"
  },
  "_response": {
    "type": "Success",
    "objectId": "1659"
  },
  "_data": {
    "model": {
      "id": 1659,
      "make": 13,
      "name": "730",
      "vehicleType": "C"
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
|_data|<a href="#modelData">Data</a>|The data object which contains the actual information that was asked for in the sent HTTP request. Below you can find the attributes that this object has.|

<span id="modelData"></span>

###Model Data Object

The following table shows the fields that are contained in the `_data` object of the Response Payload:

|Field Name|Type|Description|
|----|----|----|
|models|<a href="#modelObject2">Model</a>|The object that holds information about the requested model.|

<span id="modelObject2"></span>
###Model Object

|Field Name|Type|Description|
|----|----|----|----|
|id|Integer|The unique identifier of the model object.|
|make|Integer|The unique identifier of the make.|
|name|String|The name of the vehicle's model.|
|vehicleType|Enum|Enumeration to identify whether the model is a Car ("C") or a Bike ("B").|

### Error Codes

For the list of possible **error codes** in the `_response` object of the Response payload, please click <a href="#errors">here</a>.

