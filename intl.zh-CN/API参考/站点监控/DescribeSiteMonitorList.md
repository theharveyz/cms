# DescribeSiteMonitorList {#doc_api_Cms_DescribeSiteMonitorList .reference}

查询站点监控任务列表。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Cms&api=DescribeSiteMonitorList)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeSiteMonitorList|系统规定参数。取值：DescribeSiteMonitorList。

 |
|Keyword|String|否|site|支持根据名称或任务地址模糊搜索。

 |
|Page|Integer|否|1|分页页码，默认值为1。

 |
|PageSize|Integer|否|10|每页显示条数，默认值为10。

 |
|TaskId|String|否|a1ecd34a-8157-44d9-b060-14950837\*\*\*\*|任务ID。

 |
|TaskType|String|否|HTTP|站点监控任务探测类型。

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|String|200|状态码，200表示成功。

 |
|Message|String|Successfully|错误信息。

 |
|PageNumber|Integer|1|分页页码。

 |
|PageSize|Integer|10|每页显示记录条数，默认10。

 |
|RequestId|String|68192f5d-0d45-4b98-9724-892813f86c71|请求ID，用于排查问题。

 |
|SiteMonitors| | |站点监控任务列表。

 |
|└Address|String|http://www.aliyun.com|任务的探测URL地址或IP地址。

 |
|└CreateTime|String|2019-03-02 09:02:51|任务的创建时间。

 |
|└Interval|String|1|探测频率，单位为分钟。

 |
|└OptionsJson|Json|\{"time\_out":5000\}|监控对应协议的高级扩展选项， 不同的探测协议类型，有不同的扩展选项。

 |
|└TaskId|String|a1ecd34a-8127-44d9-b060-14950837\*\*\*\*|任务ID。

 |
|└TaskName|String|新的探测任务|任务名称。

 |
|└TaskState|String|1|任务状态，1：正常， 2：禁用。

 |
|└TaskType|String|HTTP|任务的类型，目前站点监控探测的有：HTTP 、PING 、TCP 、UDP 、DNS 、SMTP 、POP3 、FTP。

 |
|└UpdateTime|String|2019-03-03 14:16:34|任务更新时间。

 |
|Success|String|true|是否成功。

 |
|TotalCount|Integer|10|总记录条数。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DescribeSiteMonitorList
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeSiteMonitorListResponse>
  <Message>请求成功</Message>
  <RequestId>95078877-009D-43C2-8654-67AE771C08D9</RequestId>
  <SiteMonitors>
    <SiteMonitor>
      <Interval>1</Interval>
      <CreateTime>2019-03-02 09:02:51</CreateTime>
      <Address>http://www.aliyun.com</Address>
      <OptionsJson>
        <http_method>get</http_method>
        <time_out>30000</time_out>
      </OptionsJson>
      <UpdateTime>2019-03-03 15:48:00</UpdateTime>
      <TaskId>49f7b317-7645-4cc9-94fd-12****</TaskId>
      <TaskName>阿里云官网探测</TaskName>
      <TaskState>2</TaskState>
      <TaskType>HTTP</TaskType>
    </SiteMonitor>
  </SiteMonitors>
  <Success>true</Success>
  <Code>200</Code>
</DescribeSiteMonitorListResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Message":"请求成功",
	"RequestId":"95078877-009D-43C2-8654-67AE771C08D9",
	"Success":true,
	"SiteMonitors":{
		"SiteMonitor":[
			{
				"Interval":1,
				"Address":"http://www.aliyun.com",
				"CreateTime":"2019-03-02 09:02:51",
				"OptionsJson":{
					"http_method":"get",
					"time_out":30000
				},
				"UpdateTime":"2019-03-03 15:48:00",
				"TaskId":"49f7b317-7645-4cc9-94fd-12****",
				"TaskType":"HTTP",
				"TaskState":2,
				"TaskName":"阿里云官网探测"
			}
		]
	},
	"Code":"200"
}
```

## 错误码 { .section}

[查看本产品错误码](https://error-center.aliyun.com/status/product/Cms)

