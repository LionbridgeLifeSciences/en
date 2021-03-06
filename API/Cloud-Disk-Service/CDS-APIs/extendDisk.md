# extendDisk


## Description
-   Expansion of the cloud disk service requires it in available status.
-   Capacity expansion is not allowed while the disk is creating a snapshot.


## Request method
POST

## Request address
https://disk.jdcloud-api.com/v1/regions/{regionId}/disks/{diskId}:extend

|Name|Type|Required or not|Default value|Description|
|---|---|---|---|---|
|**diskId**|String|True||Cloud Disk Service ID|
|**regionId**|String|True||Region ID|

## Request parameter
|Name|Type|Required or not|Default value|Description|
|---|---|---|---|---|
|**diskSizeGB**|Integer|True||The size of the cloud disk service after expansion is in GiB|


## Return parameter
|Name|Type|Description|
|---|---|---|



## Return code
|Return code|Description|
|---|---|
|**400**|Invalid parameter|
|**401**|Authentication failed|
|**404**|Not found|
|**503**|Service unavailable|
|**200**|OK|
|**500**|Internal server error|
