# DeleteCustomMetric {#doc_api_Cms_DeleteCustomMetric .reference}

删除自定义监控上报数据。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cms&api=DeleteCustomMetric&type=RPC&version=2019-01-01)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DeleteCustomMetric|系统规定参数。取值：DeleteCustomMetric。

 |
|GroupId|String|是|12345|应用分组ID。

 |
|MetricName|String|是|cpu|监控项的名称。

 |
|Md5|String|否|38796C8CFFEB8F89BB2A626C7BD79FD3|md5校验码， 在查询监控列表的时候会返回。

 |
|UUID|String|否|5497633c-66c5-4eae-abaa-89db5adb\*\*\*\*|用于区分metric唯一性的参数，在查询自定义metric的时候会返回。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|String|200|状态码， 200表示成功。

 |
|Message|String|success|错误信息。

 |
|RequestId|String|05B36C2C-5F6E-48D5-8B41-CE36DD7EE8E0|请求ID，用于排查问题。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DeleteCustomMetric
&GroupId=12345
&MetricName=cpu
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DeleteCustomMetricResponse>
      <Message>success</Message>
      <RequestId>05B36C2C-5F6E-48D5-8B41-CE36DD7EE8E0</RequestId>
      <Code>200</Code>
</DeleteCustomMetricResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Message":"success",
	"RequestId":"05B36C2C-5F6E-48D5-8B41-CE36DD7EE8E0",
	"Code":"200"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Cms)查看更多错误码。

