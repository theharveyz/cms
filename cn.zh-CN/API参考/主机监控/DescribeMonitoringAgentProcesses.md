# DescribeMonitoringAgentProcesses {#doc_api_Cms_DescribeMonitoringAgentProcesses .reference}

查询进程监控列表。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cms&api=DescribeMonitoringAgentProcesses&type=RPC&version=2019-01-01)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeMonitoringAgentProcesses|系统规定参数。取值：DescribeMonitoringAgentProcesses。

 |
|InstanceId|String|是|i-xx12\*\*\*\*|实例ID。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|String|200|状态码，200表示成功。

 |
|Message|String|Successfully|错误信息。

 |
|NodeProcesses| | |进程列表。

 |
|Command|String|number|用于取得指定进程信息的指令：

 -   number：匹配条件的进程数。
-   detail：返回匹配条件的进程信息。

 |
|InstanceId|String|host-12xxx|实例ID。

 |
|ProcessId|Long|123456|进程ID。

 |
|ProcessName|String|http|进程名称。

 |
|ProcessUser|String|admin|进程用户。

 |
|RequestId|String|971CC023-5A96-452A-BB7C-2483F948BCFD|请求ID，用于排查问题。

 |
|Success|Boolean|true|请求是否成功。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DescribeMonitoringAgentProcesses
&InstanceId=i-xx12****
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeMonitoringAgentProcessesResponse>
      <NodeProcesses>
            <NodeProcess>
              <Command>number</Command>
              <InstanceId>host-123aaaa</InstanceId>
              <ProcessName>http</ProcessName>
              <ProcessId>123455</ProcessId>
        </NodeProcess>
        <NodeProcess>
              <Command>number</Command>
              <InstanceId>host-123aaaa</InstanceId>
              <ProcessName>nginx</ProcessName>
              <ProcessId>123456</ProcessId>
            </NodeProcess>
      </NodeProcesses>
      <Success>true</Success>
      <Code>200</Code>
</DescribeMonitoringAgentProcessesResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"NodeProcesses":{
		"NodeProcess":[
			{
				"Command":"number",
				"InstanceId":"host-123aaaa",
				"ProcessId":123455,
				"ProcessName":"http"
			},
			{
				"Command":"number",
				"InstanceId":"host-123aaaa",
				"ProcessId":123456,
				"ProcessName":"nginx"
			}
		]
	},
	"Success":true,
	"Code":200
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Cms)查看更多错误码。

