# Query monitoring data through API operations {#concept_axh_33l_ggb .concept}

This topic describes how to use API operations to query monitoring data of various Alibaba Cloud products.

## Background {#section_y4p_4jl_ggb .section}

Large enterprises typically have their own O&M and monitoring systems. When they migrate businesses to the cloud, these enterprises must integrate the cloud resource monitoring data with their existing systems. This topic describes how to use CloudMonitor API operations to query the monitoring data of various services and integrate Alibaba Cloud monitoring data with your existing systems.

## Preparations {#section_rwj_5ps_ggb .section}

Before you query monitoring data through API operations, familiarize yourself with the three types of operations provided by CloudMonitor:

-   Operations that query services: query services that can be monitored by CloudMonitor. For more information, see [DescribeProjectMeta](../../../../reseller.en-US/API Reference/Monitoring data on time series metrics of cloud services/DescribeProjectMeta.md#).
-   Operations that query metrics: query which metrics are available for a monitored service. For more information, see [DescribeMetricMetaList](../../../../reseller.en-US/API Reference/Monitoring data on time series metrics of cloud services/DescribeMetricMetaList.md#).
-   Operations that query data: query monitoring data based on services and metrics. For more information, see [DescribeMetricList](../../../../reseller.en-US/API Reference/Monitoring data on time series metrics of cloud services/DescribeMetricList.md#) and [DescribeMetricLast](../../../../reseller.en-US/API Reference/Monitoring data on time series metrics of cloud services/DescribeMetricLast.md#).

## Procedure {#section_qcp_sjl_ggb .section}

Notes

-   The DescribeMetricList and DescribeMetricLast operations allow you to query data of a specific metric for all your instances. You can create multiple threads or create a single thread in a loop to obtain multiple metrics.
-   DescribeMetricList supports a maximum of 20 queries per second \(QPS\) and DescribeMetricLast supports a maximum of 30 QPS.
-   DescribeMetricLast is applicable to scenarios where you need to obtain the most recent monitoring data at regular intervals. The time window automatically slides forward. For each period, the most recent record is retrieved.
-   The monitoring data may be prone to delay, which varies with different services. We recommend that you extend the time window by 5 to 10 minutes when using DescribeMetricLast to query the latest data.
-   Data that is obtained every few seconds is stored for 7 days, while data that is obtained every few minutes is stored for 31 days.
-   You do not need to specify the Dimensions parameter to query the aggregate data of all your instances.

Use case

The following example demonstrates how to use DescribeMetricLast to query the latest monitoring data and use DescribeMetricList to query the monitoring data in a specified time range.

``` {#codeblock_lt7_uyv_77k .language-java}
import com.aliyuncs.DefaultAcsClient;
import com.aliyuncs.IAcsClient;
import com.aliyuncs.exceptions.ClientException;
import com.aliyuncs.exceptions.ServerException;
import com.aliyuncs.profile.DefaultProfile;
import com.google.gson.Gson;
import java.util.*;
import com.aliyuncs.cms.model.v20190101. *;

/**
 * You can use the DescribeMetricList operation to query the monitoring data of a specified instance in a specified time range.
 * DescribeMetricList supports queries for multiple instances.
 * To obtain the monitoring data for multiple instances over a specified time range, you can specify multiple instances for the query. You can specify a maximum of 10 instances at a time.
 * Queries metric data over a period of time.
 */
public class DescribeMetricList {

    public static void main(String[] args) {
        DefaultProfile profile = DefaultProfile.getProfile("cn-hangzhou", "<accessKeyId>", "<accessSecret>");
        IAcsClient client = new DefaultAcsClient(profile);

        DescribeRegionsRequest request = new DescribeRegionsRequest();
        // The namespace and metrics can be obtained by calling the DescribeMetricMetaList and DescribeProjectMeta operations.
        request.setNamespace("acs_ecs_dashboard");
        request.setMetricName("cpu_total");
        // The Period parameter is set to 60, this specifies that monitoring data is obtained every 60 seconds. The value of period varies with metrics. The period of most metrics are set to 60 seconds by default.
        request.setPeriod("60");
        // The number of response data records displayed per page for this query. A maximum of 1,000 data records can be returned for each query.
        request.setLength("1000");
        // The start time of the query data.
        request.setStartTime("2019-07-22 11:00:00");
        // The end time of the query data.
        request.setEndTime("2019-07-22 12:00:00");
        // Set the Dimensions parameter for filtering, which can be a JSON array or a JSON object.
        request.setDimensions("[{\"instanceId\":\"i-8vb******\"}]");

        try {
            DescribeMetricListResponse response = client.getAcsResponse(request);
            System.out.println(new Gson().toJson(response));
        } catch (ServerException e) {
            e.printStackTrace();
        } catch (ClientException e) {
            System.out.println("ErrCode:" + e.getErrCode());
            System.out.println("ErrMsg:" + e.getErrMsg());
            System.out.println("RequestId:" + e.getRequestId());
        }

    }
}
				
```

``` {#codeblock_d7c_mqp_ynx .language-java}
import com.aliyuncs.DefaultAcsClient;
import com.aliyuncs.IAcsClient;
import com.aliyuncs.exceptions.ClientException;
import com.aliyuncs.exceptions.ServerException;
import com.aliyuncs.profile.DefaultProfile;
import com.google.gson.Gson;
import java.util.*;
import com.aliyuncs.cms.model.v20190101. *;

/**
 * Obtains the latest metric data.
 **/
public class DescribeMetricLast {

    public static void main(String[] args) {
        DefaultProfile profile = DefaultProfile.getProfile("cn-hangzhou", "<accessKeyId>", "<accessSecret>");
        IAcsClient client = new DefaultAcsClient(profile);

        DescribeMetricLastRequest request = new DescribeMetricLastRequest();

         // The namespace and metrics can be obtained by calling the DescribeMetricMetaList and DescribeProjectMeta operations.        
        request.setNamespace("acs_ecs_dashboard");
        request.setMetricName("cpu_total");
        // Set the Dimensions parameter for filtering, which can be a JSON array or a JSON object.
        request.setDimensions("[{\"instanceId\":\"i-8vb6p*****\"}]");
        // The number of response data records displayed per page for this query. A maximum of 1,000 data records can be returned for each query.
        request.setItemId("1000");
        // The start time of the query data.
        request.setStartTime("2019-07-22 11:00:00");
        // The end time of the query data.
        request.setEndTime("2019-07-22 12:00:00");
        request.setPeriod("60");

        try {
            DescribeRegionsResponse response = client.GetAcsResponse(request);
            System.out.println(new Gson().toJson(response));
        } catch (ServerException e) {
            e.printStackTrace();
        } catch (ClientException e) {
            System.out.println("ErrCode:" + e.getErrCode());
            System.out.println("ErrMsg:" + e.getErrMsg());
            System.out.println("RequestId:" + e.getRequestId());
        }

    }
}               
```

