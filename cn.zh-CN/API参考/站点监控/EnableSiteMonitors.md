# EnableSiteMonitors {#doc_api_Cms_EnableSiteMonitors .reference}

启用一个或者多个站点监控探测任务。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cms&api=EnableSiteMonitors&type=RPC&version=2019-01-01)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|EnableSiteMonitors|系统规定参数。取值：EnableSiteMonitors。

 |
|TaskIds|String|是|49f7b317-7645-4cc9-94fd-ea42e522\*\*\*\*,49f7b317-7645-4cc9-94fd-ea42e522\*\*\*\*|要启用的任务ID，多个任务用逗号分隔。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|String|200|状态码，200表示成功。

 |
|Data|String|\{"count": 0\}|返回影响的记录条数。

 |
|Message|String|Successfully|错误信息。

 |
|RequestId|String|3fcd12e7-d387-42ee-b77e-661c775bb17f|请求ID，用于排查问题。

 |
|Success|String|true|是否成功。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=EnableSiteMonitors
&TaskIds=49f7b317-7645-4cc9-94fd-ea42e522****,49f7b317-7645-4cc9-94fd-ea42e522****
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DisableSiteMonitorsResponse>
      <Message>successful</Message>
      <RequestId>3fcd12e7-d387-42ee-b77e-661c775bb17f</RequestId>
      <Code>200</Code>
      <Success>true</Success>
</DisableSiteMonitorsResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Data":"{\"count\":1}",
	"Message":"successful",
	"RequestId":"3fcd12e7-d387-42ee-b77e-661c775bb17f",
	"Success":true,
	"Code":"200"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Cms)查看更多错误码。

