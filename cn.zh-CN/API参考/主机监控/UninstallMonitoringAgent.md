# UninstallMonitoringAgent {#doc_api_Cms_UninstallMonitoringAgent .reference}

卸载非阿里云主机监控插件。

不适用于阿里云ECS 插件，阿里云ECS插件卸载请参考相关文档。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cms&api=UninstallMonitoringAgent&type=RPC&version=2019-01-01)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|InstanceId|String|是|host-\*\*\*\*|主机实例ID。

 |
|Action|String|否|UninstallMonitoringAgent|系统规定参数。取值：UninstallMonitoringAgent。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|String|200|状态码，200表示成功。

 |
|Message|String|Successfully|错误信息。

 |
|RequestId|String|466902B9-2842-40B0-B796-00FE772B6EF3|请求ID，用于排查问题。

 |
|Success|Boolean|true|是否成功。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=UninstallMonitoringAgent
&InstanceId=i-xx12****
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<UninstallMonitoringAgentResponse>
    <RequestId>466902B9-2842-40B0-B796-00FE772B6EF3</RequestId>
    <Code>200</Code>
    <Message>Successfully</Message>
</UninstallMonitoringAgentResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Message":"Successfully",
	"RequestId":"466902B9-2842-40B0-B796-00FE772B6EF3",
	"Code":"200"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Cms)查看更多错误码。

