# SendDryRunSystemEvent {#doc_api_Cms_SendDryRunSystemEvent .reference}

触发一个用于调试的系统事件，用于调试事件下游配置的触发逻辑是否符合预期。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Cms&api=SendDryRunSystemEvent)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|SendDryRunSystemEvent|系统规定参数。取值：SendDryRunSystemEvent。

 |
|EventName|String|是|Agent\_Status\_Stopped|事件名称。

 |
|Product|String|是|CloudMonitor|产品名称。

 |
|EventContent|String|否|\{"product":"CloudMonitor","resourceId":"acs:ecs:cn-hongkong:173651113438\*\*\*\*:instance/\{instanceId\}","level":"CRITICAL","instanceName":"instanceName","regionId":"cn-hangzhou","name":"Agent\_Status\_Stopped","content":\{"ipGroup":"0.0.0.0,0.0.0.1","tianjimonVersion":"1.2.11"\},"status":"stopped"\}|事件内容。

 |
|GroupId|String|否|12345|应用分组ID。

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|String|200|状态码，200表示成功。

 |
|Message|String|success|错误信息。

 |
|RequestId|String|486029C9-53E1-44B4-85A8-16A571A043FD|请求ID，用于排查问题。

 |
|Success|String|true|是否成功。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=SendDryRunSystemEvent
&EventName=Agent_Status_Stopped
&Product=CloudMonitor
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<SendDryRunSystemEventResponse>
  <Message>success</Message>
  <RequestId>590FB642-5FFE-4AE0-883B-E1323DD20541</RequestId>
  <Code>200</Code>
  <Success>true</Success>
</SendDryRunSystemEventResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Message":"success",
	"RequestId":"590FB642-5FFE-4AE0-883B-E1323DD20541",
	"Success":true,
	"Code":"200"
}
```

## 错误码 { .section}

[查看本产品错误码](https://error-center.aliyun.com/status/product/Cms)

