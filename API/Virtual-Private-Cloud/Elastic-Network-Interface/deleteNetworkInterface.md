# deleteNetworkInterface


## Description
Delete elastic network interface APIs

## Request method
DELETE

## Request address
https://vpc.jdcloud-api.com/v1/regions/{regionId}/networkInterfaces/{networkInterfaceId}

|Name|Type|Required or not|Default value|Description|
|---|---|---|---|---|
|**networkInterfaceId**|String|True||networkInterface ID|
|**regionId**|String|True||Region ID|

## Request parameter
无


## Return parameter
|Name|Type|Description|
|---|---|---|
|**requestId**|String|Request ID|



## Return code
|Return code|Description|
|---|---|
|**200**|OK|
|**404**|NOT_FOUND|
