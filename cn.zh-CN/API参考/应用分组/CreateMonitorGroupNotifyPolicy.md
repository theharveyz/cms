# CreateMonitorGroupNotifyPolicy {#doc_api_Cms_CreateMonitorGroupNotifyPolicy .reference}

创建暂停应用分组报警通知的策略。

在策略的生效期间内，应用分组内发生的所有报警都不再发送通知。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cms&api=CreateMonitorGroupNotifyPolicy&type=RPC&version=2019-01-01)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|CreateMonitorGroupNotifyPolicy|系统规定参数。取值：CreateMonitorGroupNotifyPolicy。

 |
|GroupId|String|是|12345|应用分组ID。

 |
|PolicyType|String|是|PauseNotify|暂停通知类型， 目前仅支持： PauseNotify。

 |
|StartTime|Long|是|1551756547863|暂停通知的开始时间，距离1970年1月1日 00:00:00的毫秒数。

 |
|EndTime|Long|是|1551757147863|暂停通知的结束时间，距离1970年1月1日 00:00:00的毫秒数。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|String|200|状态码，200表示成功。

 |
|Message|String|success|错误信息。

 |
|RequestId|String|13356BCA-3EC3-4748-A771-2064DA69AEF1|请求ID，用于问题排查。

 |
|Result|Integer|1|返回创建的结果数量。

 |
|Success|String|true|是否成功。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=CreateMonitorGroupNotifyPolicy
&GroupId=12345
&PolicyType=PauseNotify
&StartTime=1551756547863
&EndTime=1551757147863
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<CreateMonitorGroupNotifyPolicyResponse>
      <Result>1</Result>
      <Success>true</Success>
      <Code>200</Code>
</CreateMonitorGroupNotifyPolicyResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Result":1,
	"Success":true,
	"Code":"200"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Cms)查看更多错误码。

