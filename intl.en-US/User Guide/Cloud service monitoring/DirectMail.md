# DirectMail {#concept_pwd_g2d_zdb .concept}

By monitoring multiple metrics of DirectMail, such as the WEB/API messaging, SMTP messaging, and metrics related to account exceptions, CloudMonitor helps you to monitor the running status of DirectMail. CloudMonitor automatically collects data for DirectMail metrics from the time after you purchase the DirectMail service.

## Monitoring service {#section_ycm_n2d_zdb .section}

-   **Metrics**

    |Metric|Unit|Minimum monitor granularity|
    |:-----|:---|:--------------------------|
    |Web/API error-QPS delayed|Count/Min|1 minute|
    |Web/API error-over-quota QPS|Count/Min|1 minute|
    |Web/API error-spam QPS|Count/Min|1 minute|
    |Web/API message success QPS|Count/Min|1 minute|
    |SMTP authentication failed QPS|Count/Min|1 minute|
    |SMTP authentication is successful QPS|Count/Min|1 minute|
    |SMTP error-length exceeded QPS|Count/Min|1 minute|
    |SMTP error-over-quota QPS|Count/Min|1 minute|
    |SMTP error-spam QPS|Count/Min|1 minute|

    **Note:** 

    -   Monitor Data is saved for up to 31 days.
    -   Users can view monitoring data for up to 14 days in a row.

-   **Viewing monitoring data.**
    1.  Log on to the [CloudMonitor Console](https://partners-intl.console.aliyun.com/#/cms).
    2.  In the left-side navigation pane, choose **Cloud Service Monitoring** \> **DirectMail**.

## Alarm service {#section_lvy_fgd_zdb .section}

CloudMonitor provides alarm functions for DirectMail metrics, so that you are notified immediately in case of any metric exceptions.

-   **Set alarm rules.**

    1.  Log on to the [CloudMonitor Console](https://partners-intl.console.aliyun.com/#/cms).
    2.  In the left-side navigation pane, choose **Cloud Service Monitoring** \> **DirectMail**.
    3.  Click **Alarm Rules** to go to the Alarm Rules list page. Click **Create Alarm Rules** in the upper-right corner to create alarm rules.

        Or click the bell icon in the upper-right corner of the monitoring chart or **New Alarm Rule** in the upper-right corner of the page to set an alarm rule for corresponding monitoring metrics of this instance.

-   **Parameters**
    -   **Products**: ECS, RDS, OSS, among others
    -   **Resource Range**: the range for which an alarm rule takes effect. There are two alarm rule ranges available: **All Resources** and **Instances**.
        -   **All Resources**: Indicates that the specified alarm rule applies to all ApsaraDB for Memcache instances under your name. For example, if you set the resource range to all resources, and set the alarm threshold for CPU usage to 80%, then an alarm is triggered when the CPU usage of any ApsaraDB for Memcache instance exceeds 80%. When you select **All Resources**, you can report alarms for up to 1,000 resources. If the number of your resources exceeds 1,000, alarms cannot be reported for some resources even if they exceed the threshold you set in your alarm rule. Therefore, for these scenarios, we recommend that you use application groups to divide resources by service before setting up alarm rules to avoid this issue.
        -   **Instances**: Indicates that the specified rule only applies to a specific instance. For example, if you set the resource range to **Instances** and set the alarm threshold for CPU usage to 80%, an alarm is triggered when the CPU usage of the specified instance exceeds 80%.
    -   **Alarm Rule**: the alarm rule name
    -   **Rule Describe**: the main content of the alarm rule where you define the alarm-triggering conditions, or value threshold, for related metrics. For example, if you describe the rule as **1mins Average CPU Usage \>= 80%**, the alarm service will check every minute whether the average value of CPU usage within one minute meets or exceeds 80%.

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

