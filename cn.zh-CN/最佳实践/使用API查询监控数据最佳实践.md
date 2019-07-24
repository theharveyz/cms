# 使用API查询监控数据最佳实践 {#concept_axh_33l_ggb .concept}

本文为您介绍如何使用API查询阿里云各产品监控数据。

## 背景信息 {#section_y4p_4jl_ggb .section}

大型企业内部通常有自建的运维监控系统，上云过程中会面临如何将云资源监控数据与已有系统集成的问题。下面本文将为您介绍如何通过云监控接口查询各产品监控数据，从而将阿里云的监控数据与现有系统进行集成。

## 使用API查询监控数据的准备工作 {#section_rwj_5ps_ggb .section}

在使用API查询监控数据之前，我们先了解一下云监控提供的关于指标类监控数据查询的三类接口：

-   查询产品列表接口：查询云监控支持哪些产品的监控项，详情请参见[DescribeProjectMeta](../../../../cn.zh-CN/API参考/云产品时序指标类监控数据/DescribeProjectMeta.md#)。
-   查询监控项列表接口：查询对应产品可以获取哪些监控项，详情请参见[DescribeMetricMetaList](../../../../cn.zh-CN/API参考/云产品时序指标类监控数据/DescribeMetricMetaList.md#)。
-   查询监控数据接口：根据产品信息和监控项信息，查询具体的监控数据，详情请参见[DescribeMetricList](../../../../cn.zh-CN/API参考/云产品时序指标类监控数据/DescribeMetricList.md#)和[DescribeMetricLast](../../../../cn.zh-CN/API参考/云产品时序指标类监控数据/DescribeMetricLast.md#)。

## 使用API查询监控数据的实施步骤 {#section_qcp_sjl_ggb .section}

注意事项

-   DescribeMetricList和DescribeMetricLast接口支持批量获取用户下所有实例的某个指标的数据。如果想获取多个指标，可以多个线程获取多个指标，也可以单线程循环获取多个指标。
-   DescribeMetricList接口支持的最大QPS是20，DescribeMetricLast接口的最大QPS是30。
-   DescribeMetricLast接口适用于需要定时全量拉取所有最新数据的情况。时间窗口自动往前滑动，每个周期都取一条最新数据。
-   监控数据会有一定的延迟，且各产品的监控数据的延迟情况不太一样，所以建议您使用DescribeMetricLast查询最新数据时，时间窗口放宽到5-10分钟。
-   秒级精度的数据保存7天，分钟级精度的数据保存31天。
-   如果您需要查询云账号所有实例的数据，则不需要指定Dimensions。

使用API查询监控数据的实战案例

下面本文将通过Demo演示，介绍如何使用DescribeMetricLast接口查询最新的监控数据，使用DescribeMetricList接口查询指定时间段内的监控数据。

``` {#codeblock_lt7_uyv_77k .language-java}
import com.aliyuncs.DefaultAcsClient;
import com.aliyuncs.IAcsClient;
import com.aliyuncs.exceptions.ClientException;
import com.aliyuncs.exceptions.ServerException;
import com.aliyuncs.profile.DefaultProfile;
import com.google.gson.Gson;
import java.util.*;
import com.aliyuncs.cms.model.v20190101.*;

/**
 * 使用DescribeMetricList接口可以查询指定时间段内，指定实例的监控数据。
 * 该查询允许指定多个实例进行批量查询。
 * 如果需要获取多个实例一段时间内的监控数据，可以在查询时指定多个实例，每次最多10个实例。
 * 查询一段时间内的监控数据
 */
public class DescribeMetricList {

    public static void main(String[] args) {
        DefaultProfile profile = DefaultProfile.getProfile("cn-hangzhou", "<accessKeyId>", "<accessSecret>");
        IAcsClient client = new DefaultAcsClient(profile);

        DescribeMetricListRequest request = new DescribeMetricListRequest();
        //namespace和metric通过DescribeMetricMetaList和DescribeProjectMeta获取
        request.setNamespace("acs_ecs_dashboard");
        request.setMetricName("cpu_total");
        //period表示要获取60s精度的监控数据。period根据每个metric有不同的定义，大部分metric都会有60s的period。
        request.setPeriod("60");
        //本次查询的分页长度，每次查询最多返回1000条数据。
        request.setLength("100");
        //查询数据的开始时间
        request.setStartTime("2019-07-22 11:00:00");
        //查询数据的结束时间
        request.setEndTime("2019-07-22 12:00:00");
        //查询的关联dimension过滤，即可以是一个JSONArray，也可以是一个JSONObject
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
import com.aliyuncs.cms.model.v20190101.*;

/**
 * 取得最后一条监控数据
 **/
public class DescribeMetricLast {

    public static void main(String[] args) {
        DefaultProfile profile = DefaultProfile.getProfile("cn-hangzhou", "<accessKeyId>", "<accessSecret>");
        IAcsClient client = new DefaultAcsClient(profile);

        DescribeMetricLastRequest request = new DescribeMetricLastRequest();

         //namespace和metric通过DescribeMetricMetaList和DescribeProjectMeta获取        
        request.setNamespace("acs_ecs_dashboard");
        request.setMetricName("cpu_total");
        //查询的关联dimension过滤，即可以是一个JSONArray，也可以是一个JSONObject
        request.setDimensions("[{\"instanceId\":\"i-8vb6p*****\"}]");
        //本次查询的分页长度，每次查询最多返回100条数据。
        request.setLength("1000");
        //查询数据的开始时间
        request.setStartTime("2019-07-22 11:00:00");
        //查询数据的结束时间
        request.setEndTime("2019-07-22 12:00:00");
        request.setPeriod("60");

        try {
            DescribeMetricLastResponse response = client.getAcsResponse(request);
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

