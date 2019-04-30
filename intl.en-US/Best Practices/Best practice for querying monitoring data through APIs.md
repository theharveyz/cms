# Best practice for querying monitoring data through APIs {#concept_axh_33l_ggb .concept}

## Background information {#section_y4p_4jl_ggb .section}

Large-sized enterprises typically have their own O&M systems. When moving businesses to the cloud, these enterprises must integrate the cloud resource monitoring data with their existing systems. This topic describes how to use CloudMonitor APIs to query the monitoring data of various services and integrate Apsara Stack monitoring data into your existing systems.

## Prerequisites {#section_rwj_5ps_ggb .section}

Before you query monitoring data through APIs, we recommend that you learn about the three types of APIs provided by CloudMonitor to query monitoring data:

-   QueryProjectMeta: queries which services can be monitored by CloudMonitor. For more information, see [../../../../dita-oss-bucket/SP\_64/DNCMS11853671/EN-US\_TP\_69876.md\#](../../../../reseller.en-US/API Reference/Query monitoring data/QueryProjectMeta.md#).
-   QueryMetricMeta: queries which metrics are available for a monitored service. For more information, see [../../../../dita-oss-bucket/SP\_64/DNCMS11853671/EN-US\_TP\_67480.md\#](../../../../reseller.en-US/API Reference/Query monitoring data/QueryMetricMeta.md#).
-   QueryMetricList and QueryMetricLast: query monitoring data by service and metric. For more information, see [../../../../dita-oss-bucket/SP\_64/DNCMS11853671/EN-US\_TP\_14268.md\#](../../../../reseller.en-US/API Reference/Query monitoring data/QueryMetricList.md#) and [../../../../dita-oss-bucket/SP\_64/DNCMS11853671/EN-US\_TP\_14267.md\#](../../../../reseller.en-US/API Reference/Query monitoring data/QueryMetricLast.md#).

## Procedure {#section_qcp_sjl_ggb .section}

**Precautions**

-   QueryMetricList and QueryMetricLast allow you to query data for a certain metric for all your instances. To query data for multiple metrics, you can create multiple threads, or create a single thread to cyclically obtain data of different metrics.
-   QueryMetricList supports up to 20 queries per second \(QPS\) and QueryMetricLast supports up to 30 QPS.
-   QueryMetricLast is applicable to scenarios where you need to regularly obtain the most recent monitoring data. The time window automatically slides forward. The latest data is obtained in each period.
-   There may be a gap between the occurrence of an event and the time when it is monitored. The gap varies with service. We recommend that you extend the time window to 5 to 10 minutes when using QueryMetricLast to query the latest data.
-   Data that is obtained every few seconds is stored for 7 days. Data that is obtained every few minutes is stored for 31 days.
-   You do not need to specify Dimensions to query the data of all your instances.

**Case study**

The following example demonstrates how to use QueryMetricLast to query the latest monitoring data and use QueryMetricList to query the monitoring data in a specified time range.

```
undefined
package main

import (
    "encoding/json"
    "testing"

    "github.com/aliyun/alibaba-cloud-sdk-go/services/cms"
)

//TestQueryMetricLast

func TestQueryMetricLast(t *testing.T) {
 ​      //For more information about how to obtain the AccessKey pair, see https://yq.aliyun.com/articles/608581.
    cmsClient, _ := cms.NewClientWithAccessKey(
        "<Specify the region. If you are not sure, enter cn-hangzhou>",                    //Region ID
        "<your access key id>",               //AccessKey ID
        "<your Access Key Secret>") //AccessKey Secret

    //Obtain the latest monitoring data for the specified instance in the specified time range.
    request := cms.CreateQueryMetricLastRequest()
    //Use QueryProjectMeta and QueryMetricMeta to obtain project and metric.
    request.Metric = "cpu_total"
    //Period is set to 60, indicating that monitoring data is obtained every 60 seconds. The value of period varies with metric. Most metrics are polled at a 60-second period.
    request.Period = "60"
    //The start time of query data
    request.StartTime = "2018-11-29 11:00:00"
    //The end time of query data
    request.EndTime = "2018-11-29 12:00:00"
    //The number of response data records displayed per page for this query. Up to 1,000 data records can be returned for each query.
    request.Length = "100"
    //The page cursor. If the returned result contains cursor != "", the current page is not the last page. You must use cursors to query the next page.
    request.Cursor = ""

    t.Log("start query")

    for {
        response, _ := cmsClient.QueryMetricLast(request)
        //response code
        if response.Code ! = "200" || ! response.IsSuccess() {
            t.Fatalf("code:%s,success:%v,msg:%s, httpstatus:%d, response:%v\n", response.Code, response.IsSuccess(), response.Message, response.GetHttpStatus(), response)
        }

        var datapoints []map[string]interface{}
        err := json.Unmarshal([]byte(response.Datapoints), &datapoints)
        if err ! = nil {
            t.Fatal(err)
        }

        t.Logf("batch count %d\n", len(datapoints))
        for _, v := range datapoints {
            t.Log(v)
        }

        //If the returned result contains cursor=="", the current page is the last page. Exit the loop and end this round of query.
        if response.Cursor == "" {
            t.Log("end of loop")
            break
        }

        //If there are more pages, assign the cursor as the query condition for the next page in the next request.
        request.Cursor = response.Cursor
        t.Logf("cursor:%s\n", response.Cursor)
    }

    t.Log("finished")
}

//TestBatchQueryMultiInstance
//You can use QueryMetricList to query the monitoring data of a specified instance in a specified time range.
//You can specify multiple instances for batch query.
//To obtain the monitoring data for multiple instances over a specified time range, you can specify multiple instances for a query. Up to 10 instances can be specified at a time.

func TestBatchQueryMultiInstance(t *testing.T) {
 //For more information about how to obtain the AccessKey pair, see https://yq.aliyun.com/articles/608581
    cmsClient, _ := cms.NewClientWithAccessKey(
        "<Specify the region. If you are not sure, enter cn-hangzhou>",                    //Region ID
        "<your access key id>",               //AccessKey ID 
        "<your Access Key Secret>") //AccessKey Secret 

    //Query the monitoring data for the specified instance over the specified time range.
    request := cms.CreateQueryMetricListRequest()
   //Use QueryProjectMeta and QueryMetricMeta to obtain project and metric.
    request.Project = "acs_ecs_dashboard"
    request.Metric = "cpu_total"
   //Period is set to 60, indicating that monitoring data is obtained every 60 seconds. The value of period varies with metric. Most metrics are polled at a 60-second period.
    //The start time of query data
    request.StartTime = "2018-11-25 11:00:00"
    //The end time of query data
    request.EndTime = "2018-11-29 12:00:00"
    //The number of response data records displayed per page for this query. Up to 1,000 data records can be returned for each query.
    request.Length = "10"
    request.Dimensions = "[{'instanceId':'AY140613113321409088'},{'instanceId':'AY14061311320829774f'},{'instanceId':'AY14061311330190512d'}]"
    //The page cursor. If the returned result contains cursor != "", the current page is not the last page. You must use cursors to query the next page.
    request.Cursor = ""

    t.Log("start query")

    for {
        response, _ := cmsClient.QueryMetricList(request)
        //Response code
        if response.Code ! = "200" || ! response.IsSuccess() {
            t.Fatalf("code:%s,success:%v,msg:%s, httpstatus:%d, response:%v\n", response.Code, response.IsSuccess(), response.Message, response.GetHttpStatus(), response)
        }

        var datapoints []map[string]interface{}
        err := json.Unmarshal([]byte(response.Datapoints), &datapoints)
        if err ! = nil {
            t.Fatal(err)
        }

        t.Logf("batch count %d\n", len(datapoints))
        for _, v := range datapoints {
            t.Log(v)
        }

        //If the returned result contains cursor=="", the current page is the last page. Exit the loop and end this round of query.
        if response.Cursor == "" {
            t.Log("end of loop")
            break
        }

        //If there are more pages, assign the cursor as the query condition for the next page in the next request.
        request.Cursor = response.Cursor
        t.Logf("cursor:%s\n", response.Cursor)
    }

    t.Log("finished")
}

```

