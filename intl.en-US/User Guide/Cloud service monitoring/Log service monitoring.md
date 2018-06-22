# Log service monitoring {#concept_fwh_cn5_ydb .concept}

CloudMonitor displays the usage of the Log Service based on 11 metrics, including outbound traffic, inbound traffic, overall QPS, and log statistic method. Once you create a Log Service instance, CloudMonitor automatically starts monitoring the service. You can access CloudMonitor Log Service page to view the metric data.  You can configure alarm rules for metrics so that an alarm is triggered when any data exception occurs.

## Monitoring Services {#section_vxj_qn5_ydb .section}

-   Metrics

    |Metric|Definition|Dimension|Unit|Minimum monitor Granularity|
    |:-----|:---------|:--------|:---|:--------------------------|
    |Inflow|Logstore incoming and outgoing flows per minute|userId、Project、Logstore|Bytes|1 minute|
    |Outflow|Logstore flow per minute|userId、Project、Logstore|Bytes|1 minute|
    |SumQPS|Total number of writes per minute in the logstore|userId、Project、Logstore|Count|1 minute|
    |LogMethodQPS|Total number of writes per minute to the logstore.|userId、Project、Logstore、Method|Count|1 minute|
    |LogCodeQPS|Number of writes per minute mapped to a specific status code in the logstore. |userId、Project、Logstore、Status|Count|1 minute|
    |SuccessdByte|Number of successfully resolved bytes in the logstore.|userId、Project、Logstore|Bytes|10 minutes.|
    |SuccessdLines|Number of lines in resolved logs in the logstore.|userId、Project、Logstore|Count|10 minutes|
    |Failedlines|Number of lines in logs failed to be resolved in the logstore.|userId、Project、Logstore|Count|10 minutes|
    |AlarmPV|Total number of ECS configuration errors in the logStore|userId、Project、Logstore|Count|5 minutes|
    |AlarmUv|Total number of ECS instances with incorrect configurations in the logstore.|userId、Project、Logstore|Count|5 minutes|
    |AlarmIPCount|Number of errors incurred by a specific IP address in the logstore.|userId、Project、Logstore、alarm\_type、source\_ip|Count|5 minutes|


-   View metric data
    1.  Log on to the[CloudMonitor console](http://cms.console.aliyun.com/#/groups/).
    2.  Go to the **Log Service** instance list under **Cloud Service Monitoring**.
    3.  Click an instance name from the product instance list or click **Monitoring Charts** from the **Actions** column to access the instance monitoring details page.
    4.  Click the Chart Size button to switch to large chart display\(optional \).

## Alarm service {#section_bgt_d45_ydb .section}

-   Parameter descriptions

    -   Metrics: The monitoring indicators provided by the Log Service.
    -   Statistical cycle: The alarm system checks whether your monitoring data has exceeded the alarm threshold value based on the statistical cycle.  For example, if the statistical cycle of the alarm rule for memory usage is set to one minute, the system checks whether the memory usage has exceeded the threshold value every other minute.
    -   Statistical method: This method is used to determine if the data exceeds the threshold.  You can set Average, Maximum, Minimum, and Sum in the statistical method.
        -   Average: The average value of the metric data within a statistical cycle. The statistical result is the average of the metric data collected within 15 minutes. An average value of over 80% is deemed to exceed the threshold.
        -   Maximum: The maximum value of metric data within a statistical cycle.  When the maximum value of the metric data collected within the statistical cycle is over 80%, the value exceeds the threshold.
        -   Minimum: The minimum value of metric data within a statistical cycle.  When the minimum value of the metric data collected within the statistical cycle is larger than 80%, the value exceeds the threshold.
        -   Sum: The sum of metric data within a statistical cycle.  When the sum of the metric data collected within the statistical cycle is over 80%, it exceeds the threshold.   The preceding statistical methods are needed for traffic-based indicators.
    -   Trigger an alarm after the threshold value has exceeded several times: This refers to an alarm which is triggered when the value of the metric item continuously exceeds the threshold value in several consecutive statistical cycles.

        For example, you may set the alarm to go off when the CPU usage rate exceeds 80% within a 5-minute statistical cycle after the threshold value is exceeded three times. If the CPU usage rate is found to exceed 80% for the first time, no warning notification is sent.  No alarm is reported if the CPU usage rate exceeds 80% only twice in a row.   An alarm is reported only if the CPU usage rate exceeds 80% for the third time. That is, from the first time when the actual data exceeds the threshold to the time when the alarm rule is triggered, the minimum time consumed is the statistical cycle\*\(the quantity of consecutive detection times - 1\) = 5\*\(3-1\) = 10 minutes.

    **Note:** 

    -   When you configure alarm rules, you can select a log method and a status code for QPS. If you do not select one, QPS collects statistical data for all log methods and status codes.
    -   The method fields include PostLogStoreLogs, GetLogtailConfig, PutData,  GetCursorOrData、 GetData 、GetLogStoreHistogram 、GetLogStoreLogs、 ListLogStores、 ListLogStoreTopics。

    -   The status fields include 200, 400, 401, 403, 405, 500, and 502.

-   Set an alarm rule
    1.  Log on to the[CloudMonitor console](http://cms.console.aliyun.com/#/groups/).
    2.  Go to the**Log Service** instance list under **Cloud Service Monitoring**.
    3.  Click **Alarm Rules** from the **Actions** column to access the instance’s Alarm Rules page.
    4.  Enter all the relevant information in the required fields, and click **Confirm** to create a new alarm rule.

