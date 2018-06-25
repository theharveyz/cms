# NodeStatusList {#reference_mzn_kyy_zdb .reference}

## 描述 {#section_b2r_zdz_zdb .section}

批量查询云监控插件状态。

## 请求参数 {#section_bbf_12z_zdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是|操作接口名，系统规定参数。取值：NodeStatusList|
|InstanceIds|String|是|实例id。 例如：i-22jja5c2l，多个id使用英文逗号分隔|

## 返回参数 {#section_xgr_12z_zdb .section}

|名称|类型|描述|
|:-|:-|:-|
|ErrorCode|Integer|错误码，200为成功，其他为失败|
|ErrorMessage|String|错误提示|
|Success|String|本次操是否成功,等价与errorCode200|
|RequestId|String|请求的唯一ID用于定位错误|
|NodeStatusList|NodeStatus Array|Node状态的列表|

**NodeStatus模型**

|名称|类型|描述|
|:-|:-|:-|
|instanceId|String|实例id|
|status|String|参考NodeStatus Agent运行状态|
|autoInstall|Boolean|是否可以使用安装接口自动安装|

## 示例 {#section_lmd_b2z_zdb .section}

**请求示例**

```
http://metrics.cn-hangzhou.aliyuncs.com/?Action=NodeStatusList
&InstanceIds= i-abcdefgh123456%2C i-abcdefgh123457
&<公共请求参数>
```

**返回示例**

-   XML格式

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

-   JSON格式

    ```
    {
        "NodeStatusList": {
            "NodeStatus": [
                {
                    "Status": "running", 
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


