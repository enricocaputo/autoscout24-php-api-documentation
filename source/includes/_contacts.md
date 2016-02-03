# Resource - Contacts

The Contacts resource is a sub-resource of the Vehicle resource. It manages the complete lifecycle of the contacts of a specific vehicle of private sellers on the AutoScout24 marketplace. This includes inserting, updating, retrieving, and deleting contacts of a vehicle.

## Create a Contact

> ###Endpoint
> `POST` /vehicles/{vehicleId}/contacts

> ###Request Example
> Uploading an image and attaching it to a vehicle with id = 7e59591f-c5a3-974e-e452-2951040ae4ee:

```shell

curl https://api.autoscout24.com/vehicles/7e59591f-c5a3-974e-e452-2951040ae4ee/images \
     -X POST \
     -H "X-AS24-Version: 1.1" \
     -H "Accept-Language: en-GB" \
     -H "Content-Type: multipart/form-data; boundary=----WebKitFormBoundary7MA4YWxkTrZu0gW" 
     -H "Authorization: Bearer e7c00b24-9f5f-4909-88de-38f8d7ca08bf" 
     -F "file=@carFoto.jpg"
```

> ###Response Example

```json

{
  "_links": {
    "self": {
      "href": "/vehicles/7e59591f-c5a3-974e-e452-2951040ae4ee/images/1321961722"
    }
  },
  "_request": {
    "url": "/vehicles/7e59591f-c5a3-974e-e452-2951040ae4ee/images",
    "body": null,
    "method": "POST"
  },
  "_response": {
    "type": "Success",
    "objectId": "1321961722"
  }
}

```

Upload a new vehicle image.

- Using this method only one image can be uploaded at a time.
- Allowed image formats are JPG or PNG.
- Images are attached to the vehicle one after another. Initial image order is therefore dependent on successful upload dates and can be changed later.

The following overview shows how many images can be uploaded/shown per vehicle.

**DE - DEALERS IN GERMANY**

Max. 30 images can be uploaded.

Images will be shown according to selected ad product:

PremiumInserat (T30): max. 30 images

PlusInserat (T20): max. first 20 images

BasicInserat (T10): max. first 15 images

**NL - DEALERS IN THE NETHERLANDS**

Max. 30 images can be uploaded/shown.

**IT - DEALERS IN THE ITALY**

Max. 15 images can be uploaded/shown.

**AT - DEALERS IN AUSTRIA**

Max. 15 images can be uploaded/shown.

**ES - DEALERS IN SPAIN**

Max. 15 images can be uploaded/shown.

**BE - DEALERS IN BELGIUM**

Max. 15 images can be uploaded/shown.

**FR - DEALERS IN FRANCE**

Max. 15 images can be uploaded/shown.


###Headers

|Header Name|Data Type|Mandatory|Description|
|----|----|----|----|
|X-AS24-Version|String|Yes|Defines the API version used to serve the request. Current version number is 1.1|
|Accept-Language|String|No|Language used for returning results, e.g. en-GB.|


### Error Codes

For **error codes** please click <a href="#errors">here</a>.

##Retrieve Vehicle's Images

> ###Endpoint
> `GET` /vehicles/{vehicleId}/images

> ###Request Example
> Retrieve all the images of a vehicle with id = 7e59591f-c5a3-974e-e452-2951040ae4ee:

```shell
curl 'https://api.autoscout24.com/vehicles/7e59591f-c5a3-974e-e452-2951040ae4ee/images' \
     -X GET 
     -H "X-AS24-Version: 1.1" \
     -H "Accept-Language: en-GB" \
     -H "Authorization: Bearer e7c00b24-9f5f-4909-88de-38f8d7ca08bf" \
```

> ###Response Example

```json
{
  "_links": {
    "self": {
      "href": "/vehicles/7e59591f-c5a3-974e-e452-2951040ae4ee/images"
    },
    "images": [
      {
        "href": "http://pic.autoscout24.net/images-big/014/470/0266470014001.jpg?35d21ba78abe"
      }
    ]
  },
  "_request": {
    "url": "/vehicles/7e59591f-c5a3-974e-e452-2951040ae4ee/images",
    "body": null,
    "method": "GET"
  },
  "_response": {
    "type": "Success"
  },
  "_data": {
    "images": [
      {
        "id": "1321961722",
        "href": "http://pic.autoscout24.net/images-big/014/470/0266470014001.jpg?35d21ba78abe",
        "type": "image/jpeg"
      }
    ]
  },
  "_related": []
}
```

Retrieve all existing images of a vehicle.

###Headers

|Header Name|Data Type|Mandatory|Description|
|----|----|----|----|
|X-AS24-Version|String|Yes|Defines the API version used to serve the request. Current version number is 1.1|
|Accept-Language|String|No|Language used for returning results, e.g. en-GB.|

### Error Codes

For **error codes** please click <a href="#errors">here</a>.

##Retrieve an Image

> ###Endpoint
> `GET` /vehicles/{vehicleId}/images/{imageId}

> ###Request Example
> Retrieve the image of id = 1321961722 for the vehicle with id = b78d27e2-671a-47w6-80ab-d3726d7782c7:

```shell
curl https://api.autoscout24.com/vehicles/b78d27e2-671a-47w6-80ab-d3726d7782c7/images/1321961722 \
     -X GET \
     -H "X-AS24-Version: 1.1" \
     -H "Accept-Language: en-GB" \
     -H "Authorization: Bearer 73a06d83-6e13-4444-a288-6aa8c4098c2f" \
```

> ###Response Example

```json
{
  "_links": {
    "self": {
      "href": "/vehicles/b78d27e2-671a-47w6-80ab-d3726d7782c7/images/1321961722"
    }
  },
  "_request": {
    "url": "/vehicles/b78d27e2-671a-47w6-80ab-d3726d7782c7/images/1321961722",
    "body": null,
    "method": "GET"
  },
  "_response": {
    "type": "Success",
    "objectId": "1321961722"
  },
  "_data": {
    "image": {
      "id": "1321961722",
      "href": "http://pic.autoscout24.net/images-big/014/470/0266470014001.jpg?35d21ba78abe",
      "type": "image/jpeg"
    }
  },
  "_related": []
}
```

Retrieve details of an existing vehicle image.

###Parameters

|Parameter Name|Type|Mandatory|Description|
|----|----|----|----|
|vehicleId|URI Parameter|Yes|Unique identifier for a given vehicle.|
|imageId|URI Parameter|Yes|Unique identifier for a given image.|


###Headers

|Header Name|Data Type|Mandatory|Description|
|----|----|----|----|
|X-AS24-Version|String|Yes|Defines the API version used to serve the request. Current version number is 1.1|
|Accept-Language|String|No|Language used for returning results, e.g. en-GB.|

### Error Codes

For **error codes** please click <a href="#errors">here</a>.


## Update an Image

> ###Endpoint
> `PUT` /vehicles/{vehicleId}/images/{imageId}

> ###Request Example
> Update the image with id = 1321961722 of the vehicle with id = b78d27e2-671a-47w6-80ab-d3726d7782c7:

```shell

curl https://api.autoscout24.com/vehicles/b78d27e2-671a-47w6-80ab-d3726d7782c7/images/1321961722 \
     -X PUT \
     -H "X-AS24-Version: 1.1" \
     -H "Accept-Language: en-GB" \
     -H "Content-Type: multipart/form-data; boundary=----WebKitFormBoundary7MA4YWxkTrZu0gW" 
     -H "Authorization: Bearer e7c00b24-9f5f-4909-88de-38f8d7ca08bf" 
     -F "file=@carFoto.jpg"
```

> ###Response Example

```json
{
  "_links": {
    "self": {
      "href": "/vehicles/935e590f-d525-a948-e053-2951040a6584/images/1321961722"
    }
  },
  "_request": {
    "url": "/vehicles/935e590f-d525-a948-e053-2951040a6584/images/1321961722",
    "body": null,
    "method": "PUT"
  },
  "_response": {
    "type": "Success",
    "objectId": "1321961722"
  }
}
```

Update an existing vehicle's image.

###Parameters

|Parameter Name|Type|Mandatory|Description|
|----|----|----|----|
|vehicleID|URI Parameter|Yes|Unique identifier for a given vehicle.|
|imageId|URI Parameter|Yes|Unique identifier for a given image.|


###Headers

|Header Name|Data Type|Mandatory|Description|
|----|----|----|----|
|X-AS24-Version|String|Yes|Defines the API version used to serve the request. Current version number is 1.1|
|Accept-Language|String|No|Language used for returning results, e.g. en-GB.|

### Error Codes

For **error codes** please click <a href="#errors">here</a>.


## Delete a Vehicle

> ###Endpoint
> `DELETE` /vehicles/{vehicleId}/images/{imageId}

> ###Request Example
> Delete the image with id = 1321961722 of the vehicle with ID = b78d27e2-671a-47w6-80ab-d3726d7782c7:

```shell

curl https://api.autoscout24.com/vehicles/b78d27e2-671a-47w6-80ab-d3726d7782c7/images/1321961722 \
     -X DELETE \
     -H "X-AS24-Version: 1.1" \
     -H "Accept-Language: en-GB" \
     -H "Authorization: Bearer e7c00b24-9f5f-4909-88de-38f8d7ca08bf" 
```

> ###Response Example

```json
{
  "_links": {
    "self": {
      "href": null
    }
  },
  "_embedded": {},
  "_request": {
    "url": "/vehicles/b78d27e2-671a-47w6-80ab-d3726d7782c7/images/1321961722",
    "body": null,
    "method": "DELETE"
  },
  "_response": {
    "type": "Success",
    "messages": [
      {
        "code": 10001,
        "messageType": "Info",
        "text": "Image with id 1321961722 was succesfully deleted."
      }
    ]
  }
}
```

Delete an existing vehicle image.

###Parameters

|Parameter Name|Type|Mandatory|Description|
|----|----|----|----|
|vehicleID|URI Parameter|Yes|Unique identifier for a given vehicle.|
|imageId|URI Parameter|Yes|Unique identifier for a given image.|


###Headers

|Header Name|Data Type|Mandatory|Description|
|----|----|----|----|
|X-AS24-Version|String|Yes|Defines the API version used to serve the request. Current version number is 1.1|
|Accept-Language|String|No|Language used for returning results, e.g. en-GB.|

### Error Codes

For **error codes** please click <a href="#errors">here</a>.
