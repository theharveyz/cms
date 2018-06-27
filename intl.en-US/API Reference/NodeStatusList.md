# NodeStatusList {#reference_mzn_kyy_zdb .reference}

## Description {#section_b2r_zdz_zdb .section}

Query the status of the CloudMonitor agent in batches.

## Request Parameters {#section_bbf_12z_zdb .section}

|Name|Type|Required or not|Description|
|:---|:---|:--------------|:----------|
|Action|String|Yes|The API name specified by the system.  Value: NodeStatusList|
|InstanceIds|String|Yes|Instance ID. for example, i-22jja5c2l. Multiple IDs are separated by commas|

## Response parameter {#section_xgr_12z_zdb .section}

|Name|Type|Description|
|:---|:---|:----------|
|Error code|Integer|Error code. The value 200 indicates that request is successful, and a non-200 value indicates request failure|
|ErrorMessage|String|Error message|
|Success|String|Whether the operation is successful, which is equivalent to errorCode200|
|RequestId|String|Unique request ID used to locate error|
|NodeStatusList|NodeStatus Array|List of node status|

**NodeStatus model**

|Name|Type|Description|
|:---|:---|:----------|
|InstanceId|String|Instance ID|
|status|String|See NodeStatus Agent running status|
|autoInstall|Boolean|Whether to enable auto installation using installation APIs|

## Example {#section_lmd_b2z_zdb .section}

**Request example**

```
http://metrics.cn-hangzhou.aliyuncs.com/?Action=NodeStatusList
&InstanceIds= i-abcdefgh123456%2C i-abcdefgh123457
&<Common Request Parameters>
```

**Response example**

-   XML format

    ```
    <NodeStatusListResponse>
      <NodeStatusList>
        <NodeStatus>
          <Status>running</Status>
          <InstanceId> i-abcdefgh123456</InstanceId>
          <AutoInstall>true</AutoInstall>
        </NodeStatus>
        <NodeStatus>
          <Status>uninstalled</Status>
          <InstanceId> i-abcdefgh123457</InstanceId>
          <AutoInstall>true</AutoInstall>
        </NodeStatus>
      </NodeStatusList>
      <Success>true</Success>
      <ErrorCode>200</ErrorCode>
    </NodeStatusListResponse>
    ```

-   JSON format

    ```
    {
        "NodeStatusList": {
            "NodeStatus": [
                {
                    "Status":"running", 
                    "InstanceId": " i-abcdefgh123456", 
                    "AutoInstall": true
                }, 
                {
                    "Status": "uninstalled", 
                    "InstanceId": " i-abcdefgh123457", 
                    "AutoInstall": true
                }
            ]
        }, 
        "ErrorCode": 200, 
        "Success": true
    }
    ```


