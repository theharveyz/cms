# CreateAlarm {#reference_x3v_shv_zdb .reference}

## 描述 {#section_fy4_33v_zdb .section}

创建报警规则，可以为某一个实例创建报警规则，也可以为多个实例同时创建报警规则。

## 请求参数 {#section_ljd_k3v_zdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是|系统规定参数，取值：CreateAlarm|
|Name|String|必选|报警规则名称|
|Namespace|String|必选|产品名称，参考各产品对应的project,例如acs\_ecs\_dashboard, acs\_rds\_dashboard等|
|MetricName|String|必选|相应产品对应的监控项名称，参考各产品metric定义|
|Dimensions|String|必选|报警规则对应实例列表，为json array对应的string，例如\[\{“instanceId”:”name1”\},\{“iinstance”:”name2”\}\]|
|Period|Integer|可选|查询指标的周期，必须与定义的metric一致，默认300，单位为秒|
|Statistics|String|必选|统计方法，必须与定义的metric一致，例如Average|
|ComparisonOperator|String|必选|报警比较符，只能为以下几种<=,<,\>,\>=,==,!=|
|Threshold|String|必选|报警阈值，目前只开放数值类型功能|
|EvaluationCount|Int|可选|连续探测几次都满足阈值条件时报警，默认3次|
|ContactGroups|String|必选|报警规则通知的联系组，必须在控制台上已创建，为json array对应的string，例如 \[“联系组1”,”联系组2”\]|
|StartTime|Int|可选|报警生效时间的开始时间，默认0，代表0点|
|EndTime|Int|可选|报警生效时间的结束时间，默认24，代表24点|
|SilenceTime|Int|可选|一直处于报警状态的通知沉默周期，默认86400，单位s，最小1小时|
|NotifyType|Int|可选|通知类型，为0是旺旺+邮件，为1是旺旺+邮件+短信|

## 返回参数 {#section_nr5_l3v_zdb .section}

|名称|类型|描述|
|:-|:-|:-|
|Data|String|返回的报警规则id|
|Success|Boolean|请求是否成功|
|RequestId|String|请求的uuid，便于查询日志|
|Code|String|请求失败状态码，200为成功，非200为失败|
|Message|String|请求失败的提示信息|

## 示例 {#section_vrl_s3v_zdb .section}

**请求示例**

```
http://metrics.cn-hangzhou.aliyuncs.com/
POST请求体数据内容：
Name: test_alarm
Namespace: acs_ecs_dashboard
MetricName: vm.MemoryUtilization
Dimensions：[{"instanceId":"<your_ instanceId >","userId":"<your_ userId >"}]
Period：900
Statistics：Average
ComparisonOperator：<=
Threshold：35
EvaluationCount：2
ContactGroups：["testgroup"]
StartTime：6
EndTime：20
NotifyType：1
```

**返回示例**

-   XML格式

    ```
    <CreateAlarmResponse>
      <Data>576fbae7-2fd1-411a-ae13-6f09f4fafdde</Data>
      <RequestId>58C699ED-84BE-44D5-B55F-84AFE73932AB</RequestId>
      <Success>true</Success>
      <Code>200</Code>
    </CreateAlarmResponse>
    ```

-   JSON格式

    ```
    {
        "Data": "0c4af0f1-a864-468b-bed3-15c7deff75ee", 
        "RequestId": "910ABE4E-DC9D-4231-9DC0-C96835553327", 
        "Success": true, 
        "Code": "200"
    }
    ```


