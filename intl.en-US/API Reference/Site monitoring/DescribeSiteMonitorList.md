# DescribeSiteMonitorList {#doc_api_Cms_DescribeSiteMonitorList .reference}

You can call this operation to query site monitoring tasks.

## Debugging {#apiExplorer .section}

Alibaba Cloud provides OpenAPI Explorer to simplify API usage. You can use [OpenAPI Explorer](https://api.aliyun.com/#product=Cms&api=DescribeSiteMonitorList) to search for APIs, call APIs, and dynamically generate SDK example code.

## Request parameters {#parameters .section}

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeSiteMonitorList|The operation that you want to perform. Set this parameter to DescribeSiteMonitorList.

 |
|Keyword|String|No|site|The search keyword. CloudMonitor supports fuzzy search based on the task name or monitored address.

 |
|Page|Integer|No|1|The number of the page to return. Default value: 1.

 |
|PageSize|Integer|No|10|The number of entries to return on each page. Default value: 10.

 |
|TaskId|String|No|a1ecd34a-8157-44d9-b060-14950837\*\*\*\*|The ID of the site monitoring task.

 |
|TaskType|String|No|HTTP|The protocol of the site monitoring task.

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|Code|String|200|The status code. A value of 200 indicates that the call was successful.

 |
|Message|String|successful|The error message.

 |
|PageNumber|Integer|1|The number of the page that was returned.

 |
|PageSize|Integer|10|The number of entries that were returned on each page. Default value: 10.

 |
|RequestId|String|68192f5d-0d45-4b98-9724-892813f86c71|The ID of the request.

 |
|SiteMonitors| | |The list of the site monitoring tasks that were queried.

 |
|└Address|String|http://www.aliyun.com|The URL or IP address monitored by the site monitoring task.

 |
|└CreateTime|String|2019-03-02 09:02:51|The time when the site monitoring task was created.

 |
|└Interval|String|1|The monitoring interval of the site monitoring task. Unit: minutes

 |
|└OptionsJson|JSON|\{"time\_out":5000\}|The extended options of the protocol of the site monitoring task. The options vary according to the protocol.

 |
|└TaskId|String|a1ecd34a-8127-44d9-b060-14950837\*\*\*\*|The ID of the site monitoring task.

 |
|└TaskName|String|Alibaba Cloud official website monitoring|The name of the site monitoring task.

 |
|└TaskState|String|1|The status of the site monitoring task. A value of 1 indicates that the site monitoring task is enabled. A value of 2 indicates that the site monitoring task is disabled.

 |
|└TaskType|String|HTTP|The protocol of the site monitoring task. Currently, site monitoring supports the following protocols: HTTP, Ping, TCP, UDP, DNS, SMTP, POP3, and FTP.

 |
|└UpdateTime|String|2019-03-03 14:16:34|The time when the site monitoring task was updated.

 |
|Success|String|true|Indicates whether the call was successful.

 |
|TotalCount|Integer|10|The total number of site monitoring tasks that were returned.

 |

## Examples {#demo .section}

Sample request

``` {#request_demo}

http(s)://[Endpoint]/? Action=DescribeSiteMonitorList
&<Common request parameters>

```

Sample success response

`XML` format

``` {#xml_return_success_demo}
<DescribeSiteMonitorListResponse>
  <Message>successful</Message>
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
      <TaskName>Alibaba Cloud official website monitoring</TaskName>
      <TaskState>2</TaskState>
      <TaskType>HTTP</TaskType>
    </SiteMonitor>
  </SiteMonitors>
  <Success>true</Success>
  <Code>200</Code>
</DescribeSiteMonitorListResponse>

```

`JSON` format

``` {#json_return_success_demo}
{
	"Message":"successful",
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
				"TaskName":"Alibaba Cloud official website monitoring"
			}
		]
	},
	"Code":"200"
}
```

## Error codes { .section}

[View error codes.](https://error-center.aliyun.com/status/product/Cms)

