# CreateMonitorGroup {#doc_api_Cms_CreateMonitorGroup .reference}

创建一个应用分组。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cms&api=CreateMonitorGroup&type=RPC&version=2019-01-01)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|CreateMonitorGroup|系统规定参数。取值：CreateMonitorGroup。

 |
|GroupName|String|是|我的应用分组1|应用分组名称。

 |
|ContactGroups|String|否|默认报警联系人组|报警联系人组。应用分组的报警通知会发送给此处指定的报警联系人组。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|Integer|200|状态码，200表示成功。

 |
|GroupId|Long|123456|创建组以后生成的应用分组ID。

 |
|Message|String|success|状态描述信息，Code为”200”时，Message一般为空。

 |
|RequestId|String|3121AE7D-4AFF-4C25-8F1D-C8226EBB1F42|请求ID，用于排查问题。

 |
|Success|Boolean|true|是否成功。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=CreateMonitorGroup
&GroupName=我的应用分组1
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<CreateMonitorGroupResponse>
      <RequestId>69C34563-DD18-419E-A7C3-60D0913254E9</RequestId>
      <Success>true</Success>
      <GroupId>3391309</GroupId>
      <Code>200</Code>
</CreateMonitorGroupResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"69C34563-DD18-419E-A7C3-60D0913254E9",
	"Success":true,
	"Code":200,
	"GroupId":3391309
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Cms)查看更多错误码。

