# NodeStatus {#reference_zpd_h2v_zdb .reference}

## Description {#section_hjn_p2v_zdb .section}

Query the agent running status on a specified instance.

## Request parameters {#section_o2g_q2v_zdb .section}

|Name|Type|Required or not|Description|
|:---|:---|:--------------|:----------|
|Action|String|Yes|API name specified by the system.  Value: NodeStatus.|
|InstanceId|String|Yes|Instance id, for example: i-22jja5c2l.|

## Response parameter {#section_nnc_r2v_zdb .section}

|Name|Type|Description|
|:---|:---|:----------|
|Error code|Integer|Error code. The value 200 indicates that the request is successful, and a non-200 value indicates request failure|
|ErrorMessage|String|Error message|
|Success|String|Whether the operation is successful, which is equivalent to errorCode200.|
|RequestId|String|Unique request ID used for error locating.|
|InstanceId|String|Instance id|
|Status|String|Agent running status|
|AutoInstall|Boolean|Whether to enable automatic installation using NodeInstall|

**Agent running status**

|Name|Description|
|:---|:----------|
|running|Running|
|Stopped|Stopped|
|not\_installed|Uninstalled|
|installing|Installing|
|Install\_faild|Installation failed|
|need\_to\_upgrade|Upgrade required|
|uninstalled|Already uninstalled|

## Example {#section_nw3_s2v_zdb .section}

**Request example**

```
http://metrics.cn-hangzhou.aliyuncs.com/?Action=NodeStatus
&InstanceId= i-abcdefgh123456
&<Common Request Parameters>
```

**Response example**

-   XML format
-   ```
<NodeStatusResponse>
  <Status>running</Status>
  <InstanceId> i-abcdefgh123456</InstanceId>
  <ErrorCode>200</ErrorCode>
  <Success>true</Success>
  <AutoInstall>true</AutoInstall>
</NodeStatusResponse>
```


-   JSON format
-   ```
{
    "Status":"running", 
    "InstanceId": " i-abcdefgh123456", 
    "Success": true, 
    "ErrorCode": 200, 
    "AutoInstall": true
}
```


