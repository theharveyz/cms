# DeleteContactGroup {#doc_api_Cms_DeleteContactGroup .reference}

删除报警联系人组。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cms&api=DeleteContactGroup&type=RPC&version=2019-01-01)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DeleteContactGroup|系统规定参数。取值：DeleteContactGroup。

 |
|ContactGroupName|String|是|我的报警组|报警联系组名称。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|String|200|状态码，200表示成功。

 |
|Message|String|success|错误信息。

 |
|RequestId|String|F722BE59-2400-4A64-9C1A-AD886AED9A69|请求ID，用于排查问题。

 |
|Success|Boolean|true|是否成功。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DeleteContactGroup
&ContactGroupName=我的报警组
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DeleteContactGroupResponse>
      <RequestId>F722BE59-2400-4A64-9C1A-AD886AED9A69</RequestId>
      <Success>true</Success>
      <Code>200</Code>
</DeleteContactGroupResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"F722BE59-2400-4A64-9C1A-AD886AED9A69",
	"Success":true,
	"Code":"200"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Cms)查看更多错误码。

