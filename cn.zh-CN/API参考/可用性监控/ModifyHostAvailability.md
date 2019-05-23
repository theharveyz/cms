# ModifyHostAvailability {#doc_api_Cms_ModifyHostAvailability .reference}

修改可用性监控任务。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Cms&api=ModifyHostAvailability)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|AlertConfig.NotifyType|Integer|是|2|报警通知类型：

 -   2：电话+短信+邮件+钉钉机器人,
-   1：短信+邮件+钉钉机器人
-   0：邮件+钉钉机器人

 |
|GroupId|Long|是|12345|应用分组ID。

 |
|Id|Long|是|12345|任务ID。

 |
|TaskName|String|是|我的探测任务|任务名称。

 |
|Action|String|否|ModifyHostAvailability|系统规定参数。取值：ModifyHostAvailability。

 |
|AlertConfig.EndTime|Integer|否|23|报警结束时间，单位是小时，0表示00:59。

 |
|AlertConfig.SilenceTime|Integer|否|86400|通道沉默时间，单位是秒，默认86400（1天）。

 |
|AlertConfig.StartTime|Integer|否|0|报警开始时间，单位是小时，0表示00:00。

 |
|AlertConfig.WebHook|String|否|http://www.aliyun.com/webhook.json|URL回调地址。

 |
|AlertConfigEscalationList.N.Aggregate|String|否|Value|统计方法，不同的监控项有不同的统计方法：

 -   HttpStatus：Value
-   HttpLatency：Average
-   TelnetStatus：Value
-   TelnetLatency：Average
-   PingLostRate：Average

即状态码类的，统计方法是原始值，即VAlue，延时时间或者丢包率都用平均值，即Average。


 |
|AlertConfigEscalationList.N.MetricName|String|否|HttpStatus|需要报警的监控项：

 -   HttpStatus\(HTTP状态码\),
-   HttpLatency\(HTTP等待时间\)
-   TelnetStatus\(TELNET状态码\)
-   TelnetLatency\(TELNET等待时间\)
-   PingLostRate\(PING丢包率） \)

 |
|AlertConfigEscalationList.N.Operator|String|否|\>|比较符号，如`>、>=、<、<=、=。`

 |
|AlertConfigEscalationList.N.Times|Integer|否|3|连续几个周期超过阈值，这个指的是周期数。

 |
|AlertConfigEscalationList.N.Value|String|否|3|报警阈值。

 |
|InstanceList.N|RepeatList|否|i-absdfkwl3212346|发起探测的ecs实例列表，为空表示该应用组下所有的机器。

 |
|TaskOption.HttpMethod|String|否|GET|HTTP探测类型的方法，目前支持GET、POST、HEAD 三种种方法。

 |
|TaskOption.HttpNegative|Boolean|否|true|-   true：包含内容则报警。
-   false：不包含内容则报警。

 |
|TaskOption.HttpResponseCharset|String|否|UTF-8|HTTP探测类型响应字符集。

 |
|TaskOption.HttpResponseMatchContent|String|否|ok|匹配响应的内容。

 |
|TaskOption.HttpURI|String|否|http://www.aliyun.com|HTTP探测类型的探测URI地址。

 |
|TaskOption.TelnetOrPingHost|String|否|www.aliyun.com|如果探测任务是PING或者TELNET，此处写入要探测的域名或者地址。

 |
|TaskScope|String|否|GROUP|任务范围：

 -   GROUP：表示做里的所有ECS作为探测任务的探针
-   INSTANCE：如果选择了INSTANCE 则需要设置InstanceList参数。

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|String|200|状态码，200表示成功。

 |
|Message|String|success|错误信息。

 |
|RequestId|String|ACBDBB40-DFB6-4F4C-8957-51FFB233969C|请求ID，用于排查问题。

 |
|Success|Boolean|true|是否成功。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=ModifyHostAvailability
&AlertConfig.NotifyType=2
&GroupId=12345
&Id=12345
&TaskName=我的探测任务
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<CreateHostAvailabilityResponse>
  <RequestId>ACBDBB40-DFB6-4F4C-8957-51FFB233969C</RequestId>
  <Success>true</Success>
  <Code>200</Code>
</CreateHostAvailabilityResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"ACBDBB40-DFB6-4F4C-8957-51FFB233969C",
	"Success":true,
	"Code":200
}
```

## 错误码 { .section}

[查看本产品错误码](https://error-center.aliyun.com/status/product/Cms)

