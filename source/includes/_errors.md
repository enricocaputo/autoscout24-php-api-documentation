# Errors

##Responses

Responses as well as messages are classified by their type:

|Type|MessageType|Description|Response Code Range|
|----|----|----|----|
|Success|None|A request has been processed exactly as requested|None|
|Success|Info|A request has been processed exactly as requested, however the response contains information for the client|10000 - 19999|
|Success|Warning|A request has been processed, but not excatly as requested (e.g. some inconsistencies were found and removed)|20000 - 49999|
|Error|Error|A request was not processed|50000 - 99999|


##Error Codes

|Code|Text|
|----|----|
|10000|Vehicle with id {0} was succesfully deleted.|
|10001|Image with id {0} was succesfully deleted.|
|10003|Product with id {0} was succesfully deleted.|
|10500|Vehicle URI on PublicationChannel {channelId} is: { URI }. Please note that it might take a couple of minutes before the URI becomes available.|
|20001|Field particleFilter does not correspond with selected field fuelCategory. A particle filter is only available for diesel vehicles.|
|20500|'Accept-Language' is empty or not supported. Default Culture 'en-GB' is used.|
|50000|An error occurred while processing your request. Please try again later.|
|50001|Mandatory object {field} is missing. Please provide missing object.|
|50002|Field countryVersion has an unknown value. Please provide correct value from /references.|
|50003|Field deliveryDate doesn't match expected date format (YYYY-MM-DD). Please provide expected date format.|
|50004|Field {field} is mandatory. Please provide missing field.|
|50005|Field seals has an unknown value. Please provide correct value from /seals.|
|50006|Field {field} doesn't match expected date format (YYYY-MM). Please provide expected date format.|
|50007|Object price is missing. Please provide missing object.|
|50008|Field currency is missing. Please provide missing field.|
|50009|Field price must be greater than zero.|
|50010|Field vehicleType is missing. Please provide missing field.|
|50012|Field negotiable is missing. Please provide missing field.|
|50013|Field taxDeductible is missing. Please provide missing field.|
|50014|Field availabilityType must have a value from the following list: {allowedValues}.|
|50015|Please don't provide neither deliverydate nor deliverdays for availabilityType 1 ( = Immediately).|
|50016|Field deliveryDays must have a value from the following list: {allowedvalues}.|
|50017|Field currency has an invalid value. Please use EUR.|
|50018|Field priceTypes must have a value from the following list: {allowedValues}.|
|50019|Field hsn has an invalid value. Please use numeric values only.|
|50022|Wrong image format: '{filename}'. Please upload JPG or PNG images only.|
|50023|Please provide deliveryDate for availabilityType 2.|
|50024|Please provide deliveryDays for availabilityType 3.|
|50025|Please just provide deliveryDate for availabilityType 2.|
|50026|Please just provide deliveryDays for availabilityType 3.|
|50027|Field {field} doesn't match expected format (between 0 and 99.9). Please provide expected format.|
|50028|Invalid json - {json}. Please provide a valid json.|
|50029|Field vehicleType has an invalid value. Please use C.|
|50030|Field model does not correspond to field make.|
|50031|Field firstRegistration is mandatory. Please provide missing field.|
|50032|Field firstRegistration must not be older than 24 months.|
|50033|Field firstRegistration must not be older than 12 months.|
|50034|Field firstRegistration must be older than 360 months.|
|50035|Field tsn is missing. Please provide a complete combination of hsn/tsn or none.|
|50036|Field hsn is missing. Please provide a complete combination of hsn/tsn or none.|
|50037|Field mileage must be lower or equal to 1000.|
|50038|Field previousOwners is not allowed for vehicleOfferType = N.|
|50040|Field make has an invalid value. Please provide supported make. |
|50041|Field model has an invalid value. Please provide supported model. |
|50043|Field lastCamBeltService must be in the past. |
|50044|Field lastTechnicalService must be in the past.|
|50045|Field nextInspection must be in the future.|
|50046|Field previousOwner must not have more than 1 previous owner for vehicleOfferType = S.|
|50047|Field previousOwner must  have at least 1 previous owner for vehicleOfferType = D.|
|50048|Field deliveryDate must be in the future.|
|50049|Please provide deliveryDays for availabilityType 3.|
|50050|Field {fieldname} must not contain email addresses.|
|50051|Field {fieldname} must not contain URLs.|
|50052|Field {fieldname} must not contain prohibited characters < or >.|
|50053|Field equipment has an unknown value. Please provide correct value from /references.|
|50054|It's not allowed to have two price objects with the same priceType.|
|50055|Please provide price object with priceType = Public.|
|50058|Field co2 is mandatory for vehicleOfferType N, D, S. Please provide missing field.|
|50059|Field electricConsumptionCombined is mandatory for primaryFuelType = Electricity and vehicleOfferType N, D, S. Please provide missing field.|
|50060|Field fuelConsumption combined is mandatory for vehicleOfferType 'N', 'D', 'S' and primaryFuelType other than Electricity. Please provide missing field.|
|50061|Field efficiencyClass is mandatory for vehicleOfferType N, D, S. Please provide missing field.|
|50062|Field primaryFuelType is mandatory for vehicleOfferType N, D, S. Please provide missing field.|
|50063|Public price must be higher than dealer price.|
|50064|Availability delivery date cannot be provided along with delivery days.|
|50066|Field {field} must be in range {from}-{to}.|
|50067|Field {field} must not be longer than {to} characters.|
|50068|Field {field} must be greater than {from}.|
|50069|Field fullServiceHistory is missing. Please provide missing field.|
|50071|List of values in the field {field} has duplicates. Please remove the duplicate values.|
|50072|Field {field} must have exact length of {length} characters.|
|50073|Field {field} must have a value from the following list: {allowedValues}.|
|50074|You have no permission to change publications for the vehicle {vehicleId}.|
|50075|Publication channel name must have a value from the following list: AS24, AS24Dealers.|
|50076|ChannelDispatcher: List of publication channels is empty for the vehicle {vehicleId}. There is nothing to change.|
|50077|This account is not allowed to use this channel.|
|50080|Image does not exist.|
|50081|List of image ids should contain the same ids returned by the GET method.|
|50082|The body of the POST request contains no image data.|
|50083|Image size exceedes limit.|
|50084|Image number limit exceeded.|
|50085|Multiple image upload is not allowed. Please post one picture per request.|
|50086|You're not allowed to perform actions on this image.|
|50087|Header contains wrong customerId value. Please provide correct customerId.|
|50088|You're not allowed to book products.|
|50089|You're not allowed to book products for this vehicle.|
|50090|Wrong booking rule for this customer - Product booking via interface is not possible as customer profile is set to automatic booking rule.|
|50091|Provided product is not assigned to this vehicle. Therefore, it can not be deleted.|
|50092|A product booking for this vehicle already exists. Please remove existing booking first.|
|50093|Not all header values are set. Please provide necessary header values.|
|50094|You're not allowed to perform this action.|
|50095|Field Subtitle must not contain < , >, urls or emails.|
|50096|You don't have the subscriptions to book products.|
|50097|Product booking has an unknown value. Please provide correct value from /references.|
|50098|Provided product booking does not match subscription type. Please provide correct value from /references.|
|50099|Provided product has an unknown value. Please provide correct value from /references.|
|50100|A contact for this vehicle already exists. Per vehicle only one set of contact details is allowed.|
|50101|A contact for this vehicle does not exist.|
|50102|It's not allowed to have two phone number objects with the same phoneNumberType.|
|50103|Invalid json. Please provide a valid json.|
|50104|A contact for this vehicle does not exist. This vehicle can not be published without contact.|
|50105|You are not allowed to publish this vehicle on this channel.|
|50106|Field seals has an invalid value. Please provide supported seals.|
|50107|Only german dealers are allowed to add financing offers.|
|99901|Forbidden - You're not allowed to execute this action.|
|99902|Invalid request - Missing access token.|
|99903|Invalid request - Duplicate access token.|
|99904|Invalid request - Invalid access token.|
|99905|Invalid request - Validation error.|
