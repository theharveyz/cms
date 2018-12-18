# ListAlarmHistory {#reference_zpd_h2v_zdb .reference}

## 描述 {#section_hjn_p2v_zdb .section}

查询报警历史。

## 请求参数 {#section_o2g_q2v_zdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是|系统规定参数，取值：ListAlarmHistory。|
|Id|String|可选|报警规则的id。|
|Size|Int|可选|每页记录数，默认值：100。|
|StartTime|String|可选|查询数据开始时间，默认24小时前，可以输入long型时间，也可以输入yyyy-MM-dd HH:mm:ss类型时间|
|EndTime|String|可选|查询数据结束时间，默认当前时间，可以输入long型时间，也可以输入yyyy-MM-dd HH:mm:ss类型时间|
|Cursor|String|可选|查询数据的起始位置，为空则按时间查询前100条|

## 返回参数 {#section_nnc_r2v_zdb .section}

|名称|类型|描述|
|:-|:-|:-|
|AlarmHistoryList|List|报警历史详情列表。|
|Cursor|String|下一页数据，为空代表没有下一页。|
|Success|Boolean|请求是否成功。|
|RequestId|String|请求的uuid，便于查询日志。|
|Code|String|请求失败状态码，200为成功，非200为失败。|
|Message|String|请求失败的提示信息。|

**History 的参数**

|名称|类型|描述|
|:-|:-|:-|
|Id|String|报警规则的id。|
|Name|String|报警规则的名称。|
|Namespace|String|产品的名称。|
|MetricName|String|监控项名称。|
|Dimension|String|报警规则对应实例，为json object对应的字符串,例如\{“instance”:”name1”\}。|
|EvaluationCount|Int|连续探测几次都满足阈值条件时报警。|
|Value|String|报警的当前值。|
|AlarmTime|Long|报警发生的时间。|
|LastTime|Long|报警持续时间，单位为毫秒。|
|State|String|报警规则状态，有OK，ALARM，INSUFFICIENT\_DATA三种状态。|
|Status|Integer|通知发送状态，0为已通知用户，1为不在生效期未通知，2为处于报警沉默期未通知。|
|ContactGroups|String|发出的报警通知的通知对象，json array对应的字符串，例如\[“联系组1”:”联系组2”\]，只有通知状态为0才有该字段。|

## 示例 {#section_nw3_s2v_zdb .section}

**请求示例**

```
http://metrics.cn-hangzhou.aliyuncs.com/?Action=ListAlarmHistory
&EndTime=2017-03-16+15%3A00%3A00
&Size=3
&StartTime=2017-02-20+10%3A50%3A00
&Id=1a775e37-dfba-430c-ab9f-7036475c8bfb_2dbe619b-0483-402e-9437-7c7a38fba7ed
&<公共请求参数>
```

**返回示例**

-   XML格式

    ```
    <ListAlarmHistoryResponse>
      <AlarmHistoryList>
        <AlarmHistory>
          <Status>2</Status>
          <Value>{"Maximum":301,"Minimum":301}</Value>
          <MetricName>http.status_groupbyinstanceid#60</MetricName>
          <State>ALARM</State>
          <LastTime>122088</LastTime>
          <AlarmTime>1489568222088</AlarmTime>
          <Namespace>acs_sitemonitor</Namespace>
          <ContactGroups>null</ContactGroups>
          <Id>1a775e37-dfba-430c-ab9f-7036475c8bfb_2dbe619b-0483-402e-9437-7c7a38fba7ed</Id>
          <EvaluationCount>3</EvaluationCount>
        </AlarmHistory>
        <AlarmHistory>
          <Status>0</Status>
          <Value>{"Maximum":301,"Minimum":301}</Value>
          <MetricName>http.status_groupbyinstanceid#60</MetricName>
          <State>ALARM</State>
          <LastTime>62078</LastTime>
          <AlarmTime>1489568162078</AlarmTime>
          <Namespace>acs_sitemonitor</Namespace>
          <ContactGroups>["云账号报警联系人"]</ContactGroups>
          <Id>1a775e37-dfba-430c-ab9f-7036475c8bfb_2dbe619b-0483-402e-9437-7c7a38fba7ed</Id>
          <EvaluationCount>3</EvaluationCount>
        </AlarmHistory>
      </AlarmHistoryList>
      <RequestId>7E7A6173-EC07-43A1-ABBF-1F05EBB4C2BB</RequestId>
      <Success>true</Success>
      <Code>200</Code>
    </ListAlarmHistoryResponse>
    ```


-   JSON格式

    ```
    {
        "AlarmHistoryList": {
            "AlarmHistory": [
                {
                    "Status": 2, 
                    "Value": "{\"Maximum\":301,\"Minimum\":301}", 
                    "MetricName": "http.status_groupbyinstanceid#60", 
                    "State": "ALARM", 
                    "LastTime": 122088, 
                    "AlarmTime": 1489568222088, 
                    "Namespace": "acs_sitemonitor", 
                    "ContactGroups": "null", 
                    "Id": "1a775e37-dfba-430c-ab9f-7036475c8bfb_2dbe619b-0483-402e-9437-7c7a38fba7ed", 
                    "EvaluationCount": 3
                }, 
                {
                    "Status": 0, 
                    "Value": "{\"Maximum\":301,\"Minimum\":301}", 
                    "MetricName": "http.status_groupbyinstanceid#60", 
                    "State": "ALARM", 
                    "LastTime": 62078, 
                    "AlarmTime": 1489568162078, 
                    "Namespace": "acs_sitemonitor", 
                    "ContactGroups": "[\"云账号报警联系人\"]", 
                    "Id": "1a775e37-dfba-430c-ab9f-7036475c8bfb_2dbe619b-0483-402e-9437-7c7a38fba7ed", 
                    "EvaluationCount": 3
                }
            ]
        }, 
        "RequestId": "1DBBCE29-0F69-435C-B65C-53D1011D1D72", 
        "Success": true, 
        "Code": "200"
    }
    ```


