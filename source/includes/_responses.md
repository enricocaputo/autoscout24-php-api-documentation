# API Responses

The AutoScout24 API communicates through standard HTTP status codes paired with response objects (JSON).
These response objects contain codes that can be evaluated by the business logic of the API client.

## HTTP Status Codes
Generally the following pattern will apply for HTTP status codes:

|Status Code Pattern|Response classification|
|----|----|
|**2xx** | The request was successfully received, understood, and accepted |
|**4xx** | An error in the request (usually a bad parameter has been set)|

In detail the following HTTP Status codes are defined:

|Status Code|Description|
|-----|-----|
|**200**| request has been processed successfully|
|**201**| resource creation has been done successfully|
|**400**|	bad request|
|**401**|	unauthorized|
|**403**|	forbidden|


## Response object (JSON)

> ###Response Envelope Objects:

```json
{
  "_links": {
    "self": {
      "href": ""
    }
  },
  "_request": {
    "url": "",
    "body": "",
    "method": ""
  },
  "_response": {
    "type": "",
    "objectId": "",
    "messages": [
      {
        "code": 00000,
        "messageType": "",
        "text": ""
      }
    ]
  },
  "_data": {
	
  }
}
```

The accompanying response objects are as detailed as possible without being unwieldy. The objects contain the
following information:

|Field Name|Type|Description|
|----|----|----|
|_links|Object|The hypermedia links object that contains information about the related resources to the current resource.|
|_request|<a href="#request-object">Request</a>|An object that contains information about the sent HTTP request message. This object is mostly needed for debugging, logging, and monitoring purposes.|
|_response|<a href="#response-object">Response</a>|An object that contains information about what happened on the server e.g. it gives information if the request was processed successfully.|
|_data|Object|The object that contains the actual information about the specific resource that was requested in the HTTP message. This object is mainly used when sending GET requests to retrieve information.|

### Request Object

The following table contains the fields that could appear in the `_request` object of the API responses:

|Field Name|Type|Description|
|----|----|----|
|url|String|The URL that was used by the client application to send the HTTP request.|
|method|String|The HTTP method that was used by the client application to send the HTTP request.|
|body|String|The content of the body that was sent in the HTTP request.|

### Response Object

The following table contains the fields that could appear in the `_response` object of the API responses:

|Field Name|Type|Description|
|----|----|----|
|type|Enum|An enumeration that identifies what happened to the request that was sent. Tha possible values are: (Success, Error)|
|objectId|String|The ID of the object that was affected by the sent HTTP request.|
|messages|<a href="#message-object">Message</a> Array|An array of the messages that give information about processed object.|

### Message Object

The following table contains the fields that could appear in the `Message` object of the `_response` object:

|Field Name|Type|Description|
|----|----|----|
|code|Integer|A unique code that identifies what has happened while processing the HTTP request. For list of codes please click <a href="#errors">here</a>..|
|messageType|Enum|An enumeration value that identifies the type of the message. Possible values are: (Error, Info, Warning) |
|text|String|A text description of the message. This text can be utilized by showing it to the end user of client application.|
