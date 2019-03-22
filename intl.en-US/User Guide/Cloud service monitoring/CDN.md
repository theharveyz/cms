# CDN {#concept_wf2_cwt_xdb .concept}

By monitoring multiple metrics from Alibaba Cloud Content Delivery Network \(CDN\), such as QPS, BPS, and byte hit rate, CloudMonitor helps you to gain insights into the usage of domain names. CloudMonitor automatically begins to collect data from CDN domains after you add a CDN domain name. You can view the monitoring details on the Alibaba Cloud CDN page of the CloudMonitor console. You can also configure alarm rules for metrics so that you can be notified of any alarm when data exceptions occur.

## Monitoring service {#section_cxz_lwt_xdb .section}

-   Metrics

    |Metric|Description|Dimension|Unit|Minimum monitoring frequency|
    |:-----|:----------|:--------|:---|:---------------------------|
    |QPS|The number of visits per second|Domain name|Count/s|1 minute|
    |Peak Bandwidth|The maximum network bandwidth within a certain period of time|Domain name|bit/s|1 minute|
    |Hit Rate|The ratio of bytes served by the cache over the total number of bytes requested by the clients \(bytes = number of requests × traffic\). The byte hit rate directly reflects the back-to-source traffic.|Domain name|%|1 minute|
    |Public Network Outbound Traffic|The downstream Internet traffic of CDN|Domain name|Byte|5 minutes|
    |4xx Code|The percentage of HTTP 4xx codes out of all returned codes|Domain name|%|1 minute|
    |5xx Code|The percentage of HTTP 5xx codes out of all returned codes|Domain name|%|1 minute|

-   Viewing monitoring data
    1.  Log on to the [CloudMonitor console](https://partners-intl.console.aliyun.com/#/cms).
    2.  In the left-side navigation pane, choose **Cloud Service Monitoring** \> **Alibaba Cloud CDN**.
    3.  Click the Domain Name List tab.
    4.  Find the target domain name and click the domain name, or click **Monitoring Charts** in the **Actions** column.
    5.  To switch to a larger view, click the enlargement icon in the upper-right corner of the chart.

## Alarm service {#section_bbz_qj4_ydb .section}

-   Set an alarm rule
    1.  Log on to the [CloudMonitor console](https://partners-intl.console.aliyun.com/#/cms).
    2.  In the left-side navigation pane, choose **Cloud Service Monitoring** \> **Alibaba Cloud CDN**.
    3.  Click the Domain Name List tab.
    4.  Find the target domain name and click **Alarm Rules** in the **Actions** column.
    5.  In the upper-right corner of the displayed page, click **Create Alarm Rule**.
    6.  Configure the alarm rule by referring to the following parameter descriptions. Then, click **Confirm**.
-   **Parameters**
    -   **Products**: ECS, RDS, OSS, among others
    -   **Resource Range**: the range for which an alarm rule takes effect. There are two alarm rule ranges available: **All Resources** and **Domain Name**.
        -   **All Resources**: Indicates that the specified alarm rule applies to all CDN domain names under your account. When you select **All Resources**, you can report alarms for up to 1,000 resources. If the number of your resources exceeds 1,000, alarms cannot be reported for some resources even if they exceed the threshold you set in your alarm rule. Therefore, for these scenarios, we recommend that you use application groups to divide resources by service before setting up alarm rules to avoid this issue.
        -   **Instances**: Indicates that the specified rule only applies to a specific domain name.
    -   **Alarm Rule**: the alarm rule name
    -   **Rule Describe**: the main content of the alarm rule where you define the alarm-triggering conditions, or value threshold, for related metrics. For example, if you describe the rule as **5mins Average QPS \>= 300**, the alarm service will check every minute whether the average value of QPS within five minutes meets or exceeds 90.

        Consider the following example. For the alarm service in host monitoring, one data point is reported in 15 seconds for a single server metric, and 20 data points in five minutes. This relates to the following alarm rules.

        -   **5mins Average CPU Usage \> 90%**: The average CPU usage value of the 20 data points in five minutes exceeds 90%.
        -   **5mins CPU Usage Always \> 90%**: The CPU usage values of the 20 data points in five minutes all exceed 90%.
        -   **5mins CPU Usage Once \> 90%**: The CPU usage value of at least one of the 20 data points in five minutes exceeds 90%.
        -   **Total 5mins Internet Outbound Traffic \> 50 MB**: The sum of the outbound traffic values of the 20 data points in five minutes exceeds 50 MB.
    -   **Mute For**: the period of time that an alarm has been muted so that alarm contacts do not receive any alarm notifications during this period. An alarm rule can be muted up to 24 hours \(or 1 day\).
    -   **Triggered when threshold is exceeded for**: An alarm notification is sent if the detected values reach the alarm rule threshold a certain number of times consecutively. For example, if you set this parameter to **3** and set **Rule Describe** to **5mins Average CPU Usage \> 80%**, only when the average CPU usage in five minutes is detected to be greater than 80% for three times in a row, will an alarm be triggered.
    -   **Effective Period**: the period of time for which an alarm rule is effective. During this period of time, the alarm service checks metric data and determines whether to generate an alarm.
    -   **Notification Contact**: a group of contacts who receive alarm notifications.
    -   **Notification Methods**: Email and DingTalk chatbot.
    -   **Email Subject**: The email subject is set as the product name, metric, and instance ID involved in the alarm by default.
    -   **Email Remark**: supplementary information customized for an alarm email. Remarks are sent as part of the alarm notification email.
    -    **HTTP CallBack**: Enter a URL accessible through the Internet and CloudMonitor will push the alarm information to the address through a POST request. Currently, only HTTP is supported.

