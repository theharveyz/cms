# DisableAlarm {#reference_ydz_ylv_zdb .reference}

## 描述 {#section_chk_bmv_zdb .section}

禁用报警规则。报警规则停止后，将停止探测关联实例的监控项数据。

## 请求参数 {#section_n3v_bmv_zdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是|系统规定参数，取值：DisableAlarm|
|Id|String|必选|报警规则的id|

## 返回参数 {#section_y3h_cmv_zdb .section}

|名称|类型|描述|
|:-|:-|:-|
|Success|Boolean|请求是否成功|
|RequestId|String|请求的uuid，便于查询日志|
|Code|String|请求失败状态码，200为成功，非200为失败|
|Message|String|请求失败的提示信息|

## 示例 {#section_ivw_cmv_zdb .section}

**请求示例**

```
http://metrics.cn-hangzhou.aliyuncs.com/?Action=DisableAlarm
&Id=576fbae7-2fd1-411a-ae13-6f09f4fafdde
&<公共请求参数>提示信息
```

**返回示例**

-   XML格式

    ```
    <DisableAlarmResponse>
      <RequestId>CF9F20A2-D4CF-4FA0-B8A3-1F4C151B3C91</RequestId>
      <Success>true</Success>
      <Code>200</Code>
    </DisableAlarmResponse>
    ```

-   JSON格式

    ```
    {
        "RequestId": "DEF01F10-E747-42FE-9152-85CB43B1B552", 
        "Success": true, 
        "Code": "200"
    }
    ```


