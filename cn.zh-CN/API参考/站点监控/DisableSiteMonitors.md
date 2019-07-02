# DisableSiteMonitors {#doc_api_Cms_DisableSiteMonitors .reference}

禁用一个或者多个站点监控探测任务。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Cms&api=DisableSiteMonitors)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DisableSiteMonitors|系统规定参数。取值：DisableSiteMonitors。

 |
|TaskIds|String|是|49f7b317-7645-4cc9-94fd-ea42e522\*\*\*\*,49f7b317-7645-4cc9-94fd-ea42e522\*\*\*\*|要禁用的任务ID，多个任务ID之间用逗号分隔。

 |

## 返回参数 {#resultMapping .section}

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

http(s)://[Endpoint]/?Action=DisableSiteMonitors
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

[查看本产品错误码](https://error-center.aliyun.com/status/product/Cms)

