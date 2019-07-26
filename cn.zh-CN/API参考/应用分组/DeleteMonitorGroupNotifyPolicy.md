# DeleteMonitorGroupNotifyPolicy {#doc_api_Cms_DeleteMonitorGroupNotifyPolicy .reference}

删除指定应用分组的报警通知暂停策略。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cms&api=DeleteMonitorGroupNotifyPolicy&type=RPC&version=2019-01-01)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DeleteMonitorGroupNotifyPolicy|系统规定参数。取值：DeleteMonitorGroupNotifyPolicy。

 |
|PolicyType|String|是|PauseNotify|暂停通知类型，目前仅支持PauseNotify。

 |
|GroupId|String|否|12345|应用分组ID。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|String|200|状态码，200表示成功。

 |
|Message|String|success|错误信息。

 |
|RequestId|String|B7AF834D-D38B-4A46-920B-FE974EB7E135|请求ID，用于排查问题。

 |
|Result|Integer|1|影响行数。

 |
|Success|String|true|是否成功。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DeleteMonitorGroupNotifyPolicy
&PolicyType=PauseNotify
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DeleteMonitorGroupNotifyPolicyResponse>
      <Result>1</Result>
      <Success>true</Success>
      <Code>200</Code>
</DeleteMonitorGroupNotifyPolicyResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Result":2,
	"RequestId":"5D0D3910-5B01-4868-A2F2-A5DEA7F5150E",
	"Success":true,
	"Code":200
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Cms)查看更多错误码。

