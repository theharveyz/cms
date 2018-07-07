# Query GPU monitoring data {#concept_ysn_byq_32b .concept}

You can query GPU monitoring data in two ways: CloudMonitor console and API

## **Query GPU monitoring data through the CloudMonitor console** {#section_hcc_4mr_32b .section}

After purchasing an instance of the GPU Compute type for ECS, you only need to install the GPU drive and the 1.2.28 version of the CloudMonitor plug-in before you can view and configure GPU-related metric charts, or set alarm rules.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/15305/6845_en-US.png)

## View metric charts {#section_oyk_4dr_32b .section}

To view GPU-related metric charts, follow these steps:

1.  Log on to the [CloudMonitor console](https://cloudmonitor.console.aliyun.com).
2.  Click **Host Monitoring** in the navigation bar.
3.  Query GPU-related metric charts on the **GPUMonitor**page, as shown in the following figure.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/15305/6696_zh-CN.png)

## Configure metric charts {#section_hzg_pdr_32b .section}

1.  Log on to the [CloudMonitor console](https://cloudmonitor.console.aliyun.com).
2.  Click **Dashboard** in the navigation bar.
3.  Click **Create Dashboard** on the **Dashboard** page.
4.  In the pop-up dialog box, enter the name of the new dashboard and click **Create**.
5.  On the refreshed page, click **Add View**.
6.  On the **Add View** page, select the chart type you want, and then select **Metrics**, as shown in the following figure.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/15305/6698_zh-CN.png)

7.  Select the metrics you want from the drop-down menu. The following figure uses the instance-dimension GPU temperature as an example.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/15305/6699_zh-CN.png)

## Set alarm rules {#section_mxb_qdr_32b .section}

The method of adding alarm rules for new GPU metrics is the same as that for other ECS metrics. It is recommended that you add GPU alarm rules in batches by applying the template to groups after creating the template. For details, see [Alarm template](https://help.aliyun.com/document_detail/56012.html).

## Metrics description {#section_iyy_qjr_32b .section}

GPU-related metrics are classified into three dimensions: GPU, instance, and group.

## GPU-dimension metrics {#section_rcc_ckr_32b .section}

GPU-dimension metrics measure monitoring data on a per GPU basis. The following table lists GPU-dimension metrics.

|Metric Name|Unit|Description|Dimensions|
|:----------|:---|:----------|:---------|
|gpu\_memory\_freespace|Bytes|GPU-dimension memory free space|instanceId,gpuId|
|gpu\_memory\_totalspace|Bytes|GPU-dimension memory total space|instanceId,gpuId|
|gpu\_memory\_usedspace|Bytes|GPU-dimension memory used space|instanceId,gpuId|
|gpu\_gpu\_usedutilization|%|GPU-dimension GPU utilization|instanceId,gpuId|
|gpu\_encoder\_utilization|%|GPU-dimension encoder utilization|instanceId,gpuId|
|gpu\_decoder\_utilization|%|GPU-dimension decoder utilization|instanceId,gpuId|
|gpu\_gpu\_temperature|℃|GPU-dimension GPU temperature|instanceId,gpuId|
|gpu\_power\_readings\_power\_draw|W|GPU-dimension GPU power|instanceId,gpuId|
|gpu\_memory\_freeutilization|%|GPU-dimension memory idle rate|instanceId,gpuId|
|gpu\_memory\_useutilization|%|GPU-dimension memory utilization|instanceId,gpuId|

## Instance-dimension metrics {#section_zm3_tkr_32b .section}

Instance-dimension metrics measure the maximum, minimum, or average value of multiple GPUs on a per instance basis, so that you can query the overall resource usage at the instance level.

|Metric Name|Unit|Description|Dimensions|
|:----------|:---|:----------|:---------|
|instance\_gpu\_decoder\_utilization|%|Instance-dimension GPU decoder utilization|instanceId|
|instance\_gpu\_encoder\_utilization|%|Instance-dimension GPU encoder utilization|instanceId|
|instance\_gpu\_gpu\_temperature|℃|Instance-dimension GPU temperature|instanceId|
|instance\_gpu\_gpu\_usedutilization|%|Instance-dimension GPU utilization|instanceId|
|instance\_gpu\_memory\_freespace|Bytes|Instance-dimension GPU memory free space|instanceId|
|instance\_gpu\_memory\_freeutilization|%|Instance-dimension GPU memory idle rate|instanceId|
|instance\_gpu\_memory\_totalspace|Bytes|Instance-dimension GPU memory total space|instanceId|
|instance\_gpu\_memory\_usedspace|Bytes|Instance-dimension GPU memory used space|instanceId|
|instance\_gpu\_memory\_usedutilization|%|Instance-dimension GPU memory utilization|instanceId|
|instance\_gpu\_power\_readings\_power\_draw|W|Instance-dimension GPU power|instanceId|

## Group-dimension metrics {#section_phj_nlr_32b .section}

Group-dimension metrics measure the maximum, minimum, or average value of multiple instances on a per group basis, so that you can query the overall resource usage at the group level.

|Metric Name|Unit|Description|Dimensions|
|:----------|:---|:----------|:---------|
|group\_gpu\_decoder\_utilization|%|Group-dimension GPU decoder utilization|groupId|
|group\_gpu\_encoder\_utilization|%|Group-dimension GPU encoder utilization|groupId|
|group\_gpu\_gpu\_temperature|℃|Group-dimension GPU temperature|groupId|
|group\_gpu\_gpu\_usedutilization|%|Group-dimension GPU utilization|groupId|
|group\_gpu\_memory\_freespace|Bytes|Group-dimension GPU memory free space|groupId|
|group\_gpu\_memory\_freeutilization|%|Group-dimension GPU memory idle rate|groupId|
|group\_gpu\_memory\_totalspace|Bytes|Group-dimension GPU memory total space|groupId|
|group\_gpu\_memory\_usedspace|Bytes|Group-dimension GPU memory used space|groupId|
|group\_gpu\_memory\_usedutilization|%|Group-dimension GPU memory utilization|groupId|
|group\_gpu\_power\_readings\_power\_draw|W|Group-dimension GPU power|groupId|

## Query GPU monitoring data through the API {#section_iq4_gnr_32b .section}

-   See [**QueryMetricList**](https://help.aliyun.com/document_detail/51936.html).
-   Parameter description: The "Project" parameter should be set to "acs\_ecs\_dashboard." For the values of the "Metric" and "Dimensions" parameters, see the GPU metrics in the preceding tables.

