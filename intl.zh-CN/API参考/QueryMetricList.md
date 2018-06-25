# QueryMetricList {#reference_uq4_mfz_zdb .reference}

## 描述 {#section_a2c_pfz_zdb .section}

查询一段时间内指定产品实例的监控数据。

## 请求参数 {#section_xwj_pfz_zdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是|操作接口名，系统规定参数，取值：QueryMetricList|
|Project|String|是|名字空间，表明监控数据所属产品，如 “acs\_ecs\_dashboard”,“acs\_rds\_dashboard”等|
|Metric|String|是|监控项名称|
|Period|String|否|时间间隔，统一用秒数来计算，例如 60, 300, 900。 如果不填写,则按照注册监控项时申明的上报周期来查询原始数据。如果填写统计周期，则查询对应的统计数据 。|
|StartTime|String|否|开始时间,可以传入距离1970年1月1日0点的毫秒数，也可以传入format数据，如2015-10-20 00:00:00。|
|EndTime|String|否|可以传入距离1970年1月1日 0点的毫秒数，也可以传入format数据，如2015-10-20 00:00:00。|
|Dimensions|String|否|用于过滤监控数据的 key-value 集合，常用的key-value集合为“instanceId：XXXXXX”。需要使用 JSON 字符串表示该 Map 对象，传入时请使用字符串，Dimensions字段必须按顺序传入。|
|Length|String|否|每次查询大小，用于分页查询，默认值为1000。|
|Cursor|String|否|游标|

**参数说明**

-   各云产品的Project、Metric、Period、Dimensions等入参如何赋值，请参考[预设监控项参考](intl.zh-CN/API参考/预设监控项参考.md#)。
-   开始和结束时间执行的是左开右闭的模式，startTime不能等于或者大于endTime。
-   Cursor是分页模式下的参数，只要存在就说明还有下一页，返回为null则说明没有下一页。
-   Period一般包含60（一分钟）、300（五分钟）、900（十五分钟）。请根据文档以及查询场景的需要考虑Period。比如查询一天范围使用Period为60，则返回1000条数据（实际存在1440，因为最大返回值不超过1000，则只返回前1000条）。如果使用Period为300，则返回288条数据。
-   本接口支持RAM子账号调用，授权时操作描述符为`cms:QueryMetricList`，资源描述符为`*`。

## 返回参数 {#section_imy_pfz_zdb .section}

|名称|类型|描述|
|:-|:-|:-|
|Period|String|时间间隔，统一用秒数来计算,例如 60, 300, 900。|
|Cursor|String|游标|
|Datapoints|String|监控数据列表，内容格式例如：\{ “timestamp”: 1490164200000, “Maximum”: 100, “userId”: “1234567898765432”, “Minimum”: 4.55, “instanceId”: “i-bp18abl200xk9599ck7c”, “Average”: 93.84 \}|
|Code|String|状态码，正常为”200”。|
|Success|Boolean|否成功执行，如果服务器端有异常此返回值为false，正常为true。|
|Message|String|状态描述信息，Code为”200”时，Message一般为空。|
|RequestId|String|当请求出现问题时，可以提供此字段给技术人员进行问题排查。|

## 示例 {#section_up5_qfz_zdb .section}

**请求示例**

```
http://metrics.cn-hangzhou.aliyuncs.com/?Action=QueryMetricList
&EndTime=2017-05-17+11%3A30%3A27
&StartTime=2017-05-17+11%3A20%3A27
&Period=60
&Dimensions=%7B%22instanceId%22%3A%22i-abcdefgh123456%22%7D
&Timestamp=2017-03-22T09%3A30%3A57Z
&Project=acs_ecs_dashboard
&Metric=cpu_idle
```

**返回示例**

-   XML格式

    ```
    <QueryMetricListResponse>
      <Period>60</Period>
      <Datapoints>
        <Datapoints>
          <timestamp>1490152860000</timestamp>
          <Maximum>100</Maximum>
          <userId> 1234567898765432</userId>
          <Minimum>93.1</Minimum>
          <instanceId>i-abcdefgh123456</instanceId>
          <Average>99.52</Average>
        </Datapoints>
        <Datapoints>
          <timestamp>1490152920000</timestamp>
          <Maximum>100</Maximum>
          <userId> 1234567898765432 </userId>
          <Minimum>92.59</Minimum>
          <instanceId>i-abcdefgh123456</instanceId>
          <Average>99.49</Average>
        </Datapoints>
        <Datapoints>
          <timestamp>1490152980000</timestamp>
          <Maximum>100</Maximum>
          <userId>1234567898765432</userId>
          <Minimum>92.86</Minimum>
          <instanceId>i-abcdefgh123456</instanceId>
          <Average>99.44</Average>
        </Datapoints>
        <Datapoints>
          <timestamp>1490153040000</timestamp>
          <Maximum>100</Maximum>
          <userId>1234567898765432</userId>
          <Minimum>91.43</Minimum>
          <instanceId>i-abcdefgh123456</instanceId>
          <Average>99.36</Average>
        </Datapoints>
        <Datapoints>
          <timestamp>1490153100000</timestamp>
          <Maximum>100</Maximum>
          <userId>1234567898765432</userId>
          <Minimum>93.55</Minimum>
          <instanceId>i-abcdefgh123456</instanceId>
          <Average>99.51</Average>
        </Datapoints>
        <Datapoints>
          <timestamp>1490153160000</timestamp>
          <Maximum>100</Maximum>
          <userId>1234567898765432</userId>
          <Minimum>93.1</Minimum>
          <instanceId>i-abcdefgh123456</instanceId>
          <Average>99.52</Average>
        </Datapoints>
        <Datapoints>
          <timestamp>1490153220000</timestamp>
          <Maximum>100</Maximum>
          <userId>1234567898765432</userId>
          <Minimum>92.59</Minimum>
          <instanceId>i-abcdefgh123456</instanceId>
          <Average>99.42</Average>
        </Datapoints>
        <Datapoints>
          <timestamp>1490153280000</timestamp>
          <Maximum>100</Maximum>
          <userId>1234567898765432</userId>
          <Minimum>91.18</Minimum>
          <instanceId>i-abcdefgh123456</instanceId>
          <Average>99.34</Average>
        </Datapoints>
        <Datapoints>
          <timestamp>1490153340000</timestamp>
          <Maximum>100</Maximum>
          <userId>1234567898765432</userId>
          <Minimum>92.86</Minimum>
          <instanceId>i-abcdefgh123456</instanceId>
          <Average>99.46</Average>
        </Datapoints>
        <Datapoints>
          <timestamp>1490153400000</timestamp>
          <Maximum>100</Maximum>
          <userId>1234567898765432</userId>
          <Minimum>91.18</Minimum>
          <instanceId>i-abcdefgh123456</instanceId>
          <Average>99.35</Average>
        </Datapoints>
      </Datapoints>
      <RequestId>6661EC50-8625-4161-B349-E0DD59002AB7</RequestId>
      <Success>true</Success>
      <Code>200</Code>
    </QueryMetricListResponse>
    ```

-   JSON格式

    ```
    {
        "Period": "60", 
        "Datapoints": [
            {
                "timestamp": 1490152860000, 
                "Maximum": 100, 
                "userId": "1234567898765432", 
                "Minimum": 93.1, 
                "instanceId": "i-abcdefgh123456", 
                "Average": 99.52
            }, 
            {
                "timestamp": 1490152920000, 
                "Maximum": 100, 
                "userId": "1234567898765432", 
                "Minimum": 92.59, 
                "instanceId": "i-abcdefgh123456", 
                "Average": 99.49
            }, 
            {
                "timestamp": 1490152980000, 
                "Maximum": 100, 
                "userId": "1234567898765432", 
                "Minimum": 92.86, 
                "instanceId": "i-abcdefgh123456", 
                "Average": 99.44
            }, 
            {
                "timestamp": 1490153040000, 
                "Maximum": 100, 
                "userId": "1234567898765432", 
                "Minimum": 91.43, 
                "instanceId": "i-abcdefgh123456", 
                "Average": 99.36
            }, 
            {
                "timestamp": 1490153100000, 
                "Maximum": 100, 
                "userId": "1234567898765432", 
                "Minimum": 93.55, 
                "instanceId": "i-abcdefgh123456", 
                "Average": 99.51
            }, 
            {
                "timestamp": 1490153160000, 
                "Maximum": 100, 
                "userId": "1234567898765432", 
                "Minimum": 93.1, 
                "instanceId": "i-abcdefgh123456", 
                "Average": 99.52
            }, 
            {
                "timestamp": 1490153220000, 
                "Maximum": 100, 
                "userId": "1234567898765432", 
                "Minimum": 92.59, 
                "instanceId": "i-abcdefgh123456", 
                "Average": 99.42
            }, 
            {
                "timestamp": 1490153280000, 
                "Maximum": 100, 
                "userId": "1234567898765432", 
                "Minimum": 91.18, 
                "instanceId": "i-abcdefgh123456", 
                "Average": 99.34
            }, 
            {
                "timestamp": 1490153340000, 
                "Maximum": 100, 
                "userId": "1234567898765432", 
                "Minimum": 92.86, 
                "instanceId": "i-abcdefgh123456", 
                "Average": 99.46
            }, 
            {
                "timestamp": 1490153400000, 
                "Maximum": 100, 
                "userId": "1234567898765432", 
                "Minimum": 91.18, 
                "instanceId": "i-abcdefgh123456", 
                "Average": 99.35
            }
        ], 
        "RequestId": "6A5F022D-AC7C-460E-94AE-B9E75083D027", 
        "Success": true, 
        "Code": "200"
    }
    ```


