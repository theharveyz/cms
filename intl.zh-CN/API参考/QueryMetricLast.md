# QueryMetricLast {#reference_kxr_y2z_zdb .reference}

## 描述 {#section_svh_z2z_zdb .section}

查询指定监控对象的最新监控数据。

## 请求参数 {#section_etr_z2z_zdb .section}

|名称|类型|必填|描述|
|:-|:-|:-|:-|
|Action|String|是|操作接口名，系统规定参数，取值: QueryMetricLast|
|Project|String|是|名字空间，表明监控数据所属产品，如 “acs\_ecs\_dashboard”，“acs\_rds\_dashboard”等|
|Metric|String|是|监控项名称|
|Period|String|否|时间间隔，统一用秒数来计算，例如 60, 300, 900。 如果不填写，则按照注册监控项时申明的上报周期来查询原始数据。如果填写统计周期,则查询对应的统计数据。|
|StartTime|String|否|开始时间，可以传入距离 1970 年 1 月 1 日 0 点的毫秒数，也可以传入format数据，如2015-10-20 00:00:00。|
|EndTime|String|否|可以传入距离 1970 年 1 月 1 日 0 点的毫秒数，也可以传入format数据，如2015-10-20 00:00:00。|
|Dimensions|String|否|用于过滤监控数据的 key-value 集合，key 可以使用注册监控项时申明的 dimensionKeys 中的一个或多个，value 为 该 key 对应的值。instanceId 是必填项 需要使用 JSON 字符串表示该 Map 对象，传入时请使用字符串，dimension要求必须按顺序传入。|
|Length|String|否|返回监控数据的每页大小，用于分页查询。默认值为1000，即每页1000条监控数据。|
|Cursor|String|否|游标|

各云产品的Project、Metric、Period、Dimensions等入参如何赋值，请参见[预设监控项参考](intl.zh-CN/API参考/预设监控项参考.md#)。

## 返回参数 {#section_wyb_1fz_zdb .section}

|名称|类型|描述|
|:-|:-|:-|
|Period|String|时间间隔，统一用秒数来计算，例如 60, 300, 900。|
|Cursor|String|游标|
|Datapoints|List|监控数据列表，内容格式例如：\{ “timestamp”: 1490164200000,”Maximum”: 100,”userId”: “1234567898765432”, “Minimum”: 4.55,”instanceId”: “i-bp18abl200xk9599ck7c”, “Average”: 93.84\}|
|Code|String|状态码，正常为”200”。|
|Success|Boolean|是否成功执行，如果服务器端有异常此返回值为false，正常为true。|
|Message|String|状态描述信息，Code为“200”时，Message一般为空。|
|RequestId|String|当请求出现问题时，可以提供此字段给技术人员进行问题排查。|

## 示例 {#section_shl_1fz_zdb .section}

**请求示例**

```
http://metrics.cn-hangzhou.aliyuncs.com/?Action=QueryMetricLast
&EndTime=2017-03-22+14%3A30%3A27
&StartTime=2017-03-22+14%3A20%3A27
&Period=60
&Dimensions=%7BinstanceId%3A%27 i-abcdefgh123456%27%7D
&Project=acs_ecs_dashboard
&Metric=cpu_idle
&<公共请求参数>
```

**返回示例**

-   XML格式

    ```
    <QueryMetricLastResponse>
      <Period>60</Period>
      <Datapoints>
        <Datapoints>
          <timestamp>1490164200000</timestamp>
          <Maximum>100</Maximum>
          <userId>1234567898765432</userId>
          <Minimum>4.55</Minimum>
          <instanceId>i-bp18abl200xk9599ck7c</instanceId>
          <Average>93.84</Average>
        </Datapoints>
      </Datapoints>
      <RequestId>021472A6-25E3-4094-8D00-BA4B6A5486C3</RequestId>
      <Success>true</Success>
      <Code>200</Code>
    </QueryMetricLastResponse>
    ```

-   JSON格式

    ```
    {
        "Period": "60", 
        "Datapoints": [
            {
                "timestamp": 1490164200000, 
                "Maximum": 100, 
                "userId": "1234567898765432", 
                "Minimum": 4.55, 
                "instanceId": "i-bp18abl200xk9599ck7c", 
                "Average": 93.84
            }
        ], 
        "RequestId": "4E7664F2-9CDE-4212-9318-A0712D345A5E", 
        "Success": true, 
        "Code": "200"
    }
    ```


