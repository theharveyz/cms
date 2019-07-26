# CreateMonitorAgentProcess {#doc_api_Cms_CreateMonitorAgentProcess .reference}

创建进程监控。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cms&api=CreateMonitorAgentProcess&type=RPC&version=2019-01-01)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|CreateMonitorAgentProcess|系统规定参数。取值：CreateMonitorAgentProcess。

 |
|InstanceId|String|是|i-123\*\*\*\*|实例ID。

 |
|ProcessName|String|是|java|进程名称。

 |
|ProcessUser|String|否|admin|执行进程的用户。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|String|200|状态码，200表示成功。

 |
|Id|Long|123456|进程ID。

 |
|Message|String|Successfully|错误信息。

 |
|RequestId|String|971CC023-5A96-452A-BB7C-2483F948BCFD|请求ID，用于排查问题。

 |
|Success|Boolean|true|是否成功。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=CreateMonitorAgentProcess
&InstanceId=i-123****
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<CreateMonitorAgentProcessResponse>
      <RequestId>971CC023-5A96-452A-BB7C-2483F948BCFD</RequestId>
      <Id>17****</Id>
      <Success>true</Success>
      <Code>200</Code>
</CreateMonitorAgentProcessResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"971CC023-5A96-452A-BB7C-2483F948BCFD",
	"Id":"17****",
	"Success":true,
	"Code":200
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Cms)查看更多错误码。

