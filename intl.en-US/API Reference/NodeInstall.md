# NodeInstall {#reference_mps_mxy_zdb .reference}

## Description {#section_vlf_4xy_zdb .section}

Call APIs to install the CloudMonitor agent on a specified ECS instance. For details, see [Agent introduction](../../../../reseller.en-US/User Guide/Host monitoring/Agent introduction.md#).

**Note:** 

-   Before using the API, make sure that the [Server Guard \(Server Security\)](https://www.alibabacloud.com/help/doc-detail/28451.htm) agent has been installed on your instance. The Server Guard agent is currently integrated into security images. It is installed by default on purchased ECS instances. You can log on to the [Server Guard console](https://partners-intl.console.aliyun.com/#/aqs) to view the running status of each server.
-   The success rate of installing the CloudMonitor agent by using the APIs is about 95%. If installation fails, log on to the instance to install the agent manually. For details, see [Install CloudMonitor agent](../../../../reseller.en-US/User Guide/Host monitoring/Install CloudMonitor agent.md#).

## Request parameters {#section_rxf_qxy_zdb .section}

|Parameter|Type|Required|Description|
|:--------|:---|:-------|:----------|
|Action|String|Yes|Required parameter. Value: NodeInstall.|
|UserId|String|Yes|Alibaba Cloud account ID.|
|InstanceId|String|Yes|Instance ID, for example, i-22jja5c2l.|
|Force|Boolean|No|Whether to install the CloudMonitor agent forcibly. If the agent has been installed, the default value indicates forced installation.|

## Response parameters {#section_qw5_qxy_zdb .section}

|Parameter|Type|Description|
|:--------|:---|:----------|
|Success|Boolean|Indicates whether the request is successful.|
|Error code|Integer|Request failure status code. The value 200 indicates that the request is successful, and a non-200 value indicates that the request fails.|
|RequestId|String|Requested UUID, which is used for log query.|
|ErrorMessage|String|Request failure prompt message.|

## Examples {#section_wfw_zxy_zdb .section}

**Request example**

```
http://metrics.cn-hangzhou.aliyuncs.com/?Action=NodeInstall
&InstanceId= i-abcdefgh123456
&Force=true
&UserId= 1234567898765432
&<Common Request Parameters>
```

**Response example**

-   XML format

    ```
    <NodeInstallResponse>
      <ErrorCode>200</ErrorCode>
      <Success>true</Success>
    </NodeInstallResponse>
    ```

-   JSON format

    ```
    {
        "ErrorCode": 200, 
        "Success": true
    }
    ```


