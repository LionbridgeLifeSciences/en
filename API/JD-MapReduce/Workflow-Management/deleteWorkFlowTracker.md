# deleteWorkFlowTracker


## Description
Delete the operation record corresponding to the specified workflow

## Request method
POST

## Request address
https://idata-jmr-api.jcloud.com/v1/regions/{regionId}/tracker/{trackerId}:delete

|Name|Type|Required or not|Default value|Description|
|---|---|---|---|---|
|**regionId**|String|True||Region ID|
|**trackerId**|String|True|||

## Request parameter
|Name|Type|Required or not|Default value|Description|
|---|---|---|---|---|


## Return parameter
|Name|Type|Description|
|---|---|---|
|**requestId**|String||
|**result**|[Result](##Result)||


### <a name="Result">Result</a>
|Name|Type|Description|
|---|---|---|
|**message**|String||
|**status**|String||

## Return code
|Return code|Description|
|---|---|
|**200**|OK|
|**500**|Internal server error|
