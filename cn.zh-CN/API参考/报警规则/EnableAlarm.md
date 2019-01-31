# EnableAlarm {#reference_a4d_bgy_zdb .reference}

## 描述 {#section_exq_bgy_zdb .section}

启动报警规则，当您的报警规则处于停止状态时，可以使用此接口启用报警规则。

## 请求参数 {#section_ym2_cgy_zdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是|系统规定参数，取值：EnableAlarm|
|Id|String|必选|报警规则的id|

## 返回参数 {#section_el4_cgy_zdb .section}

|名称|类型|描述|
|:-|:-|:-|
|Data|String|返回的报警规则id|
|Success|Boolean|请求是否成功|
|RequestId|String|请求的uuid，便于查询日志|
|Code|String|请求失败状态码，200为成功，非200为失败|

## 示例 {#section_jnd_4wy_zdb .section}

**请求示例**

```
http://metrics.cn-hangzhou.aliyuncs.com/?Action= EnableAlarm
&Id=576fbae7-2fd1-411a-ae13-6f09f4fafdde
&<公共请求参数>
```

**返回示例**

-   XML格式

    ```
    <EnableAlarmResponse>
      <RequestId>1B77FA9C-4E5A-4DF9-82CB-0E898C9FDA2F</RequestId>
      <Success>true</Success>
      <Code>200</Code>
    </EnableAlarmResponse>
    ```

-   JSON格式

    ```
    {
        "RequestId": "1C5E0E5D-76D5-469C-9FA8-D74799B24860", 
        "Success": true, 
        "Code": "200"
    }
    ```


