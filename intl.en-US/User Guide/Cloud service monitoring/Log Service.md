# Log Service {#concept_fwh_cn5_ydb .concept}

By monitoring multiple metrics of Log Service, such as the outbound traffic, inbound traffic, overall QPS, and log statistic method, CloudMonitor helps you to monitor the running status of Log Service. CloudMonitor automatically collects data for Log Service metrics from the time after you purchase the Log Service service. CloudMonitor also allows you to set alarm rules for these metrics so that you can receive alarm notifications once data exceptions occur.

## Monitoring Services {#section_vxj_qn5_ydb .section}

-   **Metrics**

    |Metric|Definition|Dimension|Unit|Minimum monitor Granularity|
    |:-----|:---------|:--------|:---|:--------------------------|
    |Inflow|Logstore inboud and outbound traffic per minute|userId, Project, and Logstore|Bytes|1 minute|
    |Outflow|Logstore traffic per minute|userId, Project, and Logstore|Bytes|1 minute|
    |SumQPS|Total number of writes per minute in the Logstore|userId, Project, and Logstore|Count|1 minute|
    |LogMethodQPS|Total number of writes per minute to the Logstore|userId, Project, and Logstore|Count|1 minute|
    |LogCodeQPS|Number of writes per minute mapped to a specific status code in the Logstore|userId, Project, and Logstore|Count|1 minute|
    |SuccessdByte|Number of successfully resolved bytes in the Logstore|userId, Project, and Logstore|Bytes|10 minutes.|
    |SuccessdLines|Number of lines in resolved logs in the Logstore|userId, Project, and Logstore|Count|10 minutes|
    |Failedlines|Number of lines in logs failed to be resolved in the Logstore|userId, Project, and Logstore|Count|10 minutes|
    |AlarmPV|Total number of ECS configuration errors in the LogStore|userId, Project, and Logstore|Count|5 minutes|
    |AlarmUv|Total number of ECS instances with incorrect configurations in the Logstore|userId, Project, and Logstore|Count|5 minutes|
    |AlarmIPCount|Number of errors incurred by a specific IP address in the Logstore|userId, Project, Logstore, alarm\_type, and source\_ip|Count|5 minutes|


-   **View monitoring data.**
    1.  Log on to the [CloudMonitor Console](https://partners-intl.console.aliyun.com/#/cms).
    2.  In the left-side navigation pane, choose **Cloud Service Monitoring** \> **Log Service**.
    3.  Click an instance name from the product instance list or click **Monitoring Charts** in the **Actions** column to access the instance monitoring details page.
    4.  \(Optional\) Click the **Chart Size** button to switch to large chart display.

## Alarm service {#section_bgt_d45_ydb .section}

-   Set an alarm rule
    1.  Log on to the [CloudMonitor Console](https://partners-intl.console.aliyun.com/#/cms).
    2.  In the left-side navigation pane, choose **Cloud Service Monitoring** \> **Log Service**.
    3.  Click **Alarm Rules** in the **Actions** column to access the instance’s Alarm Rules page.
    4.  Enter all the required information and click **Confirm**.
-   **Parameters**

    **Note:** 

    -   When setting alarm rules, you can specify the status for a specific metric. Status codes include 200, 400, 401, 403, 405, 500, and 502.
    -   You can specify the method for a specific metric. Valid values of the method fileds are PostLogStoreLogs, GetLogtailConfig, PutData, GetCursorOrData, GetData, GetLogStoreHistogram, GetLogStoreLogs, ListLogStores, and ListLogStoreTopics.
    -   **Products**: ECS, RDS, OSS, among others
    -   **Resource Range**: the range for which an alarm rule takes effect. There are two alarm rule ranges available: **All Resources** and **Instances**.
        -   **All Resources**: Indicates that the specified alarm rule applies to all Log Service instances under your name. For example, if you set the resource range to all resources, and set the alarm threshold for CPU usage to 80%, then an alarm is triggered when the CPU usage of any Log Service instance exceeds 80%. When you select **All Resources**, you can report alarms for up to 1,000 resources. If the number of your resources exceeds 1,000, alarms cannot be reported for some resources even if they exceed the threshold you set in your alarm rule. Therefore, for these scenarios, we recommend that you use application groups to divide resources by service before setting up alarm rules to avoid this issue.
        -   **Instances**: Indicates that the specified rule only applies to a specific instance. For example, if you set the resource range to **Instances** and set the alarm threshold for CPU usage to 80%, an alarm is triggered when the CPU usage of the specified instance exceeds 80%.
    -   **Alarm Rule**: the alarm rule name
    -   **Rule Describe**: the main content of the alarm rule where you define the alarm-triggering conditions, or value threshold, for related metrics. For example, if you describe the rule as **1mins Overall QPS \>= 70**, the alarm service will check every one minute whether the overall PQS within one minute meets or exceeds 70.

        Consider the following example. For the alarm service in host monitoring, one data point is reported in 15 seconds for a single server metric, and 20 data points in five minutes. This relates to the following alarm rules.

        -   **5mins Average CPU Usage \> 90%**: The average CPU usage value of the 20 data points in five minutes exceeds 90%.
        -   **5mins CPU Usage Always \> 90%**: The CPU usage values of the 20 data points in five minutes all exceed 90%.
        -   **5mins CPU Usage Once \> 90%**: The CPU usage value of at least one of the 20 data points in five minutes exceeds 90%.
        -   **Total 5mins Internet Outbound Traffic \> 50 MB**: The sum of the outbound traffic values of the 20 data points in five minutes exceeds 50 MB.
    -   **Mute For**: the period of time that an alarm is muted so that alarm contacts do not receive any alarm notifications during this period. An alarm rule can be muted for up to 24 hours \(or 1 day\).
    -   **Triggered when threshold is exceeded for**: An alarm notification is sent if the detected values reach the alarm rule threshold a certain number of times consecutively.
    -   **Effective Period**: the period of time for which an alarm rule is effective. During this period of time, the alarm service checks metric data and determines whether to generate an alarm.
    -   **Notification Contact**: a group of contacts who receive alarm notifications.
    -   **Notification Methods**: Emails and DingTalk chatbot.
    -   **Email Subject**: The email subject is set as the product name, metric, and instance ID involved in the alarm by default.
    -   **Email Remark**: supplementary information customized for an alarm email. Remarks are sent as part of the alarm notification email body.
    -    **HTTP CallBack**: Enter a URL accessible through the Internet and CloudMonitor will push the alarm information to the address through a POST request. Currently, only HTTP is supported.

