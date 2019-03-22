# Auto Scaling {#concept_oxw_1rd_zdb .concept}

By monitoring multiple metrics of Auto Scaling, such as the maximum and minimum numbers of instances, CloudMonitor helps you to monitor the running status of Auto Scaling. CloudMonitor automatically collects data for Auto Scaling metrics from the time after you purchase the Auto Scaling service.

## Monitoring service {#section_rbs_4td_zdb .section}

-   **Metrics**

    |Metric|Dimension|Unit|Minimum monitor granularity|
    |:-----|:--------|:---|:--------------------------|
    |Minimum number of instances|User dimension, elastic scaling group|Items|5 minutes|
    |Maximum number of instances|User dimension, elastic scaling group|Items|5 minutes|
    |Total number of instances|User dimension, elastic scaling group|Items|5 minutes|
    |Number of running instances|User dimension, elastic scaling group|Items|5 minutes|
    |Joining instance number|User dimension, elastic scaling group|Items|5 minutes|
    |Removing number of instances|User dimension, elastic scaling group|Items|5 minutes|

    **Note:** 

    -   Monitor Data is saved for up to 31 days.
    -   Users can view monitoring data for up to 14 days in a row.

-   **Viewing monitoring data.**
    1.  Log on to the [CloudMonitor Console](https://partners-intl.console.aliyun.com/#/cms).
    2.  In the left-side navigation pane, choose **Cloud Service Monitoring** \> **Auto Scaling**.
    3.  Click the instance name or the monitor chart in the operation to go to the instance monitoring details page to view the metrics.
    4.  Click the **Time Range** toggle button or the exact select function at the top of the page, the maximum monitoring data allows you to view the monitored data for 14 consecutive days.
    5.  Click **Zoom In** in the upper-right corner of the monitor map to view the monitor larger image.

## Alarm service {#section_vvn_dwd_zdb .section}

-   **Set an alarm rule.**
    1.  Log on to the [CloudMonitor Console](https://partners-intl.console.aliyun.com/#/cms).
    2.  In the left-side navigation pane, choose **Cloud Service Monitoring** \> **Auto Scaling**.
    3.  Click the instance name or the monitor chart in the operation to enter the instance monitoring details page.
    4.  Click the bell button in the upper right corner of the monitor chart or the new alarm rule in the upper right corner of the page, alarm rules can be set for monitoring items corresponding to this instance.

-   **Set multiple alarm rules.**
    1.  Log on to the [CloudMonitor Console](https://partners-intl.console.aliyun.com/#/cms).
    2.  In the left-side navigation pane, choose **Cloud Service Monitoring** \> **Auto Scaling**.
    3.  Enter the list of elastic scale monitoring instances monitored by the cloud service.
    4.  Select the appropriate instance on the instance list page. Then, click **Set Alert Policies** at the bottom of the page to add multiple alert policies.
-   **Parameters**
    -   **Products**: ECS, RDS, OSS, among others
    -   **Resource Range**: the range for which an alarm rule takes effect. There are two alarm rule ranges available: **All Resources** and **Instances**.
        -   **All Resources**: Indicates that the specified alarm rule applies to all Auto Scaling instances under your name. For example, if you set the resource range to all resources, and set the alarm threshold for CPU usage to 80%, then an alarm is triggered when the CPU usage of any Auto Scaling instance exceeds 80%. When you select **All Resources**, you can report alarms for up to 1,000 resources. If the number of your resources exceeds 1,000, alarms cannot be reported for some resources even if they exceed the threshold you set in your alarm rule. Therefore, for these scenarios, we recommend that you use application groups to divide resources by service before setting up alarm rules to avoid this issue.
        -   **Instances**: Indicates that the specified rule only applies to a specific instance. For example, if you set the resource range to **Instances** and set the alarm threshold for CPU usage to 80%, an alarm is triggered when the CPU usage of the specified instance exceeds 80%.
    -   **Alarm Rule**: the alarm rule name
    -   **Rule Describe**: the main content of the alarm rule where you define the alarm-triggering conditions, or value threshold, for related metrics. For example, if you describe the rule as **5mins Maximum Number of Instance \>= 10**, the alarm service will check every five minutes whether the maximum number of instances within five minutes meets or exceeds 10.

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

