# DescribeMonitorGroupNotifyPolicyList {#doc_api_Cms_DescribeMonitorGroupNotifyPolicyList .reference}

查询应用分组的报警通知暂停策略列表。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cms&api=DescribeMonitorGroupNotifyPolicyList&type=RPC&version=2019-01-01)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeMonitorGroupNotifyPolicyList|系统规定参数。取值：DescribeMonitorGroupNotifyPolicyList。

 |
|PolicyType|String|是|PauseNotify|禁用的类型，目前只能选择PauseNotify。

 |
|GroupId|String|否|12346|应用分组ID。

 |
|PageNumber|Integer|否|1|页码，默认值为1。

 |
|PageSize|Integer|否|100|每页记录条数，默认值为10。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|String|200|状态码，200表示成功。

 |
|Message|String|success|错误信息。

 |
|NotifyPolicyList| | |暂停通知列表。

 |
|EndTime|Long|1551761781273|结束时间。

 |
|GroupId|String|12345|组ID。

 |
|Id|String|111|暂停通知的ID。

 |
|StartTime|Long|1551761781273|开始时间。

 |
|Type|String|PauseNotify|类型，目前默认值为PauseNotify。

 |
|RequestId|String|6072F026-C441-41A6-B114-35A1E8F8FDD3|请求ID，用于排查问题。

 |
|Success|String|true|是否成功。

 |
|Total|Integer|11|总记录条数。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DescribeMonitorGroupNotifyPolicyList
&PolicyType=PauseNotify
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeMonitorGroupNotifyPolicyListResponse>
    <NotifyPolicyList>
            <NotifyPolicy>
                  <Type>PauseNotify</Type>
                  <EndTime>1551763581273</EndTime>
                  <Id>7995</Id>
                  <StartTime>1551761781273</StartTime>
                  <GroupId>13263</GroupId>
            </NotifyPolicy>
      </NotifyPolicyList>
      <Success>true</Success>
      <Code>200</Code>
      <Total>1</Total>
</DescribeMonitorGroupNotifyPolicyListResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"NotifyPolicyList":{
		"NotifyPolicy":[
			{
				"Type":"PauseNotify",
				"Id":7995,
				"EndTime":1551763581273,
				"StartTime":1551761781273,
				"GroupId":"13263"
			}
		]
	},
	"Success":true,
	"Code":"200",
	"Total":1
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Cms)查看更多错误码。

