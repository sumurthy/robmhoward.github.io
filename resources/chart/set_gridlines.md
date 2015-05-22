# Set Chart Gridlines

Use PATCH method on the relevant ChartGridlines object to get position and related format.

##  Set Chart Gridlines

This API allows stting of postion and format of ChartGridlines.

##### HTTP Request
```
PATCH /Charts('<arg>')/axes/valueaxis/majorgridlines

```

##### Request Parameters
Parameter       | Type | Description
--------------- | ------ | ------------
 `arg`| Chart identifier | Required. Refer to `Get Chart` API for valid formats.
 

##### Optional Request Headers
None

##### Request Body

In the request body, provide a JSON object that represents the Font.

| Property         | Type    |Description| 
|:-----------------|:--------|:----------|
|visible| Boolean | True if the axis has gridlines. |

##### Example 


This example sets the display position of the chart legend.

<!-- { "blockType": "request", "name": "set-chart-gridlines" } -->
```http
PATCH /Charts('<arg>')/valueaxis/majorgridlines
Content-Type: application/json
Content-Length: <length>

{
  "visible": false
}
```

##### Response

If successful, this method returns the [ChartGridlines](../../resources/chartGridlines.md) object with updated values.

<!-- { "blockType": "response", "@odata.type": "ChartGridlines" } -->
```http
HTTP/1.1 200 OK
Content-Type: application/json
Content-length: <length>

{
  "visible": false
}
```


##### Error Response

Read the [Error Responses][error-response] topic for more information about how errors are returned.
[error-response]: ../../misc/errors.md

 HTTP Code | HTTP Error Message | Error Code           | Error Message
:----------|:-------------------|:---------------------|:---------------------------------------------------------
 400       | Bad Request        | InvalidArgument      |The argument is invalid or missing or has an incorrect format. 
 400       | Bad Request        | InvalidRequest       | Cannot process the request.
 403       | Forbidden          | AccessDenied         | You cannot perform the requested operation.
 404       | Not Found          | ItemNotFound         | The requested resource doesn't exist.
 405       | Method Not Allowed | InvalidMethod        | The method in the request is not allowed on the resource. 
 409       | Conflict           | EditConflict         | Request could not be processed because of conflict.
 411       | Length Required    | ContentLengthRequired| A Content-Length header is required.
 429       |Too Many Requests        |ActivityLimitReached|Activity limit has been reached.
 500       | Internal Server Error|GeneralException    | There was an internal error while processing the request.
 503       | Service Unavailable| ServiceNotAvailable  | The service is unavailable.