# Change Log

This section documents all the changes on the AutoScout24 RESTful API. This includes documentation for the new features, changes to old features, and deprecated features. 

<aside> <b>Version 1.1 is the most recent version of the AutoScout24 RESTful API</b>. This version was introduce on December 14th, 2015. For more information about AutoScout24's API evolution strategy, please refer to the <a href="#api-evolution">API Evolution section</a>.</aside>

##Versions

| Version | Release Date | Shutdown Date |
|----|----|----|
|1.1|08.02.2016| - |
|1.0|01.04.2015|08.08.2016 |

##December 14th, 2015 - API version 1.1

###New Features

#### - Bikes: 
Dealers can now insert not only cars, but they can also insert bikes via the `/vehicles` endpoint. 

#### - Financing Offers: 
A new Financing Offers sub-resource `/vehicles/{vehicleId}/financingoffers` was added to the Vehicles resource. This would enable dealers to offer their customers the opportunity to get a financing offer when buying the vehicle. A dealer can now create, update, retrieve, and delete one financing offer for each vehicle.

#### - Detail Page URI:
The link to the detail page is now returned when published a vehicle on a specific channel. In addition, the Channel's respective detail page URI is returned when requesting information about the publication channels. For more information, please check the <a href="#resource-publications">/publications resource</a>.

#### - Version Header: 
A new HTTP header `X-AS24-Version` was introduced to explicitly define which version the consumer application is trying to communicate with.
 
###Changes On v1.0

#### - New Response Structure: 
A new data structure is introduced that unifies how the API responses look like. This new data structure would enable the consumers of the API to handle all the responses of the API in the same way. In addition, Hypermedia is used to represent the relationship to other resources. The new data structure will replace the old data structure that was used in v1.0. 

#### - New data types for the Reference Object's fields:
`vehicleType` and `country` fields of the <a href="#referenceObject">Reference</a> object have been changed in version 1.1 to be of type array.

#### - New data type for the Make Object's fields:
`vehicleType` field of the <a href="#makeObject2">Make</a> object has been changed in version 1.1 to be of type array.


