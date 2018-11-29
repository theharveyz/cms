# RDS monitoring {#concept_l2z_2ys_xdb .concept}

CloudMonitor displays the ApsaraDB for RDS operation status based on four metrics: Disk usage, IOPS usage, Connection usage, and CPU usage. Once you buy ApsaraDB for RDS products, CloudMonitor will automatically start monitoring the above four metrics without any additional operations.

**Note:** 

-   RDS only provides monitoring and alarm services for primary and read-only instances.

-   By default, CloudMonitor will create alarm rules for each primary instance and read-only instance. These rules set up the thresholds of CPU usage, connection usage, IOPS usage, and disk usage all to 80%. When metric data exceeds any of the above thresholds, a text message and email will be sent to the contact person for the Alibaba Cloud account.


## Monitoring service {#section_mm5_5zs_xdb .section}

-   Metric description

    |Metric|Meaning|Dimension|Unit|Minimum monitoring granularity|
    |:-----|:------|:--------|:---|:-----------------------------|
    |Disk usage|The percentage of disk space used by the RDS instance.|Instance|Percentage|5 minutes|
    |IOPS usage|The percentage of I/O requests per second used by the RDS instance.|Instance|Percentage|5 minutes|
    |Connection usage|The connection count is the number of connections that application programs can establish with the RDS instance. Connection usage is the percentage of these connections currently in use.|Instance|Percentage|5 minutes|
    |CPU usage|The percentage of CPU capacity consumed by the RDS instance \(CPU performance is determined by the database memory size.\). |Instance|Percentage|5 minutes|
    |Memory usage|The percentage of the RDS instance’s memory in use. Currently, the memory usage metric is only supported by MySQL databases. |Instance|Percentage|5 minutes|
    |Read-only instance delay|MySQL read-only instance latency|Instance|seconds|5 minutes|
    |Inbound traffic|Inbound traffic to an instance per second|Instance|bit/s|5 minutes|
    |Outbound traffic|Outbound traffic from an instance per second|Instance|bit/s|5 minutes|
    |Instance failure|Event-type metric, for which alarm rules can be set|-|-|-|
    |Instance switchover|Event-type metric, for which alarm rules can be set.|-|-|-|

    The incoming and outgoing network traffic indicators only support MySQL and SQLServer databases.

-   View monitoring data
    1.  Log on to the [CloudMonitor console](http://cms.console.aliyun.com/#/groups/).
    2.  Click **Cloud Service Monitoring**, and then click **ApsaraDB for RDS**.
    3.  Click an instance name in the product instance list or click **Monitoring Charts** in the **Actions** column to access the instance monitoring details page.

    4.  Click the Chart Size button to switch to large chart display \(optional\).

## Alarm service {#section_fkc_y1t_xdb .section}

-   Parameter description
    -   Metric: It is the monitoring indicator provided by RDS.

    -   Statistical Cycle: the alarm system checks if your monitoring data exceeds the alarm threshold for this cycle. For example, if the statistical cycle of the alarm rule for memory usage is set to one minute, the system checks whether the memory usage has exceeded the threshold value every other minute.

    -   Statistic: This sets the method used to determine if the data exceeds the threshold. You can set Average, Maximum, Minimum, and Sum in Statistics.

-   Average: The average value of metric data within a statistical cycle.. The statistical result is the average of all metric data collected within 15 minutes. An average value of over 80% is deemed to exceed the threshold.
-   Maximum: The maximum value of metric data within a statistical period. When the maximum value of the metric data collected within the period is over 80%, the value exceeds the threshold.
-   Minimum: The minimum value of metric data within a statistical period. When the minimum value of the metric data collected within the period is larger than 80%, the value exceeds the threshold.
-   Sum: The sum of metric data within a statistical period. When the sum of the metric data collected within the statistical cycle is over 80%,  it exceeds the threshold. The above statistical methods are required for traffic-based indicators.
    -   Alarm After Threshold Value Exceeded for Several Times: Refers to an alarm which is triggered when the value of the metric item continuously exceeds the threshold value in several consecutive statistical cycles.

        For example, you may set the alarm to go off when the CPU usage rate exceeds 80% within a 5-minute statistical cycle after the threshold value is exceeded for three times. Alarm notification will not be issued when. No alarm is triggered either when the CPU usage exceeds 80% again in the second detection five minutes later. The third probe still exceeds 80%   Therefore, from the first time when the actual data exceeds the threshold to the time when the alarm rule is triggered, the minimum time consumed is: the statistical cycle\*\(the number of consecutive detections-1\), which is 5\*\(3-1\) = 10 minutes in this case.


-   Set alarm rules
    1.  Log on to the [CloudMonitor console](http://cms.console.aliyun.com/#/groups/).
    2.  Click **Cloud Service Monitoring**, and then click **ApsaraDB for RDS** .
    3.  Click an instance name in the product instance list or click **Alarm Rules** in the **Actions** column to access the instance monitoring details page.
    4.  Click **Create Alarm Rules** at the upper right of the alert policies page to create an alert policy based on the entered parameters.

