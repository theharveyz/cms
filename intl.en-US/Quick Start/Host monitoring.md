# Host monitoring {#concept_jf2_pnb_5db .concept}

## Application scenarios {#section_u41_hdc_5db .section}

-   **Hybrid cloud monitoring solution**

    CloudMonitor uses an agent to collect server monitoring data. You can install the agent on a non-ECS server to perform basic monitoring check both locally and on the cloud.

-   **Enterprise-level monitoring solution**

    Host monitoring provides an application grouping feature with which you can allocate servers in different regions to the same group for business-based server management. In addition, host monitoring provides group-based alarm management. You can configure one alarm rule for the entire group greatly improving O&M efficiency and your overall management experience.


## Features {#section_fbb_5dc_5db .section}

-   Diverse metrics

    Once a CloudMonitor agent is installed, you can use more than 30 metrics. For details, see [Host monitoring metrics](../../../../../reseller.en-US/User Guide/Host monitoring/Host monitoring metrics.md#).

-   Refined collection frequency

    Key metrics are collected every second. All the metrics are reported at a 15-second interval, which is the minimum interval between the data points in a chart.

-   Business-level process monitoring

    The host monitoring service collects statistical data from the CPU and memory usage of active processes and the number of opened files, helping you gain insight into server resource allocation. For details, see [Process monitoring](../../../../../reseller.en-US/User Guide/Host monitoring/Process monitoring.md#).

-   Application groups

    You can manage servers by group across regions and set alarm rules according to group, greatly reducing monitoring management costs.

-   Alarm service

    You can set alarm rules for the metrics. The following alarm notification methods are supported: telephone alarms, messages, email IDs, TradeManager, and DingTalk Robot.


## Procedure {#section_d12_ydc_5db .section}

1.  Log on to the [CloudMonitor Console](https://partners-intl.console.aliyun.com/#/cms).
2.  In the left-side navigation pane, click **Host Monitoring**. The Host Monitoring page is displayed.
3.  Click **Click to install** in the instance list. Alternatively, click **Aliyun ECS install** or **Not Aliyun ecs install** and install the agent manually as prompted.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6126/155290356813786_en-US.png)

4.  Wait 1 to 3 minutes and click **Monitoring Charts** to view the monitoring data.

