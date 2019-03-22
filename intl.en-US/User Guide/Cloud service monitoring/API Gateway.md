# API Gateway {#concept_cmr_q2c_zdb .concept}

By monitoring multiple metrics of API Gateway, such as the cache used and read hit rate, CloudMonitor helps you to monitor the running status of API Gateway. CloudMonitor automatically collects data for API Gateway metrics from the time after you purchase the API Gateway service. CloudMonitor also allows you to set alarm rules for these metrics so that you can receive alarm notifications once data exceptions occur.

## Monitoring service {#section_hjg_v2c_zdb .section}

-   **Metrics**

    |Metric|Description|Dimension|Unit|Minimum monitor granularity|
    |:-----|:----------|:--------|:---|:--------------------------|
    |Error Distribution|Number of times of 2XX, 4XX, and 5XX status codes returned for an API in one monitoring period.|User and API|Count|1 minute|
    |Inbound traffic|The sum of traffic of requests from an API in one monitoring period|User and API|Bytes|1 minute|
    |Outbound traffic|The sum of traffic of requests from an API in one monitoring period.|User and API|Bytes|1 minute|
    |Response time|The difference between the time when the gateway calls a backend service through an API and the time when the backend service receives the return result in a monitoring period.|User and API|Second|1 minute|
    |The sum of requests|Total number of requests received by an API in a monitoring period|User and API|Count|1 minute|


-   **View monitoring data.**
    1.  Log on to the [CloudMonitor Console](https://partners-intl.console.aliyun.com/#/cms).
    2.  In the left-side navigation pane, choose **Cloud Service Monitoring** \> **API Gateway**.
    3.  Click an instance name in the product instance list or click **Metric Chart** in the **Actions** column to access the instance monitoring details page.
    4.  \(Optional\) Click the **Chart Size** button to switch to large chart display.

## Alarm service {#section_zbk_nhc_zdb .section}

-   **Set an alarm rule.**
    1.  Log on to the [CloudMonitor Console](https://partners-intl.console.aliyun.com/#/cms).
    2.  In the left-side navigation pane, choose **Cloud Service Monitoring** \> **API Gateway**.
    3.  Click an instance name in the product instance list or click **Alarm Rules** in the **Actions** column to access the instance monitoring details page.
    4.  Click **Create Alarm Rules**  at the upper right of the alert policies page to create an alert policy based on the entered parameters.
-   **Parameters**
    -   **Products**: ECS, RDS, OSS, among others
    -   **Resource Range**: the range for which an alarm rule takes effect. There are two alarm rule ranges available: **All Resources** and **Instances**.
        -   **All Resources**: Indicates that the specified alarm rule applies to all API Gateway instances under your name. For example, if you set the resource range to all resources, and set the alarm threshold for CPU usage to 80%, then an alarm is triggered when the CPU usage of any API Gateway instance exceeds 80%. When you select **All Resources**, you can report alarms for up to 1,000 resources. If the number of your resources exceeds 1,000, alarms cannot be reported for some resources even if they exceed the threshold you set in your alarm rule. Therefore, for these scenarios, we recommend that you use application groups to divide resources by service before setting up alarm rules to avoid this issue.
        -   **Instances**: Indicates that the specified rule only applies to a specific instance. For example, if you set the resource range to **Instances** and set the alarm threshold for CPU usage to 80%, an alarm is triggered when the CPU usage of the specified instance exceeds 80%.
    -   **Alarm Rule**: the alarm rule name
    -   **Rule Describe**: the main content of the alarm rule where you define the alarm-triggering conditions, or value threshold, for related metrics. For example, if you describe the rule as **1mins Inbound Bnadwidth \>= 1024 KByte/s**, the alarm service will check every minute whether the inbound bandwidth within one minute meets or exceeds 1024 KByte/s.

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

