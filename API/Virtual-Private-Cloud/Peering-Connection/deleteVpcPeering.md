# deleteVpcPeering


## Description
Delete VpcPeering interface

## Request method
DELETE

## Request address
https://vpc.jdcloud-api.com/v1/regions/{regionId}/vpcPeerings/{vpcPeeringId}

|Name|Type|Required or not|Default value|Description|
|---|---|---|---|---|
|**regionId**|String|True||Region ID|
|**vpcPeeringId**|String|True||vpcPeeringId ID|

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
