# Express Connect {#concept_blv_wxd_zdb .concept}

By monitoring multiple metrics of Express Connect, such as inbound and outbound traffic, CloudMonitor helps you to monitor the running status of Express Connect. CloudMonitor automatically collects data for Express Connect metrics from the time after you purchase the Express Connect service.

## Monitoring service {#section_ohv_xxd_zdb .section}

-   **Metrics**

    |Metric|Dimension|Unit|Minimum monitoring granularity|
    |:-----|:--------|:---|:-----------------------------|
    |Inbound network traffic|User and instance|Bytes|1 minute|
    |Outbound network traffic|User and instance|Bytes|1 minute|
    |Inbound network bandwidth|User and instance|Bits/s|1 minute|
    |Outbound network bandwidth|User and instance|Bits/s|1 minute|
    |Latency|User and instance|ms|1 minute|
    |Packet loss rate|User and instance|%|1 minute|

    **Note:** 

    -   Monitoring data is saved for up to 31 days.
    -   You can view the monitoring data for up to 14 consecutive days.

-   **View monitoring data.**
    1.  Log on to the [CloudMonitor Console](https://partners-intl.console.aliyun.com/#/cms).
    2.  In the left-side navigation pane, choose **Cloud Service Monitoring** \> **Express Connect**.
    3.  Click an instance name or click **Monitoring Chart** in the **Action** column to access the instance monitoring details page and view metrics.
    4.  Click the **Time Range** toggle button on the top of the page or use the specific selection function. Up to 14 consecutive days of metric data can be viewed.
    5.  Click **Zoom In** button in the upper-right corner of the monitoring chart to view a large image.

## Alarm service {#section_ihr_vyd_zdb .section}

-   **Set an alarm rule.**
    1.  Log on to the [CloudMonitor Console](https://partners-intl.console.aliyun.com/#/cms).
    2.  In the left-side navigation pane, choose **Cloud Service Monitoring** \> **Express Connect**.
    3.  Click an instance name or click **Monitoring Chart** in the **Action** column to access the instance monitoring details page and view metrics.
    4.  Click the bell button in the upper-right corner of the monitoring chart or **New Alarm Rule** in the upper-right corner of the page to set an alarm rule for corresponding monitoring metrics of this instance.

-   **Set multiple alarm rules.**
    1.  Log on to the [CloudMonitor Console](https://partners-intl.console.aliyun.com/#/cms).
    2.  In the left-side navigation pane, choose **Cloud Service Monitoring** \> **Express Connect**.
    3.  Select instances on the instance list page. Click **Set Alarm Rules** to add multiple alarm rules.
-   **Parameters**
    -   **Products**: ECS, RDS, OSS, among others
    -   **Resource Range**: the range for which an alarm rule takes effect. There are two alarm rule ranges available: **All Resources** and **Instances**.
        -   **All Resources**: Indicates that the specified alarm rule applies to all Express Connect instances under your name. For example, if you set the resource range to all resources, and set the alarm threshold for CPU usage to 80%, then an alarm is triggered when the CPU usage of any Express Connect instance exceeds 80%. When you select **All Resources**, you can report alarms for up to 1,000 resources. If the number of your resources exceeds 1,000, alarms cannot be reported for some resources even if they exceed the threshold you set in your alarm rule. Therefore, for these scenarios, we recommend that you use application groups to divide resources by service before setting up alarm rules to avoid this issue.
        -   **Instances**: Indicates that the specified rule only applies to a specific instance. For example, if you set the resource range to **Instances** and set the alarm threshold for CPU usage to 80%, an alarm is triggered when the CPU usage of the specified instance exceeds 80%.
    -   **Alarm Rule**: the alarm rule name
    -   **Rule Describe**: the main content of the alarm rule where you define the alarm-triggering conditions, or value threshold, for related metrics. For example, if you describe the rule as **5mins Inbound Bandwidth \>= 100 Mbit/s**, the alarm service will check every five minutes whether the inbound bandwidth within five minutes meets or exceeds 100 Mbit/s.

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

