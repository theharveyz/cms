# Monitoring of ApsaraDB for RDS {#concept_l2z_2ys_xdb .concept}

By monitoring multiple metrics of ApsaraDB for Relational Database Service \(RDS\), such as disk usage, IOPS usage, connection usage, and CPU usage, CloudMonitor helps you to monitor the running status of RDS. CloudMonitor automatically collects data for RDS metrics from the time after you purchase the RDS service.

**Note:** 

-   RDS provides monitoring and alarm services only for master and read-only instances.
-   After you buy the RDS service, CloudMonitor automatically creates the following four alarm rules for each master instance and read-only instance: CPU usage \> 80%, connection usage \> 80%, IOPS usage \> 80%, and disk usage \> 80%. Alarm notifications are sent to alarm contacts through SMS messages and emails when the thresholds of the alarm rules are exceeded.

## Monitoring service {#section_mm5_5zs_xdb .section}

-   Metrics

    |Metric|Description|Dimension|Unit|Minimum monitoring frequency|
    |:-----|:----------|:--------|:---|:---------------------------|
    |Disk Usage|The percentage of disk space in use in an RDS instance|Instance|%|5 minutes|
    |IOPS Usage|The IOPS usage of an RDS instance|Instance|%|5 minutes|
    |Connections Usage|The percentage of active connections out of all possible connections that programs establish with an RDS instance.|Instance|%|5 minutes|
    |CPU Usage|The percentage of CPU capacity consumed by an RDS instance \(CPU performance is determined by the database memory size.\)|Instance|%|5 minutes|
    |Memory Usage|The percentage of the memory in use in an RDS instance. Currently, the memory usage metric is only supported by MySQL databases.|Instance|%|5 minutes|
    |Read-only Instance Delay|MySQL read-only instance latency|Instance|second|5 minutes|
    |Network Inbound Traffic|Inbound traffic to an instance per second|Instance|bit/s|5 minutes|
    |Network Outbound Traffic|Outbound traffic from an instance per second|Instance|bit/s|5 minutes|
    |RDS Fault|An event-type metric for which alarm rules can be set|N/A|N/A|N/A|
    |RDS Master/Slave Instance Switch|An event-type metric for which alarm rules can be set.|N/A|N/A|N/A|

    The inbound and outbound traffic metrics only support MySQL and SQLServer databases.

-   View monitoring data
    1.  Log on to the [CloudMonitor console](https://partners-intl.console.aliyun.com/#/cms).
    2.  In the left-side navigation pane, choose **Cloud Service Monitoring** \> **ApsaraDB for RDS**.
    3.  Select the region to which the target RDS instance belongs and find the target instance.
    4.  Click the instance name or click **Monitoring Charts** from the **Actions** column to access the Monitoring Charts page.
    5.  To switch to another chart view, click the chart view button in the upper-left corner of the page.

## Alarm service {#section_fkc_y1t_xdb .section}

-   Set an alarm rule
    1.  Log on to the [CloudMonitor console](https://partners-intl.console.aliyun.com/#/cms).
    2.  In the left-side navigation pane, choose **Cloud Service Monitoring** \> **ApsaraDB for RDS**.
    3.  Select the region to which the target RDS instance belongs and find the target instance.
    4.  Click the instance name or click **Alarm Rules** from the **Actions** column to access the Alarm Rules page.
    5.  In the upper-right corner of the displayed page, click **Create Alarm Rule**.
    6.  Set parameters by referring to the following descriptions to create an alarm rule, and then click **Confirm**.
-   **Parameters**
    -   **Products**: ECS, RDS, OSS, among others
    -   **Resource Range**: the range for which an alarm rule takes effect. There are two alarm rule ranges available: **All Resources** and **Instances**.
        -   **All Resources**: Indicates that the specified alarm rule applies to all RDS instances under your name. For example, if you set the resource range to all resources, and set the alarm threshold for CPU usage to 80%, then an alarm is triggered when the CPU usage of any RDS instance exceeds 80%. When you select **All Resources**, you can report alarms for up to 1,000 resources. If the number of your resources exceeds 1,000, alarms cannot be reported for some resources even if they exceed the threshold you set in your alarm rule. Therefore, for these scenarios, we recommend that you use application groups to divide resources by service before setting up alarm rules to avoid this issue.
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

