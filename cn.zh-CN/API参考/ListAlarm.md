# ListAlarm {#reference_fv1_lkv_zdb .reference}

## 描述 {#section_epg_mkv_zdb .section}

查询指定或全部报警规则设置。

## 请求参数 {#section_hnv_mkv_zdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|必选|系统规定参数，取值：ListAlarm|
|Namespace|String|必选|产品名称，参考各产品对应的project,例如 acs\_ecs\_dashboard, acs\_rds\_dashboard等|
|Id|String|可选|报警规则的id|
|Name|String|可选|报警规则名称，支持模糊查询|
|Dimension|String|可选|规则关联的实例信息，为json object对应的字符串，例如\{"instanceId":"name1"\}。可以查询用于查询关联该实例的所有规则，应用该字段时必须指定Namespace|
|State|String|可选|报警规则状态, ALARM, INSUFFICIENT\_DATA，OK|
|IsEnable|Boolean|可选|true为启用，false为禁用|
|PageNumber|Int|可选|页码，默认值：1|
|PageSize|Int|可选|每页记录数，默认值：100|

## 返回参数 {#section_afv_nkv_zdb .section}

|名称|类型|描述|
|:-|:-|:-|
|NextToken|Integer|下一页，为空代表没有下一页|
|AlarmList|List|报警规则详情列表|
|Total|Integer|符合条件数据总数|
|Success|Boolean|请求是否成功|
|RequestId|String|请求的uuid，便于查询日志|
|Code|String|请求失败状态码，200为成功，非200为失败|
|Message|String|请求失败的提示信息|

**Alarm的参数**

|名称|类型|描述|
|:-|:-|:-|
|Id|String|报警规则id|
|Name|String|报警规则名称|
|Namespace|String|报警规则对应的产品|
|MetricName|String|报警规则对应的监控项|
|Dimension|String|报警规则关联的实例列表，为json array对应的字符串，例如\[\{"instanceId":"name1"\},\{"instanceId":"name2"\}\]|
|Period|Int|查询指标的周期，单位秒|
|Statistics|String|统计方法，例如Average、Maximum、Minimum|
|ComparisonOperator|String|比较符|
|Threshold|String|阈值|
|EvaluationCount|Int|连续探测几次都满足阈值条件时报警，默认3次|
|ContactGroups|String|通知的联系组，为json array对应的string，如 \[“联系组1”,”联系组2”\]|
|StartTime|Int|生效时间的开始时间|
|EndTime|Int|生效时间的结束时间|
|SilenceTime|Int|一直处于报警的沉默周期，单位为秒|
|NotifyType|Int|通知类型，值为0是旺旺+邮件，值为1是旺旺+邮件+短信|
|Enable|Boolean|该规则是否启用，true为启动|
|State|String|报警规则的状态，有一个实例报警就是ALARM，所有都没数据是INSUFFICIENT\_DATA，其它情况为OK|

## 示例 {#section_ld3_4kv_zdb .section}

**请求示例**

```
http://metrics.cn-hangzhou.aliyuncs.com/?Action=ListAlarm
&PageSize=2
&Dimension=%7B%22instanceId%22%3A%22 i-abcdefgh123456%22%7D
&Namespace=acs_ecs_dashboard
&PageNumber=1
&<公共请求参数>
```

**返回示例**

-   XML格式

    ```
    <ListAlarmResponse>
      <NextToken>2</NextToken>
      <RequestId>CC2CDD2B-4EA5-43CD-BEE3-758E93C36B7F</RequestId>
      <AlarmList>
        <Alarm>
          <Period>300</Period>
          <Statistics>Average</Statistics>
          <Name>ecs_cpu_total</Name>
          <MetricName>cpu_total</MetricName>
          <State>OK</State>
          <Threshold>90</Threshold>
          <Enable>true</Enable>
          <SilenceTime>86400</SilenceTime>
          <NotifyType>1</NotifyType>
          <Dimensions>["{\"instanceId\":\" i-abcdefgh123456\"}"]</Dimensions>
          <Namespace>acs_ecs_dashboard</Namespace>
          <ContactGroups>["test4nudou"]</ContactGroups>
          <Id>putNewAlarm_group_e8da18b9-bc95-4edf-a8bf-159eb6c8286b</Id>
          <EndTime>24</EndTime>
          <StartTime>0</StartTime>
          <ComparisonOperator>&gt;=</ComparisonOperator>
        </Alarm>
        <Alarm>
          <Period>300</Period>
          <Statistics>Average</Statistics>
          <Name>ecs_diskusage_utilization</Name>
          <MetricName>diskusage_utilization</MetricName>
          <State>OK</State>
          <Threshold>90</Threshold>
          <Enable>true</Enable>
          <SilenceTime>86400</SilenceTime>
          <NotifyType>1</NotifyType>
          <Dimensions>["{\"instanceId\":\" i-abcdefgh123456\"}"]</Dimensions>
          <Namespace>acs_ecs_dashboard</Namespace>
          <ContactGroups>["test4nudou"]</ContactGroups>
          <Id>putNewAlarm_group_3233eba5-0dd4-4e80-a5d5-7399dec3d7cc</Id>
          <EndTime>24</EndTime>
          <StartTime>0</StartTime>
          <ComparisonOperator>&gt;=</ComparisonOperator>
        </Alarm>
      </AlarmList>
      <Success>true</Success>
      <Code>200</Code>
      <Total>27</Total>
    ```

-   JSON格式

    ```
    {
        "NextToken": 2, 
        "RequestId": "EFD27F56-5799-4CE8-B625-56DF3332331C", 
        "AlarmList": {
            "Alarm": [
                {
                    "Period": 300, 
                    "Statistics": "Average", 
                    "Name": "ecs_cpu_total", 
                    "MetricName": "cpu_total", 
                    "State": "OK", 
                    "Threshold": "90", 
                    "Enable": true, 
                    "SilenceTime": 86400, 
                    "NotifyType": 1, 
                    "Dimensions": "[\"{\\\"instanceId\\\":\\\" i-abcdefgh123456\\\"}\"]", 
                    "Namespace": "acs_ecs_dashboard", 
                    "ContactGroups": "[\"test4nudou\"]", 
                    "Id": "putNewAlarm_group_e8da18b9-bc95-4edf-a8bf-159eb6c8286b", 
                    "EndTime": 24, 
                    "StartTime": 0, 
                    "ComparisonOperator": ">="
                }, 
                {
                    "Period": 300, 
                    "Statistics": "Average", 
                    "Name": "ecs_diskusage_utilization", 
                    "MetricName": "diskusage_utilization", 
                    "State": "OK", 
                    "Threshold": "90", 
                    "Enable": true, 
                    "SilenceTime": 86400, 
                    "NotifyType": 1, 
                    "Dimensions": "[\"{\\\"instanceId\\\":\\\" i-abcdefgh123456\\\"}\"]", 
                    "Namespace": "acs_ecs_dashboard", 
                    "ContactGroups": "[\"test4nudou\"]", 
                    "Id": "putNewAlarm_group_3233eba5-0dd4-4e80-a5d5-7399dec3d7cc", 
                    "EndTime": 24, 
                    "StartTime": 0, 
                    "ComparisonOperator": ">="
                }
            ]
        }, 
        "Success": true, 
        "Code": "200", 
        "Total": 27
    }
    ```


