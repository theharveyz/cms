# NodeInstall {#doc_api_1005306 .reference}

调用接口为指定ECS 实例安装云监控插件。

可参见[云监控Go语言版本插件介绍](~~99300~~)。

-   使用接口前请确保您的实例已安装[服务器安全（安骑士）插件](~~28451~~)。安骑士插件目前集成于安全镜像中，在购买ECS后，一般都已经默认安装，您可以进入安骑士控制台，查看每台服务器的在线状态。
-   接口安装云监控插件的成功率约为95%，如安装失败，可登录主机手工安装，具体安装请参见[云监控Go语言版本插件安装](~~97929~~)。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Cms&api=NodeInstall)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|InstanceId|String|是|i-abcdefgh123456|实例id，例如：i-22jja5c2l

 |
|UserId|String|是|1234567898765432|阿里云userId

 |
|Action|String|否|NodeInstall|系统规定参数，取值：NodeInstall

 |
|Force|Boolean|否|true|是否强制安装，如果用户已经安装过云监控，默认值为强制安装

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|ErrorCode|Integer|200|请求失败状态码，200为成功，非200为失败

 |
|ErrorMessage|String|MissingInstanceId|请求失败的提示信息

 |
|RequestId|String|58DE3CE4-4EB2-41EB-B15E-A82558AEFAE5|请求的uuid，便于查询日志

 |
|Success|Boolean|true|请求是否成功

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=NodeInstall
&InstanceId=i-abcdefgh123456
&UserId=1234567898765432
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<NodeInstallResponse>
  <ErrorCode>200</ErrorCode>
  <Success>true</Success>
</NodeInstallResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Success":true,
	"ErrorCode":200
}
```

## 错误码 { .section}

[查看本产品错误码](https://error-center.aliyun.com/status/product/Cms)

