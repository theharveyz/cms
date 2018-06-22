# Auto Scaling {#concept_oxw_1rd_zdb .concept}

CloudMonitor monitors multiple metrics, such as the minimum and maximum numbers of instances in an auto scaling group. It helps you monitor the status of instances in an auto scaling group and set alert policies for metrics. After you buy the auto scaling service, CloudMonitor will automatically collect data on the metrics listed above.

## Monitoring Services {#section_rbs_4td_zdb .section}

-   Monitoring items

    |Monitoring items|Dimensions|Unit|Minimum monitor Granularity|
    |:---------------|:---------|:---|:--------------------------|
    |Minimum number of instances|User dimension, elastic scaling group|Items|5 minutes|
    |Maximum number of instances|User dimension, elastic scaling group|Items|5 minutes|
    |Total number of instances|User dimension, elastic scaling group|Items|5 minutes|
    |Number of running instances|User dimension, elastic scaling group|Items|5 minutes|
    |Joining instance number|User dimension, elastic scaling group|Items|5 minutes|
    |Removing number of instances|User dimension, elastic scaling group|Items|5 minutes|

    **Note:** 

    -   Monitor Data is saved for up to 31 days.

    -   Users can view monitoring data for up to 14 days in a row.


-   Viewing Monitoring Data
    1.  Log in to the cloud monitoring console.
    2.  Go to the auto scaling group list in "Auto scaling" under "Cloud Service Monitoring".
    3.  Click the Instance name or the monitor chart in the operation to go To the instance monitoring details page to view the metrics.
    4.  Click the time range quick select button or the exact select function at the top of the page, the maximum monitoring data allows you to view the monitored data for 14 consecutive days.
    5.  Click the zoom in button in the upper-right corner of the monitor MAP to view the monitor larger image.

## Alarm service {#section_vvn_dwd_zdb .section}

-   Parameter descriptions
    -   Metrics: Monitoring indexes provided by the auto scaling service.

    -   Statistical Cycle: the alarm system checks if your monitoring data exceeds the alarm threshold for this cycle. For example, to set a memory usage alarm rule, the statistics cycle is 1 minute, an interval of 1 minute checks if memory usage exceeds the threshold.

    -   Statistical Methods: Statistical Methods refer to settings that exceed the threshold range. You can set the average, maximum, minimum, count, and value in a statistical method.

        -   Average: the average of the monitored data during the statistical cycle. For example, the statistical method selects the average of all monitoring data collected in 15 minutes, when the average is greater than 80% Only when the threshold is exceeded.
        -   Maximum: the maximum value of the monitor data during the statistics cycle. For example, when the statistic result is the maximum value of all metric data collected within 15 minutes, an average value of over 80% is deemed to exceed the threshold. Only when the threshold is exceeded.
        -   Minimum: the minimum value of the monitored data during the statistics cycle. For example, when the statistic result is the minimum value of all metric data collected within 15 minutes, an average value of over 80% is deemed to exceed the threshold. Only when the threshold is exceeded.
        -   Value: Sum of monitoring data during the statistics cycle. For example, Statistical Methods select the requirements and values for all monitoring data collected in 15 minutes, when the value is greater than 80% Only when the threshold is exceeded. Such statistical methods are required for traffic-class metrics.
    -   Continuous number of times: refers to the continuous number of statistical cycle monitoring items that continue to exceed the threshold value to trigger the alarm.

        Example: Set CPU usage to more than 80% alarm, statistical cycle to 5 minutes, 3 consecutive The alarm after the threshold is exceeded, the first time the detection CPU usage exceeds 80%, the alarm notification is not issued. The second time in 5 minutes to detect CPU usage exceeds 80% and no alarm will be issued. The third probe still exceeds 80% Alarm notification will be issued only when. That is, from the first time the actual data exceeds the threshold to the final alarm rule, the minimum time required is statistical cycle X \(number of consecutive probes-1\) = 5 x \(3-1\) = 10 minutes.


-   Set single alarm rule
    1.  Log in to the cloud monitoring console.
    2.  Go to the auto scaling group list in "Auto scaling" under "Cloud Service Monitoring".
    3.  Click the Instance name or the monitor chart in the operation to enter the instance monitoring details page.
    4.  Click the bell button in the upper right corner of the monitor chart or the new alarm rule in the upper right corner of the page, alarm rules can be set for monitoring items corresponding to this instance.

-   Set up bulk alarm rules
    1.  Log in to the cloud monitoring console.
    2.  Enter the list of elastic scale monitoring instances monitored by the cloud service.
    3.  Select the appropriate instance on the instance list page. Then, click "Set Alert Policies" at the bottom of the page to add multiple alert policies.

