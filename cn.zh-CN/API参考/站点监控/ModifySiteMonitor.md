# ModifySiteMonitor {#doc_api_Cms_ModifySiteMonitor .reference}

修改站点监控探测任务。

站点监控支持 HTTP 、PING 、TCP 、UDP 、DNS 、SMTP 、POP3 、FTP 8种类型的探测任务，不同的类型对应不同的扩展参数\(OptionsJson\)，扩展参数说明详见如下列表：

 **HTTP** 

|参数名

|类型

|描述

|
|-----|----|----|
|http\_method

|String

|HTTP请求方式，支持三种：GET、POST、HEAD。缺省值为GET。

|
|header

|String

|换行符\("\\n"\)分隔的用户自定义HTTP header。每行header格式需符合http协议要求（英文冒号分隔的键值）。

|
|cookie

|String

|cookie , 和HTTP请求标准的写法一致。

|
|request\_content

|String

|请求内容。支持两种格式：json和表单，不提供时，请求中不含正文。

|
|response\_content

|String

|期望的回应内容。探测时会在HTTP服务器返回的前64K字节进行检查。

|
|match\_rule

|String

|0 - 回应中不含response\_content时，探测成功， 1 - 回应中含response\_content时，探测成功。

|
|username

|String

|如果提供username，则会在http请求中携带BasicAuth header。

|
|password

|String

|HTTP请求验证密码。

|
|time\_out

|int

|超时时间，单位：毫秒。缺省：5秒。

|
|max\_redirect

|int

|大跳转次数。ECS探针缺省5次，运营商探针缺省2次。如果需要禁止跳转，则将该值置为：0。取值范围：\[0, 50\]。

|

 **PING** 

|参数名

|类型

|描述

|
|-----|----|----|
|failure\_rate

|int

|当PING失败率超过该值时。则探测失败。返回610\(PingAllFail\)，或615\(PingPartialFail\)。缺省：0.1 。

|
|ping\_num

|int

|PING次数，缺省：20。取值范围：\[1, 100\]。

|

 **DNS** 

|参数名

|类型

|描述

|
|-----|----|----|
|dns\_server

|string

|DNS服务器地址，可以为域名或IP地址。

|
|dns\_type

|string

|DNS查询类型，可取值：A、NS、CNAME、MX、TXT、ANY。

|
|expect\_value

|string

|英文空白符\(参见下表\)分隔的期望值列表。

|
|match\_rule

|string

|期望值列表与dns列表的关系，当不满足指定关系时，探测失败。

 空字符串或IN\_DNS: 期望值列表是dns列表的子集。

 DNS\_IN: dns列表是期望值列表的子集

 EQUAL: dns列表与期望值列表相等

 ANY: dns列表与期望值列表有交集\(交集不为空\)。

 |

 **FTP** 

|参数名

|类型

|描述

|
|-----|----|----|
|port

|int

|FTP服务器端口号。如果不提供，则使用缺省：ftp: 21, ftps: 990。

|
|username

|string

|用户名、密码。 如果未提供则匿名登录。用户名：anonymous 密码：ftp@example.com。

|
|password

|string

|FTP密码。

|

 **POP3/SMTP** 

|参数名

|类型

|描述

|
|-----|----|----|
|port

|int

|POP3服务器端口号。缺省为 pop3:110， pop3s:995。

|
|username

|string

|用户名。

|
|password

|string

|密码。

|

 **TCP/UDP** 

|参数名

|类型

|描述

|
|-----|----|----|
|port

|int

|探测的TCP/UDP端口。

|
|request\_content

|string

|请求的内容。当request\_format为"hex"时，request\_content的内容为十六进制紧凑格式。

|
|request\_format

|string

|当request\_format为其它值时，request\_content作为普通字符串发送给服务器。

|
|response\_content

|string

|回应内容。当服务器返回的内容中不含response\_content时，探测失败。当response\_format为"hex"时，response\_content中的内容为十六进制紧凑格式。当response\_content为其它值时，response\_content为普通字符串。

|

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Cms&api=ModifySiteMonitor)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|ModifySiteMonitor|系统规定参数。取值：ModifySiteMonitor。

 |
|TaskId|String|是|49f7b317-7645-4cc9-94fd-ea42e522\*\*\*\*|站点监控探测任务ID。

 |
|Address|String|否|http://www.aliyun.com|任务的探测URL地址或IP地址。

 |
|AlertIds|String|否|49f7c317-7645-4cc9-94fd-ea42e122\*\*\*\*|关联已存在的报警规则ID。

 |
|Interval|String|否|1|探测频率，单位为分钟，取值范围1、5、15，单位是分钟，默认值为1分钟。

 |
|IspCities|String|否|\[\{"city":"546","isp":"465"\},\{"city":"572","isp":"465"\},\{"city":"738","isp":"465"\}\]|探针的信息， 格式为jsonArray，例如`[{"city":"546","isp":"465"},{"city":"572","isp":"465"},{"city":"738","isp":"465"}]`（分别对应北京、杭州、青岛\)

 可以使用 DescribeISPAreaCity 接口获取探测点信息。如果为空系统则随机选择3个探点探测。

 |
|OptionsJson|String|否|\{"time\_out":5000\}|监控对应协议的高级扩展选项， 不同的探测协议类型，有不同的扩展选项。

 |
|TaskName|String|否|网站探测修改|站点监控探测任务名称，为4-100位长度的英文字符、数字、下划线以及汉字。

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|String|200|状态码，200表示成功。

 |
|Data|String|\{ "count": 1\}|返回影响结果数量。

 |
|Message|String|Successfully|错误信息。

 |
|RequestId|String|68192f5d-0d45-4b98-9724-892813f86c71|请求的ID， 用于排查问题。

 |
|Success|String|true|是否成功。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=ModifySiteMonitor
&TaskId=49f7b317-7645-4cc9-94fd-ea42e522****
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<ModifySiteMonitorResponse>
  <Data>
    <count>1</count>
  </Data>
  <Message>请求成功</Message>
  <RequestId>B6593DD0-73E6-48EF-8019-ED4687ED378D</RequestId>
  <Success>true</Success>
  <Code>200</Code>
</ModifySiteMonitorResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Data":{
		"count":1
	},
	"Message":"请求成功",
	"RequestId":"B6593DD0-73E6-48EF-8019-ED4687ED378D",
	"Success":true,
	"Code":"200"
}
```

## 错误码 { .section}

[查看本产品错误码](https://error-center.aliyun.com/status/product/Cms)

