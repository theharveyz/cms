# ApsaraDB for Redis {#concept_vhm_kv4_ydb .concept}

By monitoring multiple metrics from ApsaraDB for Redis, such as CPU usage, memory usage, and connection usage, CloudMonitor helps you to monitor the running status and usage of Redis. CloudMonitor automatically collects data for the metrics from the time after you create a Redis instance. You can view the Redis monitoring data on the ApsaraDB for Redis page of the CloudMonitor console. You can also configure alarm rules for metrics so that you can be notified of any alarm when data exceptions occur.

## Monitoring service {#section_j5m_hw4_ydb .section}

-   Metrics

    |Metric|Description|Dimension|Unit|Minimum monitoring frequency|
    |:-----|:----------|:--------|:---|:---------------------------|
    |Capacity in use|The Redis capacity that is occupied|Instance|Byte|1 minute|
    |Number of connections used|Total number of client connections|Instance|Count|1 minute|
    |Write speed|The network traffic written per second|Instance|bit/s|1 minute|
    |Read Speed|The network traffic read per second|Instance|bit/s|1 minute|
    |Failed operations|The number of failed operations on KVSTORE|Instance|Count|1 minute|
    |Capacity usage|The percentage of currently occupied capacity to total capacity|Instance|%|1 minute|
    |Connections Usage|The percentage of established connections out of all possible connections|Instance|%|1 minute|
    |Inbound Bandwidth Usage|The inbound bandwidth as a percentage of total bandwidth|Instance|%|1 minute|
    |Outbound Bandwidth Usage|The outbound bandwidth as a percentage of total bandwidth|Instance|%|1 minute|
    |Redis fault|Event-type metric, for which alarm rules can be set|N/A|N/A|N/A|
    |Redis Master/Slave Instance Switch|Event-type metric, for which alarm rules can be set.|N/A|N/A|N/A|


-   View monitoring data
    1.  Log on to the [CloudMonitor console](https://partners-intl.console.aliyun.com/#/cms).
    2.  In the left-side navigation pane, choose **Cloud Service Monitoring** \> **ApsaraDB for Redis**.
    3.  Select the region to which the target instance belongs and select the instance type.
    4.  Find the target instance and click the instance name or click **Monitoring Charts** from the **Actions** column.
    5.  To switch to a larger view, click the enlargement icon in the upper-right corner of the chart.

## Alarm service {#section_yy5_qw4_ydb .section}

-   Set an alarm rule
    1.  Log on to the [CloudMonitor console](https://partners-intl.console.aliyun.com/#/cms).
    2.  In the left-side navigation pane, choose **Cloud Service Monitoring** \> **ApsaraDB for Redis**.
    3.  Select the region to which the target instance belongs and select the instance type.
    4.  Find the target instance and click **Alarm Rules** in the **Actions**column.
    5.  In the upper-right corner of the displayed page, click **Create Alarm Rules**.
    6.  Configure the alarm rule by referring to the following parameter descriptions. Then, click **Confirm**.
-   **Parameters**
    -   **Products**: ECS, RDS, OSS, among others
    -   **Resource Range**: the range for which an alarm rule takes effect. There are two alarm rule ranges available: **All Resources** and **Instances**.
        -   **All Resources**: Indicates that the specified alarm rule applies to all Redis instances under your account. For example, if you set the resource range to **All Resources**, and set the alarm threshold for CPU usage to 80%, then an alarm is triggered when the CPU usage of any Redis instance exceeds 80%. When you select **All Resources**, you can report alarms for up to 1,000 resources. If the number of your resources exceeds 1,000, alarms cannot be reported for some resources even if they exceed the threshold you set in your alarm rule. Therefore, for these scenarios, we recommend that you use application groups to divide resources by service before setting up alarm rules to avoid this issue.
        -   **Instances**: Indicates that the specified rule only applies to a specific instance. For example, if you set the resource range to **Instances** and set the alarm threshold for inbound traffic to 100 MB, an alarm is triggered when the inbound traffic of the specified instance exceeds 100 MB.
    -   **Alarm Rule**: the alarm rule name
    -   **Rule Describe**: the main content of the alarm rule where you define the alarm-triggering conditions, or value threshold, for related metrics. For example, if you describe the rule as **5mins Average Inbound Traffic \>= 100 MB**, the alarm service will check every five minutes whether the average value of inbound traffic within five minutes meets or exceeds 100 MB.

        Consider the following example. For the alarm service in host monitoring, one data point is reported in 15 seconds for a single server metric, and 20 data points in five minutes. This relates to the following alarm rules.

        -   **5mins Average CPU Usage \> 90%**: The average CPU usage value of the 20 data points in five minutes exceeds 90%.
        -   **5mins CPU Usage Always \> 90%**: The CPU usage values of the 20 data points in five minutes all exceed 90%.
        -   **5mins CPU Usage Once \> 90%**: The CPU usage value of at least one of the 20 data points in five minutes exceeds 90%.
        -   **Total 5mins Internet Outbound Traffic \> 50 MB**: The sum of the outbound traffic values of the 20 data points in five minutes exceeds 50 MB.
    -   **Mute For**: the period of time that an alarm has been muted so that alarm contacts do not receive any alarm notifications during this period. An alarm rule can be muted up to 24 hours \(or 1 day\).
    -   **Triggered when threshold is exceeded for**: An alarm notification is sent if the detected values reach the alarm rule threshold a certain number of times consecutively. For example, if you set this parameter to **3** and set **Rule Describe** to **5min Average CPU Usage \> 80%**, only when the average CPU usage in five minutes is detected to be greater than 80% for three times in a row, will an alarm be triggered.
    -   **Effective Period**: the period of time for which an alarm rule is effective. During this period of time, the alarm service checks metric data and determines whether to generate an alarm.
    -   **Notification Contact**: a group of contacts who receive alarm notifications.
    -   **Notification Methods**: Email and DingTalk chatbot.
    -   **Email Subject**: The email subject is set as the product name, metric, and instance ID involved in the alarm by default.
    -   **Email Remark**: supplementary information customized for an alarm email. Remarks are sent as part of the alarm notification email.
    -    **HTTP CallBack**: Enter a URL accessible through the Internet and CloudMonitor will push the alarm information to the address through a POST request. Currently, only HTTP is supported.

