# GPU monitoring {#concept_ysn_byq_32b .concept}

You can query GPU monitoring data either by using the CloudMonitor console or by calling APIs.

## Metrics {#section_xmb_mtz_pgb .section}

The metrics for GPU monitoring are based on three dimensions: GPU, instance, and application group.

-   **GPU-dimension metrics**

    GPU-dimension metrics measure monitoring data on a per GPU basis. The following table lists GPU-dimension metrics.

    |Metric|Unit|Description|Dimensions|
    |:-----|:---|:----------|:---------|
    |gpu\_memory\_freespace|Byte|The free memory of a GPU|instanceId, gpuId|
    |gpu\_memory\_totalspace|Byte|The total memory of a GPU|instanceId, gpuId|
    |gpu\_memory\_usedspace|Byte|The memory in use of a CPU|instanceId, gpuId|
    |gpu\_gpu\_usedutilization|%|The usage of a GPU|instanceId, gpuId|
    |gpu\_encoder\_utilization|%|The usage of an encoder with GPU support|instanceId, gpuId|
    |gpu\_decoder\_utilization|%|The usage of an decoder with GPU support|instanceId, gpuId|
    |gpu\_gpu\_temperature|℃|The temperature of a GPU|instanceId, gpuId|
    |gpu\_power\_readings\_power\_draw|W|The power of a GPU|instanceId, gpuId|
    |gpu\_memory\_freeutilization|%|The percentage of the free memory of a GPU|instanceId, gpuId|
    |gpu\_memory\_useutilization|%|The percentage of the memory in use of a GPU|instanceId, gpuId|

-   **Instance-dimension metrics**

    Instance-dimension metrics measure the maximum, minimum, or average value of multiple GPUs on a per instance basis, so that you can query the overall resource usage at the instance level.

    |Metric|Unit|Description|Dimension|
    |:-----|:---|:----------|:--------|
    |instance\_gpu\_decoder\_utilization|%|GPU decoder usage at the instance level|instanceId|
    |instance\_gpu\_encoder\_utilization|%|GPU encoder usage at the instance level|instanceId|
    |instance\_gpu\_gpu\_temperature|℃|GPU temperature at the instance level|instanceId|
    |instance\_gpu\_gpu\_usedutilization|%|GPU usage at the instance level|instanceId|
    |instance\_gpu\_memory\_freespace|Byte|Free GPU memory at the instance level|instanceId|
    |instance\_gpu\_memory\_freeutilization|%|The percentage of free GPU memory at the instance level|instanceId|
    |instance\_gpu\_memory\_totalspace|Byte|GPU memory at the instance level|instanceId|
    |instance\_gpu\_memory\_usedspace|Byte|GPU memory in use at the instance level|instanceId|
    |instance\_gpu\_memory\_usedutilization|%|GPU memory usage at the instance level|instanceId|
    |instance\_gpu\_power\_readings\_power\_draw|W|GPU power at the instance level|instanceId|

-   **Group-dimension metrics**

    Group-dimension metrics measure the maximum, minimum, or average value of multiple instances on a per group basis, so that you can query the overall resource usage at the group level.

    |Metric|Unit|Description|Dimension|
    |:-----|:---|:----------|:--------|
    |group\_gpu\_decoder\_utilization|%|GPU decoder usage at the application group level|groupId|
    |group\_gpu\_encoder\_utilization|%|GPU encoder usage at the application group level|groupId|
    |group\_gpu\_gpu\_temperature|℃|GPU temperature at the application group level|groupId|
    |group\_gpu\_gpu\_usedutilization|%|GPU usage at the application group level|groupId|
    |group\_gpu\_memory\_freespace|Byte|Free GPU memory at the application group level|groupId|
    |group\_gpu\_memory\_freeutilization|%|The percentage of free GPU memory at the application group level|groupId|
    |group\_gpu\_memory\_totalspace|Byte|GPU memory at the application group level|groupId|
    |group\_gpu\_memory\_usedspace|Byte|GPU memory in use at the application group level|groupId|
    |group\_gpu\_memory\_usedutilization|%|GPU memory usage at the application group level|groupId|
    |group\_gpu\_power\_readings\_power\_draw|W|GPU power at the application group level|groupId|


## Query GPU monitoring data in the console {#section_hcc_4mr_32b .section}

After you have purchased an ECS instance of the GPU Compute type, you need to install the [GPU driver](../../../../../reseller.en-US/User Guide/Instances/Create an instance/Create a compute optimized instance with GPUs.md#) and a CloudMonitor agent to be able to view and configure GPU monitoring charts and set alarm rules.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/15305/15508163976845_en-US.png)

**View monitoring charts**

1.  Log on to the [CloudMonitor console](https://partners-intl.console.aliyun.com/#/cms).
2.  In the left-side navigation pane, click **Host Monitoring**.
3.  On the **Instances** tab page, find the target instance and click the instance name.
4.  Click the **GPUMonitor** tab to view the GPU monitoring charts.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/15305/15508163976696_en-US.png)


**Configure monitoring charts**

1.  Log on to the [CloudMonitor console](https://partners-intl.console.aliyun.com/#/cms).
2.  In the left-side navigation pane, choose **Dashboard** \> **Custom Dashboard**.
3.  In the upper-right corner, click **Create Dashboard**.
4.  In the displayed dialog box, enter a name for the dashboard and click **Create**.
5.  On the displayed page of the created dashboard, click **Add View**.
6.  On the **Add View** page, select the chart type, and then select the metrics.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/15305/15508163976698_en-US.png)

7.  Click **Save**.

**Set alarm rules**

We recommended that you use alarm templates to set alarm rules for new GPU metrics in batches. You can create alarm templates for the GPU metrics and then apply the templates to related application groups. For more information, see [Create an alarm template](../../../../../reseller.en-US/Best Practices/Create an alarm template.md#).

## Query GPU monitoring data through APIs {#section_iq4_gnr_32b .section}

-   For more information about how to call APIs to query GUP monitoring data, see [QueryMetricList](../../../../../reseller.en-US/API Reference/Query monitoring data/QueryMetricList.md#).
-   Parameter description: The `Project` parameter should be set to `acs_ecs_dashboard`. For the values of `Metric` and `Dimensions`, see the GPU metrics in the preceding tables.

