# DeleteSiteMonitors {#doc_api_Cms_DeleteSiteMonitors .reference}

删除站点监控的探测任务。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cms&api=DeleteSiteMonitors&type=RPC&version=2019-01-01)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DeleteSiteMonitors|系统规定参数。取值：DeleteSiteMonitors。

 |
|TaskIds|String|是|01adacc2-ece5-41b6-afa2-3143ab5da7a0,43bd1ead-514f-4524-813e-228ce091\*\*\*\*|要删除的任务ID，多个任务ID之间用英文逗号分隔。

 |
|IsDeleteAlarms|Boolean|否|true|删除任务的同时是否删除报警规则，默认值为True。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|String|200|状态码，200表示成功。

 |
|Data|String|\{ "count": 0 \}|返回受影响的行数。

 |
|Message|String|Successful|错误信息。

 |
|RequestId|String|123BCC5D-8B63-48EA-B747-9A8995BE7AA6|请求ID，用于排查问题。

 |
|Success|String|true|是否成功。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DeleteSiteMonitors
&TaskIds=01adacc2-ece5-41b6-afa2-3143ab5da7a0,43bd1ead-514f-4524-813e-228ce091****
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DeleteSiteMonitorsResponse>
    <RequestId>6661EC50-8625-4161-B349-E0DD59002AB7</RequestId>
    <Success>true</Success>
    <Code>200</Code>
    <Message>Successful</Message>
</DeleteSiteMonitorsResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Data":{
		"count":0
	},
	"Message":"请求成功",
	"RequestId":"123BCC5D-8B63-48EA-B747-9A8995BE7AA6",
	"Success":true,
	"Code":"200"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Cms)查看更多错误码。

