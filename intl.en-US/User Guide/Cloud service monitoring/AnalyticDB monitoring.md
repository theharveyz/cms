# AnalyticDB monitoring {#concept_dcx_fwp_ydb .concept}

By monitoring multiple metrics of AnalyticDB, such as rated disk space, disk space in use, and disk usage, CloudMonitor helps you to monitor the usage of the AnalyticDB service. CloudMonitor automatically collects data for AnalyticDB from the time after you purchase the AnalyticDB service. You can view monitoring details on the AnalyticDB monitoring page in the CloudMonitor console. You can also configure alarm rules for metrics so that an alarm is generated when any data exception occurs.

## Monitoring service {#section_p4r_pwp_ydb .section}

-   Metrics

    |Metric|Description|Dimension|Unit|Minimum monitoring frequency|
    |:-----|:----------|:--------|:---|:---------------------------|
    |diskSize|The rated disk capacity|instanceId, tableSchema, workerId|MB|1 minute|
    |diskUsed|The disk capacity in use|instanceId, tableSchema, workerId|MB|1 minute|
    |diskUsedPercent|The disk usage|Instanceid, tableschema, workerid|%|1 minute|


-   View monitoring data
    1.  Log on to the [CloudMonitor console](https://partners-intl.console.aliyun.com/#/cms).
    2.  In the left-side navigation pane, choose **Cloud Service Monitoring** \> **Analytic DB**.
    3.  Find the target instance and click the instance name or click **Monitoring Charts** from the **Actions** column.
    4.  To switch to another chart view, click the chart view button in the upper-left corner of the page.

## Alarm service {#section_eyk_wyp_ydb .section}

-   **Set an alarm rule**
    1.  Log on to the [CloudMonitor console](https://partners-intl.console.aliyun.com/#/cms).
    2.  In the left-side navigation pane, choose **Cloud Service Monitoring** \> **Analytic DB**.
    3.  Find the target instance and click **Alarm Rules** in the **Actions** column.
    4.  In the upper-right corner of the displayed page, click **Create Alarm Rule**.
    5.  Set parameters by referring to the following descriptions to create an alarm rule, and then click **Confirm**.
-   **Parameters**
    -   **Products**: ECS, RDS, OSS, among others
    -   **Resource Range**: the range for which an alarm rule takes effect. There are two alarm rule ranges available: **All Resources** and **Instances**.
        -   **All Resources**: Indicates that the specified alarm rule applies to all AnalyticDB instances under your name. For example, if you set the resource range to all resources, and set the alarm threshold for CPU usage to 80%, then an alarm is triggered when the CPU usage of any instance exceeds 80%. When you select **All Resources**, you can report alarms for up to 1,000 resources. If the number of your resources exceeds 1,000, alarms cannot be reported for some resources even if they exceed the threshold you set in your alarm rule. Therefore, for these scenarios, we recommend that you use application groups to divide resources by service before setting up alarm rules to avoid this issue.
        -   **Instances**: Indicates that the specified rule only applies to a specific instance. For example, if you set the resource range to **Instances** and set the alarm threshold for CPU usage to 80%, an alarm is triggered when the CPU usage of the specified instance exceeds 80%.
    -   **Alarm Rule**: the alarm rule name
    -   **Rule Describe**: the main content of the alarm rule where you define the alarm-triggering conditions, or value threshold, for related metrics. For example, if you describe the rule as **5mins Average CPU Usage \>= 90%**, the alarm service will check every five minutes whether the average value of CPU usage within five minutes meets or exceeds 90%.

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

