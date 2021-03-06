# putMetricData


## Description
The interface is the interface for customized metric monitoring data reporting, which is convenient for you to report the time series data collected by yourself to the Cloud Monitor. It can report original data and aggregated statistical data. It supports reporting methods in batches. A single request contains up to 50 data points; the data size does not exceed 256k.

## Request method
POST

## Request address
https://monitor.{regionId}.jdcloud-api.com/v1/customMetrics

|Name|Type|Required or not|Default value|Description|
|---|---|---|---|---|

## Request parameter
|Name|Type|Required or not|Default value|Description|
|---|---|---|---|---|
|**metricDataList**|[MetricDataCm[]](##MetricDataCm)|False||Data parameter|

### <a name="MetricDataCm">MetricDataCm</a>
|Name|Type|Required or not|Default value|Description|
|---|---|---|---|---|
|**dimensions**|Object|True||Data dimension, data type is map type, support at least one, up to five tags, no more than 255 bytes in total length, only English, numbers, underlines_, dot., [0-9][a-z] [A-Z] [. _ ] are allowed, others will return err|
|**metric**|String|True||Monitoring indicator name, no more than 255 bytes in length, only English, numbers, underlines_, dot., [0-9][a-z] [A-Z] [. _ ] are allowed, others will return err|
|**namespace**|String|True||Naming space, no more than 255 bytes in length, only English, numbers, underlines_, dot., [0-9][a-z] [A-Z] [. _ ] are allowed, others will return err|
|**timestamp**|Integer|True||Time stamp for reporting data points only supports 10-bit, second-level time stamp, the time of the past 30 days cannot be written in|
|**type**|Integer|True||Data reporting type, 1 is the original value, 2 is aggregated data. When the aggregated data is reported, it is suggested that it shall be reported during the period of 60s, otherwise, it cannot be queried normally.|
|**values**|Object|True||Indicator value collection, the data type must be the map type, key is the data type, value is the data value, when type=1, key only can be “value”, the reported is the original value, when type=2, key can be "avg”, "sum”, "last”, "max”, "min”, “count”, which only support the above types, otherwise it will report an error, value contents are integers or floating point numbers, the largest value is 9223372036854775807, count only supports numbers >=0|

## Return parameter
|Name|Type|Description|
|---|---|---|
|**error**|Object|Error information|
|**requestId**|String|Requested identifier id|
|**result**|[Result](##Result)||


### <a name="Result">Result</a>
|Name|Type|Description|
|---|---|---|
|**errMetricDataList**|[MetricDataList[]](##MetricDataList)||
|**success**|Boolean|All successful write-ins are true, or false|
### <a name="MetricDataList">MetricDataList</a>
|Name|Type|Description|
|---|---|---|
|**errDetail**|String|Error data description|
|**errMetricData**|String|Error data|

## Return code
|Return code|Description|
|---|---|
|**200**|OK|
|**400**|invalid parameter|
|**500**|internal server error|
|**429**|quota exceed|
