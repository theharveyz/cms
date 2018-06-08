# UpdateAlarm {#reference_j3t_2gz_zdb .reference}

## 描述 {#section_qrc_kgz_zdb .section}

修改已创建的报警规则。

## 请求参数 {#section_snm_kgz_zdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|必选|系统规定参数，取值：UpdateAlarm|
|Id|String|必选|报警规则的id|
|Name|String|可选|报警规则名称|
|Period|Integer|可选|查询指标的周期，必须与定义的metric一致，默认300，单位为秒|
|Statistics|String|可选|修改后的值|
|ComparisonOperator|String|必选|报警比较符，只能为以下几种<=,<,\>,\>=,==,!=|
|Threshold|String|必选|报警阈值，目前只开放数值类型功能|
|EvaluationCount|Int|可选|连续探测几次都满足阈值条件时报警，默认3次|
|ContactGroups|String|必选|报警规则通知的联系组，必须在控制台上已创建，为json array对应的string，例如 \[“联系组1”,”联系组2”\]|
|StartTime|Int|可选|报警生效时间的开始时间，默认0，代表0点|
|EndTime|Int|可选|报警生效时间的结束时间，默认24，代表24点|
|SilenceTime|Int|可选|一直处于报警状态的通知沉默周期，默认86400，单位s，最小1小时|
|NotifyType|Int|可选|通知类型，为0是旺旺+邮件，为1是旺旺+邮件+短信|

## 返回参数 {#section_o51_lgz_zdb .section}

|名称|类型|描述|
|:-|:-|:-|
|Success|Boolean|请求是否成功|
|RequestId|String|请求的uuid，便于查询日志|
|Code|String|状态码|
|Message|String|请求失败的提示信息|

## 示例 {#section_bml_lgz_zdb .section}

**请求示例**

```
http://metrics.cn-hangzhou.aliyuncs.com/?Action=UpdateAlarm
&ComparisonOperator=%3E
&Name=test_modify
&Id=576fbae7-2fd1-411a-ae13-6f09f4fafdde
&Threshold=40
&<公共请求参数>
```

**返回示例**

-   XML格式

    ```
    <UpdateAlarmResponse>
      <RequestId>C08FADC4-CFDB-42F7-B9B8-0ED5391CD084</RequestId>
      <Success>true</Success>
      <Code>200</Code>
    </UpdateAlarmResponse>
    ```

-   JSON格式

    ```
    {
        "RequestId": "945B9183-95C0-44FF-B30C-9ED37D44F6DC", 
        "Success": true, 
        "Code": "200"
    }
    ```


