# 使用API查询监控数据最佳实践 {#concept_axh_33l_ggb .concept}

## 背景信息 {#section_y4p_4jl_ggb .section}

大型企业内部通常有自建的运维监控系统，上云过程中会面临如何将云资源监控数据与已有系统集成的问题。本文将为您介绍如何通过云监控接口查询各产品监控数据，从而将阿里云的监控数据与现有系统进行集成。

## 使用API查询监控数据的准备工作 {#section_rwj_5ps_ggb .section}

在使用API查询监控数据之前，我们先了解一下云监控提供的关于指标类监控数据查询的三类接口：

-   查询产品列表接口：查询云监控支持哪些产品的监控项，详情请参见[../../../../dita-oss-bucket/SP\_64/DNCMS11853671/ZH-CN\_TP\_69876.md\#](../../../../intl.zh-CN/API参考/云产品时序指标类监控数据/QueryProjectMeta.md#)。
-   查询监控项列表接口：查询对应产品可以获取哪些监控项，详情请参见[../../../../dita-oss-bucket/SP\_64/DNCMS11853671/ZH-CN\_TP\_67480.md\#](../../../../intl.zh-CN/API参考/云产品时序指标类监控数据/DescribeMetricMetaList.md#)。
-   查询监控数据接口：根据产品信息和监控项信息，查询具体的监控数据，详情请参见[../../../../dita-oss-bucket/SP\_64/DNCMS11853671/ZH-CN\_TP\_14268.md\#](../../../../intl.zh-CN/API参考/云产品时序指标类监控数据/DescribeMetricList.md#)和[../../../../dita-oss-bucket/SP\_64/DNCMS11853671/ZH-CN\_TP\_14267.md\#](../../../../intl.zh-CN/API参考/云产品时序指标类监控数据/DescribeMetricLast.md#)。

## 使用API查询监控数据的实施步骤 {#section_qcp_sjl_ggb .section}

**注意事项**

-   QueryMetricList和QueryMetricLast接口支持批量获取用户下所有实例的某个指标的数据。如果想获取多个指标，可以多个线程获取多个指标，也可以单线程循环获取多个指标。
-   QueryMetricList接口支持的最大QPS是20，QueryMetricLast接口的最大QPS是30。
-   QueryMetricLast接口适用于需要定时全量拉取所有最新数据的情况。时间窗口自动往前滑动，每个周期都取一条最新数据。
-   监控数据会有一定的延迟，且各产品的监控数据的延迟情况不太一样，所以建议您使用QueryMetricLast查询最新数据时，时间窗口放宽到5-10分钟。
-   秒级精度的数据保存7天，分钟级精度的数据保存31天。
-   如果您需要查询云账号所有实例的数据，则不需要指定Dimensions。

**使用API查询监控数据的实战案例**

下面本文将通过Demo演示，介绍如何使用QueryMetricLast接口查询最新的监控数据，使用QueryMetricList接口查询指定时间段内的监控数据。

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
 ​      //关于如何获取ak，参考：https://yq.aliyun.com/articles/608581
    cmsClient, _ := cms.NewClientWithAccessKey(
        "<指定region，如果不确定，可以填入cn-hangzhou>",                    // 地域ID
        "<your access key id>",               // Access Key ID
        "<your Access Key Secret>") // Access Key Secret

    //获取给定时间范围内的给定实例的最后一条也就是最新一条监控数据。
    request := cms.CreateQueryMetricLastRequest()
    //project和metric通过QueryProjectMeta和QueryMetricMeta获取
    request.Metric = "cpu_total"
    //period表示要获取60s精度的监控数据。period根据每个metric有不同的定义，大部分metric都会有60s的period
    request.Period = "60"
    //查询数据的开始时间
    request.StartTime = "2018-11-29 11:00:00"
    //查询数据的结束时间
    request.EndTime = "2018-11-29 12:00:00"
    //本次查询的分页长度，每次查询最多返回1000条数据。
    request.Length = "100"
    //分页的cursor，如果返回结果数据里有cursor != "",表示数据还有下一页。需要通过cursor来查询下一页。
    request.Cursor = ""

    t.Log("start query")

    for {
        response, _ := cmsClient.QueryMetricLast(request)
        //response code
        if response.Code != "200" || !response.IsSuccess() {
            t.Fatalf("code:%s,success:%v,msg:%s, httpstatus:%d, response:%v\n", response.Code, response.IsSuccess(), response.Message, response.GetHttpStatus(), response)
        }

        var datapoints []map[string]interface{}
        err := json.Unmarshal([]byte(response.Datapoints), &datapoints)
        if err != nil {
            t.Fatal(err)
        }

        t.Logf("batch count %d\n", len(datapoints))
        for _, v := range datapoints {
            t.Log(v)
        }

        //如果返回的结果中cursor==""，表示没有下一页了。跳出循环，结束本轮查询
        if response.Cursor == "" {
            t.Log("循环结束")
            break
        }

        //如果有下一页，将cursor作为查询下一页的条件，赋值给request
        request.Cursor = response.Cursor
        t.Logf("cursor:%s\n", response.Cursor)
    }

    t.Log("finished")
}

//TestBatchQueryMultiInstance
//使用QueryMetricList接口可以查询指定时间段内，指定实例的监控数据。
//该查询允许指定多个实例进行批量查询。
//如果需要获取多个实例一段时间内的监控数据，可以在查询时指定多个实例，每次最多10个实例。

func TestBatchQueryMultiInstance(t *testing.T) {
 ​      //关于如何获取ak，参考：https://yq.aliyun.com/articles/608581
    cmsClient, _ := cms.NewClientWithAccessKey(
        "<指定region，如果不确定，可以填入cn-hangzhou>",                    // 地域ID
        "<your access key id>",               // Access Key ID
        "<your Access Key Secret>") // Access Key Secret

    //查询指定时间段内，指定实例的监控数据。
    request := cms.CreateQueryMetricListRequest()
   //project和metric通过QueryProjectMeta和QueryMetricMeta获取
    request.Project = "acs_ecs_dashboard"
    request.Metric = "cpu_total"
   //period表示要获取60s精度的监控数据。period根据每个metric有不同的定义，大部分metric都会有60s的period。
    //查询数据的开始时间
    request.StartTime = "2018-11-25 11:00:00"
    //查询数据的结束时间
    request.EndTime = "2018-11-29 12:00:00"
    //本次查询的分页长度，每次查询最多返回1000条数据。
    request.Length = "10"
    request.Dimensions = "[{'instanceId':'AY140613113321409088'},{'instanceId':'AY14061311320829774f'},{'instanceId':'AY14061311330190512d'}]"
    //分页的cursor，如果返回结果数据里有cursor != "",表示数据还有下一页。需要通过cursor来查询下一页。
    request.Cursor = ""

    t.Log("start query")

    for {
        response, _ := cmsClient.QueryMetricList(request)
        //response code
        if response.Code != "200" || !response.IsSuccess() {
            t.Fatalf("code:%s,success:%v,msg:%s, httpstatus:%d, response:%v\n", response.Code, response.IsSuccess(), response.Message, response.GetHttpStatus(), response)
        }

        var datapoints []map[string]interface{}
        err := json.Unmarshal([]byte(response.Datapoints), &datapoints)
        if err != nil {
            t.Fatal(err)
        }

        t.Logf("batch count %d\n", len(datapoints))
        for _, v := range datapoints {
            t.Log(v)
        }

        //如果返回的结果中cursor==""，表示没有下一页了。跳出循环，结束本轮查询
        if response.Cursor == "" {
            t.Log("循环结束")
            break
        }

        //如果有下一页，查询下一页的条件，赋值给request
        request.Cursor = response.Cursor
        t.Logf("--------分页cursor:%s\n", response.Cursor)
    }

    t.Log("finished")
}

```

