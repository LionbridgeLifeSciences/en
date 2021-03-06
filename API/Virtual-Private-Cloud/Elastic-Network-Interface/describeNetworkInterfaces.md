# describeNetworkInterfaces


## Description
Query elastic network interface list

## Request method
GET

## Request address
https://vpc.jdcloud-api.com/v1/regions/{regionId}/networkInterfaces/

|Name|Type|Required or not|Default value|Description|
|---|---|---|---|---|
|**regionId**|String|True||Region ID|

## Request parameter
|Name|Type|Required or not|Default value|Description|
|---|---|---|---|---|
|**filters**|[Filter[]](##Filter)|False||networkInterfaceIds - Elastic network interface ID list, support multiple IDs<br>networkInterfaceNames - Elastic network interface name list, support multiple names<br>vpcId - vpc Id of elastic network interface, support single Ids<br>subnetId	- Subnet Id of elastic network interface, support single Ids<br>role - Network interface role, value range: Primary (primary network interface), Secondary (secondary network interface), support single role<br>|
|**pageNumber**|Integer|False|1|Page, 1 by default, value range: [1,∞); when the pages exceed total pages, show the last page|
|**pageSize**|Integer|False|20|Paging size, 20 by default; value range: [10,100]|

### <a name="Filter">Filter</a>
|Name|Type|Required or not|Default value|Description|
|---|---|---|---|---|
|**name**|String|True||Name of filter requirements|
|**operator**|String|False||Operator of filter requirements is eq by default|
|**values**|String[]|True||Value of filter requirements|

## Return parameter
|Name|Type|Description|
|---|---|---|
|**requestId**|String|Request ID|
|**result**|[Result](##Result)|Return result|


### <a name="Result">Result</a>
|Name|Type|Description|
|---|---|---|
|**networkInterfaces**|[NetworkInterface[]](##NetworkInterface)|networkInterface resource information list|
|**totalCount**|Number|Total amount|
### <a name="NetworkInterface">NetworkInterface</a>
|Name|Type|Description|
|---|---|---|
|**az**|String|Availability zone name|
|**createdTime**|String|Creation time of elastic network interface|
|**description**|String|Network interface description information|
|**deviceIndex**|Integer|Device reference number of network interface on the instance, value range: [0,8], 0: secondary network interface doesn't associate device, 1: primary network interface, 2-8: secondary network interface has associated device|
|**instanceId**|String|Associated instance ID|
|**instanceOwnerId**|String|Account of instance|
|**instanceType**|String|Associated instance type family, value range: vm|
|**macAddress**|String|Ethernet address|
|**networkInterfaceId**|String|Elastic network interface ID|
|**networkInterfaceName**|String|Elastic network interface name|
|**networkSecurityGroupIds**|String[]|Security group ID list|
|**primaryIp**|[NetworkInterfacePrivateIp](##NetworkInterfacePrivateIp)|Network interface primary IP|
|**role**|String|Network interface role, value range: Primary (primary network interface), Secondary (secondary network interface)|
|**sanityCheck**|Integer|Source and target IP address verification, with value 0 or 1|
|**secondaryIps**|[NetworkInterfacePrivateIp[]](##NetworkInterfacePrivateIp)|Network interface auxiliary IP list|
|**subnetId**|String|Subnet ID|
|**vpcId**|String|Virtual network ID|
### <a name="NetworkInterfacePrivateIp">NetworkInterfacePrivateIp</a>
|Name|Type|Description|
|---|---|---|
|**elasticIpAddress**|String|Elastic IP instance address|
|**elasticIpId**|String|Elastic IP instance ID|
|**privateIpAddress**|String|IPV4 address of private IP|

## Return code
|Return code|Description|
|---|---|
|**200**|OK|
|**400**|invalid parameter|
|**401**|Authentication failed|
